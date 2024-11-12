data = LOAD '{data000.txt, data000.txt, data002.txt}' USING PigStorage(',') as (name:chararray, ID:INT, buy1:float, buy2:float, buy3:float, 
buy4:float, buy5:float, buy6:float, buy7:float, buy8:float, buy9:float, buy10:float, text1:chararray, text2:chararray, 
text3:chararray, text4:chararray, text5:chararray);
DESCRIBE data;
SH echo '********************************************** data  ***********************************';

data1 = FOREACH data GENERATE
name,
ID,
SIZE(text1) + SIZE(text2) + SIZE(text3) + SIZE(text4) + SIZE(text5) AS S,
LOWER(text2) AS L,
CONCAT(text1,text2,text3,text4,text5) AS C;

DESCRIBE data1;
SH echo '********************************************** data1  ***********************************';

data2 = FOREACH data1 GENERATE
name,
ID,
S,
L,
REPLACE(C,'and','') AS C1,
REPLACE(C,'the','') AS C2;

DESCRIBE data2;
SH echo '********************************************** data2  ***********************************';
DUMP data2;
