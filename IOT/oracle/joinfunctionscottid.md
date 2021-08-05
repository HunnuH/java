# 08.03 join함수 (scott계정)과제

1. SALESMAN의사원번호, 이름, 급여, 부서명, 근무지코드를조회

   ```sql
   select e.empno, e.ename, e.sal, e.job, d.deptno 
   from emp e, dept d 
   where e.job = 'SALESMAN';
   ```

   - 정답

     ```sql
     select e.empno, e.ename, e.sal, d.dname, d.loc_code 
     from emp e, dept d 
     where job = 'SALESMAN' 
     and e.deptno = d.deptno;

2. 사원이름,부서명, 급여, 근무도시명을조회

   ```sql
   select e.ename, e.job, e.sal, l.city 
   from emp e, locations l;
   ```

   - 정답

     ```sql
     select e.ename, d.dname, e.sal, l.city 
     from emp e, dept d, locations l 
     where e.deptno = d.deptno 
     and d.loc_code = l.loc_code;
     ```

     

3. DALLAS에근무하는사원중급여1500 이상인사원의이름,급여,업무, 입사일, 보너스를조회

   ```sql
   select e.ename, e.sal, e.job, e.hiredate, e.comm 
   from emp e, dept d, locations l 
   where l.city = 'DALLAS' 
   and e.deptno = d.deptno 
   and d.loc_code = l.loc_code 
   and e.sal >= 1500;
   ```

   - 정답

     ```sql
     select e.ename, e.sal, e.job, e.hiredate, e.comm 
     from emp e, dept d, locations l 
     where l.city = 'DALLAS' 
     and e.deptno = d.deptno 
     and d.loc_code = l.loc_code 
     and e.sal >= 1500;
     ```

     

4. EMP 테이블과 DEPT 테이블에있는모든자료를 다음과 같이 조회합니다. 사원번호, 이름, 업무, EMP 테이블의부서번호, DEPT 테이블의부서번호, 부서명을조회

   ```sql
   select e.empno, e.ename, e.job, e.deptno , d.deptno , d.dname  
   from emp e, dept d;
   ```

   - 정답

     ```sql
     select e.empno, e.ename, e.job, e.deptno , d.deptno , d.dname 
     from emp e, dept d
     where e.deptno = d.deptno;
     ```

     

5. DEPT 테이블, LOCATIONS 테이블을이용하여부서번호, 부서명, 해당부서의city 정보를조회

   ```sql
   select d.deptno, d.dname, l.city 
   from dept d, locations l 
   where d.loc_code = l.loc_code;
   ```

   - 정답

     ```sql
     select d.deptno, d.dname, l.city 
     from dept d, locations l 
     where d.loc_code = l.loc_code;
     ```

     