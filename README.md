# SQL50Quiz
經典50題SQL練習
[题目来源](https://blog.csdn.net/flycat296/article/details/63681089)

## Table資訊
1.學生表
Student(SId,Sname,Sage,Ssex)
SId 學生編號,Sname 學生姓名,Sage 出生年月,Ssex 學生性別

2.課程表
Course(CId,Cname,TId)
CId 課程編號,Cname 課程名稱,TId 教師編號

3.教師表
Teacher(TId,Tname)
TId 教師編號,Tname教師姓名

4.成績表
SC(SId,CId,score)
SId 學生編號,CId 課程編號,score 分數

![image](image/pic_table.jpg)

## 產生資料SQL
```sql
--學生表 Student
create table Student(SId varchar(10),Sname varchar(10),Sage datetime,Ssex varchar(10));
insert into Student values('01' , '趙雷' , '1990-01-01' ,'男');
insert into Student values('02' , '錢電' , '1990-12-21' ,'男');
insert into Student values('03' , '孫風' , '1990-05-20' ,'男');
insert into Student values('04' , '李雲' , '1990-08-06' ,'男');
insert into Student values('05' , '周梅' , '1991-12-01' ,'女');
insert into Student values('06' , '吳蘭' , '1992-03-01' ,'女');
insert into Student values('07' , '鄭竹' , '1989-07-01' ,'女');
insert into Student values('09' , '張三' , '2017-12-20' ,'女');
insert into Student values('10' , '李四' , '2017-12-25' ,'女');
insert into Student values('11' , '李四' , '2017-12-30' ,'女');
insert into Student values('12' , '趙六' , '2017-01-01' ,'女');
insert into Student values('13' , '孫七' , '2018-01-01' ,'女');

--科目表 Course
create table Course(CId varchar(10),Cname nvarchar(10),TId varchar(10))
insert into Course values('01' , '語文' , '02')
insert into Course values('02' , '數學' , '01')
insert into Course values('03' , '英語' , '03')

--教師表 Teacher
create table Teacher(TId varchar(10),Tname varchar(10))
insert into Teacher values('01' , '張三')
insert into Teacher values('02' , '李四')
insert into Teacher values('03' , '王五')

--成績表 SC
create table SC(SId varchar(10),CId varchar(10),score decimal(18,1))
insert into SC values('01' , '01' , 80)
insert into SC values('01' , '02' , 90)
insert into SC values('01' , '03' , 99)
insert into SC values('02' , '01' , 70)
insert into SC values('02' , '02' , 60)
insert into SC values('02' , '03' , 80)
insert into SC values('03' , '01' , 80)
insert into SC values('03' , '02' , 80)
insert into SC values('03' , '03' , 80)
insert into SC values('04' , '01' , 50)
insert into SC values('04' , '02' , 30)
insert into SC values('04' , '03' , 20)
insert into SC values('05' , '01' , 76)
insert into SC values('05' , '02' , 87)
insert into SC values('06' , '01' , 31)
insert into SC values('06' , '03' , 34)
insert into SC values('07' , '02' , 89)
insert into SC values('07' , '03' , 98)
```

## Quiz
1.	查詢" 01 "課程比" 02 "課程成績高的學生的資訊及課程分數

2.	查詢同時存在" 01 "課程和" 02 "課程的情況

3.	查詢存在" 01 "課程但可能不存在" 02 "課程的情況(不存在時顯示為 null )

4.	查詢不存在" 01 "課程但存在" 02 "課程的情況

5.	查詢平均成績大於等於 60 分的同學的學生編號和學生姓名和平均成績

6.	查詢在 SC 表存在成績的學生資訊

7.	查詢所有同學的學生編號、學生姓名、選課總數、所有課程的總成績(沒成績的顯示為 null )

8.	查有成績的學生資訊

9.	查詢「李」姓老師的數量 

10.	查詢學過「張三」老師授課的同學的資訊 

11.	查詢沒有學全所有課程的同學的資訊 

12.	查詢至少有一門課與學號為" 01 "的同學所學相同的同學的資訊 

13.	查詢和" 01 "號的同學學習的課程完全相同的其他同學的資訊 

14.	查詢沒學過"張三"老師講授的任一門課程的學生姓名 

15.	查詢兩門及其以上不及格課程的同學的學號，姓名及其平均成績 

16.	檢索" 01 "課程分數小於 60，按分數降冪排列的學生資訊

17.	按平均成績從高到低顯示所有學生的所有課程的成績以及平均成績

18.	查詢各科成績最高分、最低分和平均分：

以如下形式顯示：課程 ID，課程 name，最高分，最低分，平均分，及格率，中等率，優良率，優秀率
及格為>=60，中等為：70-80，優良為：80-90，優秀為：>=90
要求輸出課程號和選修人數，查詢結果按人數降冪排列，若人數相同，按課程號昇冪排列

19.	按各科成績進行排序，並顯示排名， Score 重複時保留名次空缺

20.	按各科成績進行排序，並顯示排名， Score 重複時合併名次

21.	查詢學生的總成績，並進行排名，總分重複時保留名次空缺

22.	查詢學生的總成績，並進行排名，總分重複時不保留名次空缺

23.	統計各科成績各分數段人數：課程編號，課程名稱，[100-85]，[85-70]，[70-60]，[60-0] 及所占百分比

24.	查詢各科成績前三名的記錄

25.	查詢每門課程被選修的學生數 

26.	查詢出只選修兩門課程的學生學號和姓名 

27.	查詢男生、女生人數

28.	查詢名字中含有「風」字的學生資訊

29.	查詢同名同性學生名單，並統計同名人數

30.	查詢 1990 年出生的學生名單

31.	查詢每門課程的平均成績，結果按平均成績降冪排列，平均成績相同時，按課程編號昇冪排列

32.	查詢平均成績大於等於 85 的所有學生的學號、姓名和平均成績 

33.	查詢課程名稱為「數學」，且分數低於 60 的學生姓名和分數 

34.	查詢所有學生的課程及分數情況（存在學生沒成績，沒選課的情況）

35.	查詢任何一門課程成績在 70 分以上的姓名、課程名稱和分數

36.	查詢不及格的課程

37.	查詢課程編號為 01 且課程成績在 80 分以上的學生的學號和姓名

38.	求每門課程的學生人數 

39.	成績不重複，查詢選修「張三」老師所授課程的學生中，成績最高的學生資訊及其成績

40. 成績有重複的情況下，查詢選修「張三」老師所授課程的學生中，成績最高的學生資訊及其成績

41.	查詢不同課程成績相同的學生的學生編號、課程編號、學生成績 

42.	查詢每門功成績最好的前兩名

43.	統計每門課程的學生選修人數（超過 5 人的課程才統計）。

44.	檢索至少選修兩門課程的學生學號 

45.	查詢選修了全部課程的學生資訊

46.	查詢各學生的年齡，只按年份來算 

47.	按照出生日期來算，當前月日 < 出生年月的月日則，年齡減一

48.	查詢本周過生日的學生資訊

49.	查詢下周過生日的學生資訊

50.	查詢本月過生日的學生資訊

51.	查詢下月過生日的學生資訊


## My Solution
1.	查詢" 01 "課程比" 02 "課程成績高的學生的資訊及課程分數
>Think：用corss join

```sql
select c.*,d.Cname ,a.score,e.Cname,b.score from 
SC a, SC b, Student c,Course d,Course e
where
1=1
and a.Sid=b.Sid
and a.Cid=01
and b.Cid=02
and a.score>b.score
and c.Sid=a.Sid
and d.Cid=a.Cid
and e.Cid=b.Cid
```
![image](image/q1.jpg)

2.	查詢同時存在" 01 "課程和" 02 "課程的情況
>Think：用cross join

```sql
SELECT * FROM SC a, SC b
WHERE
1=1
AND a.Sid=b.Sid
AND a.Cid=01
AND b.Cid=02
```
![image](image/q2.jpg)

3.	查詢存在" 01 "課程但可能不存在" 02 "課程的情況(不存在時顯示為 null )
>Think：用兩個Table的子查詢，做Left Join

```sql
Select * from 
(Select * from SC Where CId=01) A
Left Join
(Select * FROM SC WHERE CId=02) B
On A.SId=B.SId
```
![image](image/q3.jpg)

4.	查詢不存在" 01 "課程但存在" 02 "課程的情況
>Think：用Left Join

```sql
Select * from
(Select * from sc Where CId=02) a
LEFT JOIN 
(Select * from sc where Cid=01) b
On a.SId=b.SId
Where b.CId is null
```
![image](image/q4.jpg)

5.	查詢平均成績大於等於 60 分的同學的學生編號和學生姓名和平均成績
>Think：用Group by

```sql
SELECT A.SId,A.Sname,B.AVGScore FROM Student A
JOIN 
(SELECT sid,AVG(score) AVGScore FROM SC
GROUP BY SId
HAVING AVG(score) >60) B
ON A.SId=B.SId
```
![image](image/q5.jpg)

6.	查詢在 SC 表存在成績的學生資訊
>Think：1. GROUP by 2. DISTINCT

```sql
--1
SELECT * FROM Student 
WHERE SId IN 
(
SELECT a.Sid FROM SC a
Join Student b
on a.SId=b.SId
GROUP by a.Sid
)
--2
SELECT DISTINCT a.* FROM Student a
Join SC b
on a.SId=b.SId
```
![image](image/q6.jpg)

7.	查詢所有同學的學生編號、學生姓名、選課總數、所有課程的總成績(沒成績的顯示為 null )
>Think：用LEFT JOIN、GROUP BY

```sql
SELECT A.Sid,A.Sname,COUNT(B.CId) ClassAmount,SUM(B.Score) TotalScore 
FROM Student A
Left JOIN SC B
ON A.SId=B.SId
GROUP BY A.SId,A.Sname

```
![image](image/q7.jpg)

8.	查有成績的學生資訊
>Think：Join、DISTINCT

```sql
SELECT DISTINCT A.* FROM Student A
Join SC B
ON A.SId=B.SId
```
![image](image/q8.jpg)

9.	查詢「李」姓老師的數量 
>Think：用like %

```sql
SELECT COUNT(*)NameCount FROM Teacher
WHERE Tname LIKE ('李%')
```
![image](image/q9.jpg)

10.	查詢學過「張三」老師授課的同學的資訊 
>Think：用Join

```sql
SELECT DISTINCT A.* FROM Student A
JOIN SC B
On A.Sid=B.SId
JOIN Course C
On B.CId=C.CId
JOIN Teacher D
On D.TId=C.TId
WHERE D.Tname='張三' 
```
![image](image/q10.jpg)

11.	查詢沒有學全所有課程的同學的資訊 
>Think：用Count、Group by、子查詢

```sql
SELECT sc.SId, st.Sname,COUNT(sc.CId) CourseCount FROM SC sc
Join Student st 
On sc.SId =st.SId
GROUP BY sc.SId,st.Sname
HAVING COUNT(sc.Cid)<
(SELECT COUNT(*) FROM Course)
```
![image](image/q11.jpg)

12.	查詢至少有一門課與學號為" 01 "的同學所學相同的同學的資訊 
>Think：先查01、再用CID In做子查詢

```sql
SELECT * FROM Student 
WHERE SID IN (
SELECT DISTINCT(SID) FROM SC
WHERE CID IN (
SELECT CID FROM SC
WHERE SID =01
)
AND SID <> 01
)
```
![image](image/q12.jpg)

13.	查詢和" 01 "號的同學學習的課程完全相同的其他同學的資訊 
>Think：用join後，再用Count計算數量是否相同

```sql
--參考網路
select stu.* ,r.t2_count from 
student as stu,
(select distinct t2.sid as t2_sid ,count(t2.cid) as t2_count 
	        from(select sc.sid ,sc.cid from sc where sc.sid = 01) t1
		inner join 
			(select sc.sid ,sc.cid from sc ) t2
		on t1.cid = t2.cid
		group by t2.sid
	) as r
	where 
		r.t2_count = (select count(sc.cid) from sc where sc.sid = 05)
		and stu.sid = r.t2_sid;
--可能會有漏洞，如果課程不同但數量相同，在r.t2_count = (select count(sc.cid) from sc where sc.sid = 05)的判斷就會錯誤，畢竟不是從同一張表來

--關鍵:
SELECT B.* FROM 
(SELECT CID FROM SC WHERE SID=01) AS A
JOIN SC AS B
ON A.CId=B.CId

--MySQL:用TEMP TABLE
DECLARE @stSid int
SET @stSid=01

SELECT * INTO #TEMP FROM
(SELECT B.SId, COUNT(B.CID) AS CIDCOUNT FROM 
(SELECT CID FROM SC WHERE SID=@stSid) AS A
JOIN SC AS B
ON A.CId=B.CId
GROUP BY B.SID) C

SELECT ST.* FROM Student ST
JOIN #TEMP B
ON ST.SId=B.SId
WHERE B.SId<>@stSid
AND B.CIDCOUNT=
(SELECT CIDCOUNT FROM #TEMP
WHERE SID=@stSid)

DROP TABLE #TEMP

```
![image](image/q13.jpg)

14.	查詢沒學過"張三"老師講授的任一門課程的學生姓名 
>Think：先找出有上過張三的學生，再排除

```sql
SELECT * FROM Student
WHERE SID NOT IN(
SELECT st.SID FROM Student st 
JOIN SC sc 
ON st.SId=sc.SId
WHERE sc.CId IN 
(SELECT CID FROM Course A
JOIN Teacher B
ON A.TId=B.TId
WHERE B.Tname='張三'
)
)
```
![image](image/q14.jpg)

15.	查詢兩門及其以上不及格課程的同學的學號，姓名及其平均成績 
>Think：先找不及格，再group by 數量

```sql
SELECT * FROM Student WHERE 
SId IN (
SELECT SID FROM SC
WHERE score<60
GROUP BY SID
HAVING COUNT(SID)>=2
)
```
![image](image/q15.jpg)

16.	檢索" 01 "課程分數小於 60，按分數降冪排列的學生資訊
>Think：用Join，注意用IN會錯誤

```sql
--正確
SELECT * FROM Student st
JOIN (
SELECT SID,score FROM SC
WHERE CID=01
AND score<60
) sc
ON st.SId=sc.SId
ORDER BY sc.score DESC

--錯誤
SELECT * FROM Student 
WHERE SID IN (
SELECT SID FROM SC
WHERE CID=01
AND score<60
ORDER BY score DESC
)
```
![image](image/q16.jpg)

17.	按平均成績從高到低顯示所有學生的所有課程的成績以及平均成績
>Think：先整理AVG，再JOIN到課程

```sql
SELECT sc.*, avgsc.avgscore FROM SC sc
JOIN(
SELECT SID,AVG(score) avgscore FROM SC
GROUP BY SID
) avgsc
ON sc.SId=avgsc.SId
```
![image](image/q17.jpg)

18.	查詢各科成績最高分、最低分和平均分：

以如下形式顯示：課程 ID，課程 name，最高分，最低分，平均分，及格率，中等率，優良率，優秀率
及格為>=60，中等為：70-80，優良為：80-90，優秀為：>=90
要求輸出課程號和選修人數，查詢結果按人數降冪排列，若人數相同，按課程號昇冪排列
>Think：

```sql

```
![image](image/q.jpg)

19.	按各科成績進行排序，並顯示排名， Score 重複時保留名次空缺
>Think：

```sql

```
![image](image/q.jpg)

20.	按各科成績進行排序，並顯示排名， Score 重複時合併名次
>Think：

```sql

```
![image](image/q.jpg)

21.	查詢學生的總成績，並進行排名，總分重複時保留名次空缺
>Think：

```sql

```
![image](image/q.jpg)

22.	查詢學生的總成績，並進行排名，總分重複時不保留名次空缺
>Think：

```sql

```
![image](image/q.jpg)

23.	統計各科成績各分數段人數：課程編號，課程名稱，[100-85]，[85-70]，[70-60]，[60-0] 及所占百分比
>Think：

```sql

```
![image](image/q.jpg)

24.	查詢各科成績前三名的記錄
>Think：

```sql

```
![image](image/q.jpg)

25.	查詢每門課程被選修的學生數 
>Think：

```sql

```
![image](image/q.jpg)

26.	查詢出只選修兩門課程的學生學號和姓名 
>Think：

```sql

```
![image](image/q.jpg)

27.	查詢男生、女生人數
>Think：

```sql

```
![image](image/q.jpg)

28.	查詢名字中含有「風」字的學生資訊
>Think：

```sql

```
![image](image/q.jpg)

29.	查詢同名同性學生名單，並統計同名人數
>Think：

```sql

```
![image](image/q.jpg)

30.	查詢 1990 年出生的學生名單
>Think：

```sql

```
![image](image/q.jpg)

31.	查詢每門課程的平均成績，結果按平均成績降冪排列，平均成績相同時，按課程編號昇冪排列
>Think：

```sql

```
![image](image/q.jpg)

32.	查詢平均成績大於等於 85 的所有學生的學號、姓名和平均成績 
>Think：

```sql

```
![image](image/q.jpg)

33.	查詢課程名稱為「數學」，且分數低於 60 的學生姓名和分數 
>Think：

```sql

```
![image](image/q.jpg)

34.	查詢所有學生的課程及分數情況（存在學生沒成績，沒選課的情況）
>Think：

```sql

```
![image](image/q.jpg)

35.	查詢任何一門課程成績在 70 分以上的姓名、課程名稱和分數
>Think：

```sql

```
![image](image/q.jpg)

36.	查詢不及格的課程
>Think：

```sql

```
![image](image/q.jpg)

37.	查詢課程編號為 01 且課程成績在 80 分以上的學生的學號和姓名
>Think：

```sql

```
![image](image/q.jpg)

38.	求每門課程的學生人數 
>Think：

```sql

```
![image](image/q.jpg)

39.	成績不重複，查詢選修「張三」老師所授課程的學生中，成績最高的學生資訊及其成績
>Think：

```sql

```
![image](image/q.jpg)

40. 成績有重複的情況下，查詢選修「張三」老師所授課程的學生中，成績最高的學生資訊及其成績
>Think：

```sql

```
![image](image/q.jpg)
41.	查詢不同課程成績相同的學生的學生編號、課程編號、學生成績 
>Think：

```sql

```
![image](image/q.jpg)
42.	查詢每門功成績最好的前兩名
>Think：

```sql

```
![image](image/q.jpg)
43.	統計每門課程的學生選修人數（超過 5 人的課程才統計）。
>Think：

```sql

```
![image](image/q.jpg)
44.	檢索至少選修兩門課程的學生學號 
>Think：

```sql

```
![image](image/q.jpg)
45.	查詢選修了全部課程的學生資訊
>Think：

```sql

```
![image](image/q.jpg)
46.	查詢各學生的年齡，只按年份來算 
>Think：

```sql

```
![image](image/q.jpg)
47.	按照出生日期來算，當前月日 < 出生年月的月日則，年齡減一
>Think：

```sql

```
![image](image/q.jpg)
48.	查詢本周過生日的學生資訊
>Think：

```sql

```
![image](image/q.jpg)
49.	查詢下周過生日的學生資訊
>Think：

```sql

```
![image](image/q.jpg)
50.	查詢本月過生日的學生資訊
>Think：

```sql

```
![image](image/q.jpg)
51.	查詢下月過生日的學生資訊
>Think：

```sql

```
![image](image/q.jpg)