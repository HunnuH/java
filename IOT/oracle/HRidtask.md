# 08.02 HR 계정 과제

1. emp테이블에 사원이름, 매니저번호,매니저번호가 null이면 상위자로 표시하고, 매니저 번호가 있으면 담당으로 표시(scott계정이용)

   ```sql
   select ename, mgr, nvl2(to_char(mgr),'담당', '상위자')관리자 from emp;
   ```

   - 정답

     ```sql
     select ename, mgr, nvl2(mgr,'담당', '상위자')관리자 from emp;
     ```

     

2. 각 부서별로 월급의 평균을 조회한 후 평균값이 6000 보다 큰 값만 출력하고 부서번호가 없을 경우는 'No Department'로 출력되도록 하시오.  출력되는 부서별 평균값은 소수점 일의 자리에서 반올림을 시킵니다.  (예 : 4.5 인 경우 5로 변함,   alias를 포함하여 실행결과와 동일하게 출력되어야 합니다.)

   ```sql
   ```

   - 정답

     ```sql
     select nvl(to_char(department_id),'NO Department')부서번호,round(avg(salary),0)평균급여 
     from employees  
     group by department_id 
     having avg(salary) > 6000;
     ```

     

3. EMPLOYEES 테이블에서 부서별 평균연봉을 구하는 SQL 문을 작성하시오.  출력결과는 부서아이디와 평균연봉이며 평균 연봉이 10000 이상(같거나 큰) 부서에 대해서만 정보를 출력하시오. 

   ```sql
   select DEPARTMENT_ID, avg(SALARY) 
   from EMPLOYEES 
   having avg(SALARY)  >= 10000 
   group by DEPARTMENT_ID;
   ```

   - 정답

     ```sql
     select DEPARTMENT_ID, avg(SALARY) 
     from EMPLOYEES 
     having avg(SALARY)  >= 10000 
     group by DEPARTMENT_ID;
     ```

     

4. 부서 아이디별로 해당 부서의 부서아이디, 평균급여를 평균급여에 대한 내림차순으로  정렬하여 조회하시오. 

   ```sql
   select DEPARTMENT_ID, avg(SALARY) 
   from EMPLOYEES 
   having avg(SALARY)  >= 10000 
   group by DEPARTMENT_ID;
   ```

   - 정답

     ```sql
     select DEPARTMENT_ID, avg(SALARY) 
     from EMPLOYEES
     where department_id not in(40,50)
     group by department_id
     order by avg(salary) desc;
     ```

     

5. EMPLOYEE Table에서 first_name, last_name, 급여, 커미션 금액, 총액(sal + comm)을 구하여 총액이 많은 순서로 출력하라. 단, 커미션이 NULL인 사람은 제외한다

   ```sql
    select FIRST_NAME, LAST_NAME, SALARY, COMMISSION_PCT, SALARY+COMMISSION_PCT 총액
    from EMPLOYEES 
    where COMMISSION_PCT is not null
    order by SALARY+COMMISSION_PCT desc;
   ```

   - 정답

     ```sql
     select FIRST_NAME, LAST_NAME, SALARY, COMMISSION_PCT, SALARY+COMMISSION_PCT 총액
      from EMPLOYEES 
      where COMMISSION_PCT is not null
      order by SALARY+COMMISSION_PCT desc;
     ```

     

6. 월 별 입사자 수를 조회하는 SQL 쿼리문을 작성하세요. 월 순으로 정렬하세요.

   ```sql
   select to_char(HIRE_DATE,'MM')월, count(to_char(HIRE_DATE,'MM'))입사자수
   from EMPLOYEES 
   group by to_char(HIRE_DATE,'MM') 
   order by t_char(HIRE_DATE,'MM') asc;
   ```

   - 정답

     ```sql
     select to_char(HIRE_DATE,'MM')월, count(to_char(HIRE_DATE,'MM'))입사자수
     from EMPLOYEES 
     group by to_char(HIRE_DATE,'MM') 
     order by t_char(HIRE_DATE,'MM') asc;
     ```

     







