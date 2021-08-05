### 07.30 문자열 함수 과제 

1. "SMITH의 급여 800만원"의 유형으로 출력할 수 있도록 concat함수를 써서 작업하세요.   단, 급여가 1000만원 미만인 직원에 대해서 작업

   ```sql
   elect concat(ename, concat(':',sal))
   from emp
   where sal < '1000' ;
   ```

   - 정답

     ``` sql
     select concat(ename, concat('의 급여',concat(sal,'만원'))) 
     from emp 
     where sal <1000;
     ```

     

2. 입사일이 81년인 직원에 대해서 각 직원의 이름과 입사일을 나타내시오. (substr이용)

   ```sql
   ```

   - 정답

     ```sql
     select ename, hiredate 
     from emp
     where substr(hiredate,1,2) = 81;
     ```

     

3. 각 직원의 이름,job,급여를 나타내되 급여는 5자리로 나타내며 부족한 자릿수는 *로 표시한다. 급여가 2000만원 이하인 직원만 나타내기

   ``` sql
   select ename,job, lpad(sal, 5, '*') 
   from emp 
   where sal < '2000';
   ```

   - 정답

     ```sql
     select ename, job, lpad(sal,5,'*') 
     from emp
     where sal <= 2000;
     ```

     

   

4. 3번의 결과에서 *를 없애고 출력해보세요..단,함수를 이용하여 작업

   ```sql
   select ename,job, lpad(sal, 5, '*'), ltrim(sal, '*')
   from emp
   where sal < '2000';
   ```

   - 정답

     ```sql
     select ename, job, ltrim( lpad(sal,5,'*'),'*') 
     from emp
     where sal <=2000;
     ```

     

5. emp 테이블에서 scott의 사원번호, 성명, 담당업무(소문자로), 부서번호를조회한다.

   ``` sql
   select empno, ename, lower(job), deptno 
   from emp
   where ename = 'SCOTT';
   ```

   - 정답

     ```sql
     select empno, ename, lower(job), deptno 
     from emp
     where ename = upper('scott');
     ```

     

6. mp 테이블에서 이름의 첫글자가 'K'보다크고 'Y'보다 작은 사원의 사원번호, 이름, 업무, 급여,    부서번호를 조회한다. 단, 이름순으로 정렬하여라.

   ``` sql
   select empno, ename, job, sal, deptno
   from emp
   where ename >'K' and ename <'Y’
   ```

   - 정답

     ```sql
     select empno, ename, job, sal, deptno
     from emp
     where substr(ename, 1,1) > 'K' and
     substr(ename,1,1) < 'Y'
     oreder by ename;
     ```

     

7. emp 테이블에서 10번부서의 사원에 대하여 담당업무 중 좌측에 'A'를 삭제하고 급여 중   좌측의 1을 삭제하여 출력하여라.

   ```sql
   select ename, deptno, ltrim(job,'A'), ltrim(sal,'1'), 
   from emp 
   where deptno = '10';
   ```

   - 정답

     ```sql
     select deptno, ename, ltrim(job,'A') 담당업무, ltrim(sal,1) 급여 
     from emp 
     where deptno = 10;
     
     ```

     

