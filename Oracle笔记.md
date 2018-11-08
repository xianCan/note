select last_name,first_name from hr.employees;

--连接两列数据，并且可以再两列数据中间进行处理
select last_name || ' ' || first_name as 姓名 from hr.employees;

--消除重复字段
select department_id from hr.employees;
select distinct department_id from hr.employees;

select * from hr.employees where salary>5000
--between..and.. 是闭区间
select * from hr.employees where salary between 2900 and 6000;
select * from hr.employees where salary in (3000,6000)

--模糊查询，%表示任意匹配，_表示有，并且只有一个
select * from hr.employees where first_name like '%a_';
select * from hr.employees where department_id is null;
--与或非 and or not

--排序 desc降序 asc升序
select * from hr.employees order by salary asc

--关联查询
select e.first_name,e.department_id from hr.employees e;
select d.department_id,d.department_name from hr.departments d;
select e.first_name,d.department_name from hr.employees e left join hr.departments d on e.department_id=d.department_id;

--统计函数count max min avg
select count(e.salary) as 月薪高于5000的人数 from hr.employees e where e.salary>5000
select max(salary),min(salary) from hr.employees e where e.department_id =100;
select avg(salary) from hr.employees e;

--分组查询
select avg(salary),e.department_id from hr.employees e group by e.department_id

--视图
create view herosimple as(
       select int,name from hero
)
select * from herosimple
