# 07.03 변수과제

1. 81년도에 입사한 사람들 중에서 job이 ' MANAGER'인 사람들의 성명과 직업을 다음 과 같은 형태로 출력하세요

   ```sql
   select ename, job 
   from emp where job = 'MANAGER'
   and hiredate between '81/01/01'
   and '81/12/31';
   ```

   - 정답

     ``` sql
     select ename ||’:’|| job
     from emp where job = ‘MANAGER’ 
     and hiredate >= ‘81/1/1’ 
     and hiredate<=’81/12/31’;
     ```

     

2. job이 'SALESMAN'이면서 급여가 1500이상인 데이터를 출력 (사번,성명,직업,급여 출력)

   ```sql
   select empno, ename, job, sal
   from emp where job = 'SALESMAN'
   and sal  >'1500';
   ```

   - 정답

     ```sql
     select empno, ename, job, sal,
     from emp where job = 'SALESMAN’ 
     and sal >=1500;
     ```

     

3. 급여(sal) 2000에서 3000사이의 사원 between ~ and 연산자를 이용하여 작업. 급여가 높은 순서대로 출력하세요.(사번,성명,급여)

   ``` sql
   select empno, ename, sal 
   from emp where sal between '2000' and '3000' 
   order by sal desc;
   ```

   - 정답

     ``` sql
     select empno, ename, sal 
     from emp where sal between 2000 and 3000
     order by sal desc;
     ```

     

4. 82년도 이후에 입사했거나 급여가 5000이상인 사람을 출력. (사번,성명,급여,입사년월)

   ```sql
   select empno, ename, sal, hiredate 
   from emp where sal >= '5000' or hiredate > '82/01/01';
   ```

   - 정답

     ``` sql
     select empno, ename, sal, hiredate
     from emp where hiredate >= ‘82/1/1’ or sal >= 5000;
     ```

     

5. emp테이블에서 부서번호가 10이거나 20에 속하는 사원들 중에서 급여가 2000이상인 사원들 의 이름,급여,부서번호를 출력

   ```sql
   select ename, sal, deptno 
   from emp where deptno < '30' and sal > '2000';
   ```

   - 정답

     ``` sql
     select ename, sal, deptno 
     from emp where deptno in(10,20) sand sal >= 2000;
     ```

     

6. 급여가 1300에서 1700사이에 해당하는 사원의 성명,담당업무,급여,부서번호 조회

   ``` sql
   select ename, job, sal, hiredate
   from emp where sal between '1300' and '1700';
   ```

   - 정답

     ```sql
     select ename, job, sal, deptno
     from emp where sal between 1300 and 1700;
     ```

     

7.  사원번호가 7902,7788,7566인 사원의 사원번호, 성명,담당업무,급여,입사일자 조회

   ```sql
   ```

   - 정답

     ```sql
     select empno, ename, job, sal, hiredate
     from emp where empno in (7902,7788,7566);
     ```

     

8.  emp테이블에서 급여가 2800이상이고 job이 MANAGER인 사원의 사원번호,성명,담당업무, 급여,입사일자,부서번호를 조회하기

   ```sql
   select empno, ename, job, sal, hiredate, deptno 
   from emp where sal >= '2800' and job = 'MANAGER';
   ```

   - 정답

     ```sql
     select empno, ename, job, sal, hiredate, deptno
     from emp where sal >= 2800 and jon = ‘MANAGER’;
     ```

     

9. emp테이블에서 JOB이 'MANAGER',"CLERK','ANALYST' 가 아닌 사원의 사원번호, 성명, 담당업무,급여,부서번호 출력

   ```sql
   select empno, ename, job, sal, deptno 
   from emp where job not in ('MANAGER', 'CLERK', 'ANALYST');
   ```

   - 정답

     ```sql
     select empno, ename, job, sal, depno 
     from emp where job not in ('MANAGER','ANALYST’,‘CLERK’);
     ```

     

