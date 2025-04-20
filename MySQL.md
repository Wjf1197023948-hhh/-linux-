# MySQL
    MySQL课程介绍

##    一、基础
###        1、MySQL概述
            数据库：存储数据的仓库，数据是有组织的进行存储
            数据库管理系统：操纵和管理数据库的大型软件
            SQL：操纵关系型数据库的编程语言，定义了一套操作关系型数据库同意标准
            Oracle、MySQL、SQL Server、SQLite
            MySQL：关系型数据库，建立在关系模型基础上，由多张相互连接的二维表组成的数据库。

###        2、SQL
            SQL通用语法
                分号结尾
                不区分大小写
                /*注释内容*/

            SQL分类

            DDL：数据定义语言
                数据库操作
                    查询所有数据库：SHOW DATABASES;
                    查询当前数据库：SELECT DATABASE();
                        select database();

                    创建：CREATE DATABASE [IF NOT EXISTS] 数据库名 [DEFAILT CHARSET 字符集] [COLLATE 排序规则];
                        create database itcast;
                        creata database if not exists itcast; 不会被创建
                        creata database if not exists test; 被创建
                        create database itheima default charset utf8mb4;支持4个字节

                    删除：DROP DATABASE [IF EXISTS] 数据库名;
                        drop database test;
                        drop database if exists test;不会报错

                    使用：USE 数据库名;
                        use itcast;


                表操作
                    查询当前数据库所有表：SHOW TABLES;
                    查询表结构：DESC 表名;
                        注：最后一个字段后面没有逗号

                    查询指定表的建表语句：SHOW CREATE TABLE 表名;
                    实例
                        代码
                            CREATE TABLE tb_user (
                                id INT COMMENT '编号',
                                name VARCHAR(50) COMMENT '姓名',
                                age INT COMMENT '年龄',
                                gender VARCHAR(1) COMMENT '性别'
                            ) COMMENT '用户表';

                        展示
                            show tables;
                            desc tb_user;
                            show create table tb_user; 



                    DECIMAL
                        精度：数字多少位
                        标度：小数后多少位

                    无符号年龄数：age TINYINT UNSIGNED
                    score double(4,1)：4表示整体长度，1表示小数位

                    char(10)：存一个字符也占十个字符的空间，其他用空格补充，性能更好
                        性别 gender char(1)

                    varchar(10)：存几个字符就占几个字符的空间，性能更差
                        如用户名 username varchar(50)


                    birthday：date

                案例
                        create table emp(                                                                                                             id int comment '编号'，                                                                                workno varchar(10) comment ‘工号’,                                                                         name varchar(10) comment ‘姓名’,                                                                          gender char(1) comment ‘性别’ ,                                                                              age tinyint unsigned coment ‘年龄’,                                                                          idcard char(18)comment ‘身份证号’，                                                                   entrydate datecomment ‘入职时间‘ ）                                                                  comment '员工表';



                表操作-修改&删除
                    添加字段：ALTER TABLE 表名 ADD 字段名 类型(长度) [COMMENT 注释] [约束];
                        alter table emp add nickname varchar(20) comment '昵称';

                    修改数据类型：ALTER TABLE 表名 MODIFY 字段名 新数据类型(长度);
                    修改字段名和字段类型：ALTER TABLE 表名 CHANGE 旧字段名 新字段名 类型(长度) [COMMENT 注释] [约束];
                         alter table emp change nickname username varchar(30) comment '用户名';

                    删除字段：ALTER TABLE 表名 DROP 字段名;
                         alter table emp drop username;

                    修改表名：ALTER TABLE 表名 RENAME TO 新表名
                         alter table emp rename to employee;

                    删除表：DROP TABLE [IF EXISTS] 表名;
                    删除表，并重新创建该表：TRUNCATE TABLE 表名;


            MySQL图形化界面

            DML：数据库操作语言
                用来对数据库中表的数据记录进行增删改操作

                添加数据 （INSERT）
                    指定字段：INSERT INTO 表名 (字段名1, 字段名2, ...) VALUES (值1, 值2, ...);
                    全部字段：INSERT INTO 表名 VALUES (值1, 值2, ...);
                    批量添加数据：
                        指定字段：INSERT INTO 表名 (字段名1, 字段名2, ...) VALUES (值1, 值2, ...), (值1, 值2, ...), (值1, 值2, ...);
                        所有字段：INSERT INTO 表名 VALUES (值1, 值2, ...), (值1, 值2, ...), (值1, 值2, ...);


                修改数据（UPDATE）
                    修改数据：UPDATE 表名 SET 字段名1 = 值1, 字段名2 = 值2, ... [ WHERE 条件 ];

                删除数据（DELETE）

            DQL：数据库查询语言
            DCL：数据库控制语言

###        3、函数
###        4、约束
###        5、多表查询
###        6、事务


