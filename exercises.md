# EXERCISES ( POSTGRES & MYSQL )

> Display all the information of the EMP table? </br>
PG `select * from "EMP"` </br> MS `select * from EMP;`

> Display unique Jobs from EMP table? </br>
> PG `select distinct job from emp` </br> MS `select distinct JOB from EMP;`

> List the emps in the asc order of their Salaries? </br>
> select * from emp order by sal asc;

> List the details of the emps in asc order of the Dptnos and desc of Jobs </br>
> PG `select * from emp order by deptno asc, job desc` </br> MS `select * from emp order by DEPTNO asc, JOB desc;`

> Display all the unique job groups in the descending order </br>
> PG `select distinct job from emp order by job asc` </br> MS `select distinct JOB from EMP order by JOB asc;`

> Display all the details of all ‘Mgrs’ </br>
> select distinct e1.* from emp e1 join emp e2 on e1.empno = e2.mgr;
