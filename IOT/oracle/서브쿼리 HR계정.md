# 서브쿼리 HR계정 - 08.06

1. 부서 이름(department_name) 별 직원들의 평균연봉(salary) 을 조회하시오.단,'30번’ 부서의 직원 평균 연봉보다 평균 연봉이 이하인 부서 정보만 출력되어야 합니다. 

   ```sql
   select d.department_name, avg(e.salary) 
   from departments d, employees e 
   where e.department_id = d.department_id 
   and e.salary < (select avg(salary) from employees where department_id = 30) 
   group by d.department_name;
   ```

   - 정답

     ```sql
     select d.department_name, avg(e.salary)
     from employees e, departments d
     where e.department_id = d.department_id
     group by d.department_name
     having avg(e.salary) <= (select avg(salary) from employees where department_id =30);
     ```

     

2. 각 부서(department_id)별로 최고 연봉(salary)를 받는 사원의 사번(employee_id), 성(last_name)과 연봉(salary)을 조회하시오. 단 조회결과는 연봉의 내림차순으로 정렬되어 나타나야 합니다.

   ```sql
    select e.employee_id, e.last_name, e.salary, d.department_id
    from employees e, departments d
    where d.department_id = e.department_id
    and e.salary  > (select max(salary) from employees)
   order by e.salary desc;
   ```

   - 정답

     ```sql
     select employee_id, last_name, salary, department_id
      from employees
     where (department_id, salary) 
     in (select department_id, max(salary) from employees group by department_id)
     order by salary desc;
     ```

     