# map使用

+ 声明后必须初始化

>>`testMap := make(map[int]string)`

>>`testMap := map[int]string{}`
+ key一定要是可比较类型，value是任意类型
+ 新增、更新、删除、查询

>>>新增

>>>`testMap[1] = "1"`

>>>删除

>>>`delete(testMap, 1)`

>>>更新

>>>`testMap[1] = "2"`

>>>查找

>>>`value, isExist := testMap[1]`

+ 遍历，golang的map底层是哈希表，所以是无序的

>>`for k,v := range testMap {}`

+ 函数传参，golang中是没有引用传递的，都是值传递，map本身是引用类型，作为形参或者返回参数的时候，传递的是值的拷贝，值为地址

+ 并发map：sync.Map
>>原理：sync.Map里头有两个map一个是专门用于读的read map，另一个是才是提供读写的dirty map；优先读read map，若不存在则加锁穿透读dirty map，同时记录一个未从read map读到的计数，当计数到达一定值，就将read map用dirty map进行覆盖。

