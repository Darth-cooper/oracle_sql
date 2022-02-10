--日期轉字串
SELECT TO_CHAR(SYSDATE, 'MM/DD/YY HH24:MI:SS') FROM dual;


--日期加減
--加法
select sysdate,add_months(sysdate, 12) from dual; --加1年
select sysdate,add_months(sysdate, 1) from dual; --加1月
select sysdate,to_char(sysdate+ 7,'yyyy-mm-dd HH24:MI:SS' ) from dual ; --加1星期
select sysdate,to_char(sysdate+ 1,'yyyy-mm-dd HH24:MI:SS' ) from dual ; --加1天
select sysdate,to_char(sysdate+ 1/24 ,'yyyy-mm-dd HH24:MI:SS') from dual; --加1小時
select sysdate,to_char(sysdate+ 1/24 /60, 'yyyy-mm-dd HH24:MI:SS') from dual; --加1分鐘
select sysdate,to_char(sysdate+ 1/24 /60/ 60,'yyyy-mm-dd HH24:MI:SS' ) from dual; --加1秒
 
--減法
select sysdate,add_months(sysdate,- 12) from dual; --減1年
select sysdate,add_months(sysdate,- 1) from dual; --減1月
select sysdate,to_char(sysdate- 7,'yyyy-mm-dd HH24:MI:SS' ) from dual ; --減1星期
select sysdate,to_char(sysdate- 1,'yyyy-mm-dd HH24:MI:SS' ) from dual ; --減1天
select sysdate,to_char(sysdate- 1/24 ,'yyyy-mm-dd HH24:MI:SS') from dual; --減1小時
select sysdate,to_char(sysdate- 1/24 /60, 'yyyy-mm-dd HH24:MI:SS') from dual; --減1分鐘
select sysdate,to_char(sysdate- 1/24 /60/ 60,'yyyy-mm-dd HH24:MI:SS' ) from dual; --減1秒


to_char(sysdate,'FMyyyy-mm-dd')，如果sysdate是2014年4月1日，前面函数导出的数据就不会是2014-04-01，而是2014-4-1



兩個Date型別欄位：START_DATE，END_DATE，計算這兩個日期的時間差（分別以天，小時，分鐘，秒，毫秒）：

天：ROUND(TO_NUMBER(END_DATE - START_DATE))

小時：ROUND(TO_NUMBER(END_DATE - START_DATE) * 24)

分鐘：ROUND(TO_NUMBER(END_DATE - START_DATE) * 24 * 60)

秒：ROUND(TO_NUMBER(END_DATE - START_DATE) * 24 * 60 * 60)

毫秒：ROUND(TO_NUMBER(END_DATE - START_DATE) * 24 * 60 * 60 * 1000)
