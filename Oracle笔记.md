select last_name,first_name from hr.employees;

--�����������ݣ����ҿ��������������м���д���
select last_name || ' ' || first_name as ���� from hr.employees;
--�����ظ��ֶ�
select department_id from hr.employees;
select distinct department_id from hr.employees;

select * from hr.employees where salary>5000
--between..and.. �Ǳ�����
select * from hr.employees where salary between 2900 and 6000;
select * from hr.employees where salary in (3000,6000)
--ģ����ѯ��%��ʾ����ƥ�䣬_��ʾ�У�����ֻ��һ��
select * from hr.employees where first_name like '%a_';
select * from hr.employees where department_id is null;
--���� and or not

--���� desc���� asc����
select * from hr.employees order by salary asc

--������ѯ
select e.first_name,e.department_id from hr.employees e;
select d.department_id,d.department_name from hr.departments d;
select e.first_name,d.department_name from hr.employees e left join hr.departments d on e.department_id=d.department_id;

--ͳ�ƺ���count max min avg
select count(e.salary) as ��н����5000������ from hr.employees e where e.salary>5000
select max(salary),min(salary) from hr.employees e where e.department_id =100;
select avg(salary) from hr.employees e;

--�����ѯ
select avg(salary),e.department_id from hr.employees e group by e.department_id