data = LOAD '{data000.txt, data000.txt, data002.txt}' USING PigStorage(',') as (name:chararray, ID:INT, buy1:float, buy2:float, buy3:float, 
buy4:float, buy5:float, buy6:float, buy7:float, buy8:float, buy9:float, buy10:float, text1:chararray, text2:chararray, 
text3:chararray, text4hararray, text5chararray);
DESCRIBE data
SH echo '********************************************** data  ***********************************';
DUMP data;






