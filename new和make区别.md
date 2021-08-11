# new和make的区别

## new
GO提供了内建函数new

`func new(type) *Type`
+ 只接口一个参数，参数是类型，分配好内存后，返回一个指向该类型内存地址的指针
+ 分配的内存置为零

## make

`func make(t Type, size ...IntegerType) Type`
+ make用于chan、map、slice的内存创建
+ 返回类型就是以上三个类型本身，并不是指针类型，这三种本身就是引用类型
+ 这三种类型是引用类型，所以必须初始化，但不是置为零值

## make和new的区别
+ 均是在堆上内存分配
+ make只用于slice、map、channel的初始化（非零值），new用于类型的内存分配（内存置为零）
+ make返回的是这三个引用类型本身，new返回的是指向类型的指针
+ new不常用，一般均是直接使用如下方式new

`t:= test{}`

`t:= &test{}`
