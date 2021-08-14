# Oracle-11g Commands:
There are some SQL commands for Oracle 11g

--Creat user: (syntex then example)
CREATE USER [user name] IDENTIFIED BY [password];
CREATE USER batch11 IDENTIFIED BY rose;

--Permission for access the database:
GRANT CONNECT,RESORCE,DBA TO [username];
GRANT CONNECT,RESORCE,DBA TO bacth11;

--Connect database:
CONN [username]
conn batch11

--Show user:
SHOW USER;

--Some commands:
To show tabs:
SELECT * FROM TAB;

--To show date:
SELECT SYSDATE FROM DUAL;

--To add:
SELECT 8+4 FROM DUAL;

--To multiply:
SELECT 100*50 FROM DUAL;

--Make uppercase:
SELECT UPPER('rashid') from dual;

--Display 1 to 4 character from the string:
SELECT SUBSTR('Bangladesh',1,4) FROM DUAL;

--Display two digit after dot:
SELECT ROUND (120.58974,2) FROM DUAL;

--Display * sign after 100 and total digit will be 10:
SELECT RPAD(100,10,'*') FROM student;

--Display * sign before 100 and total digit will be 10:
SELECT LPAD(100,10,'*') FROM DUAL;

--For clear screen:
cl scr;

--For commit multiple line: 
/*
[texgt or command]
*/

--For commit one line: 
-- [text or command]

--Create table:
CREATE TABLE [table name] ([column name] [data type][character], .....);
CREATE TABLE School (sc_code number(3), sc_name varchar2(30), sc_location char(20), sc_union varchar2(20), sc_upazila varchar2(20));

--Delete table:
DROP TABLE School;

--Data insurt to table:
INSERT INTO [table name]
VALUES (column data, 'column data','column data','.....','.....');

INSERT INTO School 
VALUES (100, 'Little Angle High School','Azimpur Quarter','Azimpur','Lalbagh');

--To see fileds of the table:
DESC [table name];
DESC School;

--To Insert trigger:
CREATE OR REPLACE TRIGGER insert_trig
AFTER INSERT ON school

BEGIN
            INSERT INTO dml_log_trig_table
            (USER_NAME,DML_DATE, DML_TYPE)
            VALUES (USER,SYSDATE,'INSERT');
END;
/

--To Update trigger

CREATE OR REPLACE TRIGGER update_trig
AFTER UPDATE ON school

BEGIN
            INSERT INTO dml_log_trig_table
            (USER_NAME,DML_DATE, DML_TYPE)
            VALUES (USER,SYSDATE,'UPDATE');
END;
/

--To Delete trigger

CREATE OR REPLACE TRIGGER delete_trig
AFTER INSERT ON school

BEGIN
            INSERT INTO dml_log_trig_table
            (USER_NAME,DML_DATE, DML_TYPE)
            VALUES (USER,SYSDATE,'DELETE');
END;
/

--To see triger activities:
SELECT * FROM [triger name];
SELECT * FROM dml_log_trig_table;

--To see all elements of the triger:
SELECT * FROM USER_TRIGGERS;

--To see triger table's fields:
DESC user_triggers;

--
