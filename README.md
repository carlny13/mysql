# mysql
mysql
查看mysql版本方法：
客户端下：select version()，或者命令行下，键入：status

什么是mysql存储程序？
存储程序有时候被称为：存储模块或者存储例程，一种被数据库服务器所存储和执行的计算机程序，存储程序的源代码（有时）可能是二进制编译版本，
几乎总是占据着数据库服务器系统的表空间，程序总是位于数据库服务器的进程或线程的内存地址中被执行。

主要有3种类型的数据库存储程序：
1、存储过程
2、存储函数
3、触发器

delimiter $$
DROP PROCEDURE if EXISTS helloworld$$
CREATE PROCEDURE helloworlf ()
BEGIN 
    SELECT 'hello world';
END$$

解释：
delimiter（定界符），delimiter命令确保把‘$$’作为语句终结条件，经常，mysql会把“;”作为语句的终结，但是因为存在储存过程在其过程中。
drop procedure if exists语句用来确保在同名存储过程已经存在的情况下将其移除，如果我们不这样做，那么在同名存储过程已存在的情况下将收到一个mysql的修改重复执行的错误。
create procedure 语句指示一个存储过程定义的开始，注意，存储过程名“helloworld”的后面跟这一对内空为空的括号“（）”。如果存储过程有任何参数，那么我们就可以把参数放在里面。但是如果没有参数，我们同样要把圆括号放上，否则，将会语法错误。
begin语句指示存储程序的开始，所有超过一个语句的存储程序必须用至少一个begin-end块来定义存储程序的开始和结束。
SELECT 'hello world'是存储过程中的一个单个语句：一个select语句将“helloworld”返回给它的调用程序，马上将像我们看到的一样，存储程序中的select能够向控制台和调用程序返回数据，就像我们直接把select语句输入mysql命令行一样。
end：结束存储过程的定义。注意用$$来结束对存储过程的定义，这样mysql就知道我们完整的结束了create procedure语句
