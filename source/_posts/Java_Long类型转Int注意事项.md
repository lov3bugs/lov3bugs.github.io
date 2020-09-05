---
title: Java_Long类型转Int注意事项
date: 2018-09-05
tags: Hexo
---
2018-09-05 接到用户反馈会员订单付费之后, 会员的有效日期没有增加.
发现BUG隐藏在截止日期的转换方法intValue上, 遂记录之.
 <!-- more -->
 
# 问题
用户反馈会员的订单付款完成, 但是会员的有效日期并没有变化. 并且反馈该问题的不止一例. 

# 解释
如下: 
``` java
public static int subDateFmtStr(String start, String end) {
		if (start == null || end == null) {
			return 0;
		}
		Date starttime = parseYMDHHmmssString(start);
		Date endtime = parseYMDHHmmssString(end);
		if (starttime == endtime) {
			return 0;
		}
		long temp = endtime.getTime() - starttime.getTime();
		
		System.out.println("temp:"+temp);
		/**
		 * 注意：
		 * long 是64位，int 是32位。
		 * 当使用强制类型把long转换为int类型有可能会出现负数问题,
		 * 而Long.MAX_VALUE在Java中的值是2的63次方,即011111111111111(63个1)
		 * 最前面的是符号位 0为正数,1为负数,int截取了后面的32位数 为111111111(32个1)
		 * 这个值就是-1,因为负数是用补码表示的111111111(32个1) 正好就是-1的补码,所以 最终的结果就是-1. 
		 * 例如：
		 *  subDateFmtStr("20141229 16:21:58","20150210 11:43:28")
		 * 
		 */
		//return (int)temp;
		if (temp > 0) {
			//正数
			return 1;
		}else if(temp ==0 ){
			return 0;
		}else {
			//负数 取它的绝对值
			return -1;
		}
	}
```


# 行动
修改代码:
``` java
if (keys.size() > 0) {
	result = getAuthFromRedis(keys, endPointCode);
	result.setResponsibilityType(new ArrayList<>(responsibilityType));
	// allEndDate.sort(Comparator.comparing(Long::intValue).reversed());
	allEndDate.sort(Comparator.comparing(Long::longValue).reversed());
	result.setMemberEndDate(allEndDate.size() > 0 ? new Date(allEndDate.get(0)) : null);
	result.setDaysRemaining(computeLastRemainingDays(result.getMemberEndDate()));
	result.setExpirationReminding(computeExpirationReminding(result.getMemberEndDate(), userResponsibilities));

```


