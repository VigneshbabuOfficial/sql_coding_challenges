# sql_coding_challenges

## sql practice
[REF](https://github.com/VigneshbabuOfficial/vb_important_files/blob/main/sql_queries_to_practice.pdf)

### POSTGRES
> create database
```SQL
-- Database: practice_db

-- DROP DATABASE IF EXISTS practice_db;

CREATE DATABASE practice_db
    WITH
    OWNER = postgres
    ENCODING = 'UTF8'
    LC_COLLATE = 'English_India.1252'
    LC_CTYPE = 'English_India.1252'
    TABLESPACE = pg_default
    CONNECTION LIMIT = -1
    IS_TEMPLATE = False;

 ```
> create tables
```SQL
-- Table: public.DEPT

-- DROP TABLE IF EXISTS public."DEPT";

CREATE TABLE IF NOT EXISTS public."DEPT"
(
    "DEPTNO" integer NOT NULL,
    "DNAME" text COLLATE pg_catalog."default" NOT NULL,
    "LOC" text COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT "DEPT_pkey" PRIMARY KEY ("DEPTNO")
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public."DEPT"
    OWNER to postgres;

----------------------------

-- Table: public.EMP

-- DROP TABLE IF EXISTS public."EMP";

CREATE TABLE IF NOT EXISTS public."EMP"
(
    "EMPNO" integer NOT NULL,
    "ENAME" text COLLATE pg_catalog."default" NOT NULL,
    "JOB" text COLLATE pg_catalog."default" NOT NULL,
    "MGR" integer,
    "HIREDATE" date NOT NULL,
    "SAL" integer,
    "COMM" integer,
    "DEPTNO" integer NOT NULL,
    CONSTRAINT "EMP_pkey" PRIMARY KEY ("EMPNO"),
    CONSTRAINT "EMP_DEPT_FK" FOREIGN KEY ("DEPTNO")
        REFERENCES public."DEPT" ("DEPTNO") MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE SET NULL
        NOT VALID
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public."EMP"
    OWNER to postgres;

```

> populate data
```SQL
TABLE : DEPT

INSERT INTO public."DEPT"(
	"DEPTNO", "DNAME", "LOC")
	VALUES
(10,'ACCOUNTING','NEW YORK'),
(20,'RESEARCH','DALLAS'),
(30,'SALES','CHICAGO'),
(40,'OPERATIONS','BOSTON');

-----------------------------

TABLE : EMP

INSERT INTO public."EMP"(
	"EMPNO", "ENAME", "JOB", "MGR", "HIREDATE", "SAL", "COMM", "DEPTNO")
	VALUES 
(7369,'SMITH','CLERK',7902,'17-Dec-80',800,null,20),
(7499,'ALLEN','SALESMAN',7698,'20-Feb-81',1600,300,30),
(7521,'WARD','SALESMAN',7698,'22-Feb-81',1250,500,30),
(7566,'JONES','MANAGER',7839,'02-Apr-81',2975,null,20),
(7654,'MARTIN','SALESMAN',7698,'28-Sep-81',1250,1400,30),
(7698,'BLAKE','MANAGER',7839,'01-May-81',2850,null,30),
(7782,'CLARK','MANAGER',7839,'09-Jun-81',2450,null,10),
(7788,'SCOTT','ANALYST',7566,'09-Dec-82',3000,null,20),
(7839,'KING','PRESIDENT',null,'17-Nov-81',5000,null,10),
(7844,'TURNER','SALESMAN',7698,'08-Sep-81',1500,0,30),
(7876,'ADAMS','CLERK',7788,'12-Jan-83',1100,null,20),
(7900,'JAMES','CLERK',7698,'03-Dec-81',950,null,30),
(7802,'FORD','ANALYST',7586,'03-Dec-81',3000,null,20),
(7934,'MILLER','CLERK',7782,'23-Jan-82',1300,null,10);


```


