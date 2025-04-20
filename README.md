# 嵌入式C语言自我修养
##    第1章 工欲善其事必先利其器
###        1、Vim
            安装
                apt-get insall vim
                sudo apt-get install vim

            vim --version
            工作模式
                普通模式
                插入模式
                命令行模式
                可视化模式
                替换模式


###        2、make
            make/make clean

###        3、gcc
            安装
                apt-get install gcc
                apt-get install gcc-arm-linux-gnueabi

            gcc -v
            gcc -o hello main.c

###        4、Git
            apt-get install git
            通过配置信息联系
                git config --global user.email 1197023948@qq.com
                git config --global user.name "litao.wang"



##    第2章 计算机体系结构与CPU工作原理
        CPU性能提升：Cache机制
        CPU性能提升：流水线
        多核CPU
            GPU
            DSP
            FPGA
            TPU
            NPU
            CPU

        总线与地址
            地址
                地址的本质是由CPU管脚发出的一组地址控制信号

            总线
                总线编址方式
                    统一编址
                    独立编址



        指令集与微架构
            指令集
                指令的分发、预取、解码、执行、写回
                操作数的类型、存储、存取、旁路转移
                Load/Store架构
                寄存器
                地址的格式、大端模式、小端模式
                字节对齐、边界对齐

            微架构：CPU内核
                SoC



##    第3章 ARM体系结构与汇编语言
        ARM体系架构
            工作模式
                User mode
                FIQ mode
                IRQ mode
                Supervisor mode
                Abort mode
                Undefined mode
                System mode
                Monitor mode

            CPSR
            SPSR

        ARM汇编指令
            存储访问
                LDR/STR
                LDM/STM
                LDMFD/STMFD

            数据传送
                MOV/MVN

            算术逻辑运算指令
                ADD：加法
                ADC：带进位加法
                SUB：减法
                AND：逻辑与运算
                ORR：逻辑或运算
                EOR：异或运算
                BIC：位清除指令

            操作数：operand2
                ASR
                LSL
                LSR
                ROR
                RRX

            比较指令
                CMP {cond} Rn, operand2：比较两个数大小
                CMN {cond} Rn, operand2：取负比较

            条件执行指令
            跳转指令
                B
                BL
                BX
                BLX


        ARM寻址方式
            寄存器寻址
            立即数寻址
            寄存器偏移寻址
            寄存器间接寻址
            基址寻址
            多寄存器寻址
            相对寻址

        ARM伪指令
            LDR伪指令
            ADR伪指令

        AMR汇编程序设计
            ARM汇编程序格式

            符号与标号
                %、F、B、A、T、N、routename

            伪操作
                AREA定义段
                GBLA定义数据
                ENTRY指定汇编程序的执行入口


        C语言和汇编语言混合编程
            ATPCS规则：定义了ARM子程序调用的基本规则及堆栈的使用约定
            在C程序中内嵌汇编代码
            在汇编程序中调用C程序

        GNU ARM汇编语言
            编译器分类
                IDE内部集成ARM编译期
                使用开源的GNU GCC for ARM编译期

            重新认识编译器

            GNU ARM 编译期的伪操作

            GNU ARM 汇编语言中的标号
                _start作为汇编程序的入口

            .section伪操作
                readelf命令查看系统预留的段名
                .text：代码段
                .data：数据段
                .bss：BSS段
                .rodata：只读数据段

            基本数据格式
                小圆点.表示当前指令的地址

            数据定义
                .float 3.14
                    使用.float伪操作定义一个浮点数f，初始化位3.14

                .equ f，3.1415
                    重新赋值为3.1415


            汇编代码分析实战


##    第4章 程序的编译、链接、安装和运行
        从源程序到二进制文件
            arm-linux-gnueabi-gcc -o a.out main.c sub.c得到二进制文件a.out
            readelf -h a.out查看二进制文件
            查看可执行文件a.out的section header代码：readelf -S a.out

        预处理过程
            头文件实现模块化编程
            #pragma预处理命令完成一些特定的动作
            预处理的操作
                头文件展开
                宏展开
                条件编译
                删除注释
                添加行号和文件名标识
                保留#pragma命令

            将输出的信息重定向到main.i文件：arm-linux-gnueabi-gcc -E main.c > main.i

        程序的编译
            从C文件到编译文件
            汇编过程
            符号表语重定位表

        链接过程
            分组组装
            符号决议
            重定位

        程序的安装
            程序安装的本质
            在Linux下制作软件安装包
            使用apt-get在线安装软件
            在windows下制作软件安装包

        程序的运行
            操作系统环境下的程序运行
            裸机环境下的程序运行
            程序入口main()函数分析
            BSS段的小秘密

        链接静态库
        动态链接
            与地址无关的代码
            全局偏移表
            延迟绑定
            共享库

        插件的工作原理
        Linux内核模块运行机制
        Linux内核编译和启动分析
        U-boot重定位分析
        常用的binutils工具集


