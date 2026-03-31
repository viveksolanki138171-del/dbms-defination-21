Definition 4:
Write a PL/SQL block to display the salary of that employee whose age
is 45 year otherwise display appropriate message using exception
handling.
set serveroutput on;
declare
v_salary emp.sal%type; begin
select sal into v_salary from emp where age = 45;
dbms_output.put_line('salary: ' || v_salary);
exception
when no_data_found then
dbms_output.put_line('no employee with age 45');
when too_many_rows then dbms_output.put_line('multiple
employees found with age 45'); when others then
dbms_output.put_line('error occurred'); 
end;
/
