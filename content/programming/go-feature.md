+++
title = "Go语言特性"
description = ""
date = 2021-08-29T13:23:24+08:00
draft = false
toc = true
categories = [
  "编程开发"
]
tags = [
  "Golang"
]
images = []
+++


#### slice
- 每个切片都指向一个底层数组
- 每个切片都保存了当前切片的长度、底层数组可用容量
- 使用len()计算切片长度时间复杂度为O(1)，不需要遍历切片
- 使用cap()计算切片容量时间复杂度为O(1)，不需要遍历切片
- 通过函数传递切片时，不会拷贝整个切片，因为切片本身只是个结构体而矣
- 使用append()向切片追加元素时有可能触发扩容，扩容后将会生成新的切片

#### map
- map是并发不安全的
- map遍历的顺序不固定
- 从map读取一个不存在的key将不会引起panic

#### chan
- 关闭值为nil的channel会引发panic
- 关闭值为nil的channel会引发panic
- 向已经关闭的channel或者nil的channel写数据会引发panic
- 可以从关闭的channel中读数据

#### iota
- iota在const关键字出现时被重置为0
- const声明块中每新增一行iota值自增1

简单理解：iota代表了const声明块的行索引（下标从0开始）

#### defer
- defer定义的延迟函数参数在defer语句出时就已经确定下来了
- defer定义顺序与实际执行顺序相反
- defer可以改变return返回值，执行过程是: 保存返回值(若有)—>执行 defer（若有）—>执行ret跳转
- 申请资源后立即使用defer关闭资源是好习惯

#### select
- select语句中除default外，每个case操作一个channel，要么读要么写
- select语句中除default外，各case执行顺序是随机的
- select语句中如果没有default语句，则会阻塞等待任一case
- select语句中读操作要判断是否成功读取，关闭的channel也可以读

#### recover
 recover必须在defer中执行，并且不能在defer嵌套函数中
这样可以
```
func main(){
	defer func ()  {
		err:=recover()
	}()
	panic("some exception")
}

```
嵌套不可以
```
func main(){
	defer func ()  {
		func(){
            err:=recover()
        }
	}()
	panic("some exception")
}

```

#### for range
for range语句可以遍历数组、slice、map、chan
- 遍历slice时，循环内可以改变切片的长度，不影响循环次数，循环次效在循环开始前就已经确定了
- 遍历chan时，chan关闭后会退出循环；如果channel中没有数据，可能会阻塞
- 遍历map时，遍历的顺序不固定，是随机的，循环内插入的数据不一定能遍历到，最好不要在遍历时对map进行写操作
- 使用index,value接收range返回值会发生一次数据拷贝，遍历过程中可以适情况放弃接收index或value，可以一定程度上提升性能。数组、slice可以放弃value，避免value拷贝。

#### Golang中的引用类型
- 切片
- map
- channel
- interface

#### Golang中的指针运算
- 可以通过“&”取指针的地址
- 可以通过“*”取指针指向的数据

#### Golang main函数
- main函数不能带参数
- main函数不能定义返回值
- main函数所在的包必须为main包
- main函数中可以使用flag包来获取和解析命令行参数
