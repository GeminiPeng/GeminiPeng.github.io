---
layout: post
title: "autorelease深度学习"
date: 2018-01-31
description: ""
tag: iOS
---   

### 1.autorelease对象什么时候释放

在没有手加`Autorelease Pool`的情况下，`Autorelease`对象是在当前的`runloop`迭代结束时释放的，而它能够释放的原因是系统在每个`runloop`迭代中都加入了自动释放池`Push`和`Pop`

##### 2.获取字符串长度

>`NSString = @"abcd"; 
>NSUInteger length = [str length]//str.length`

##### 2.根据索引获得单个字符

>`NSString * str = @"www.baidu.com";`
>//如果你给定的索引值超出了字符串的长度,就会导致异常崩溃
>//如果你给入的是一个负数那么获得的值就是一个乱码
>`unichar c = [str characterAtIndex:2];`
>//索引值从0开始

##### 3.根据索引获得字符串的一个子串

>`NSString * str = @"www.baidu.com";`
>//substringFromIndex 从给定的索引开始(包含该索引位置)截取到字符串末尾
>`NSString * tmpStr = [str substringFromIndex:3];`
>//substringToIndex截取字符串到给定索引的位置结束,(不包括改索引位置);
>`NSString : tmpStr = [str substringToIndex:3];`

##### 4.截取字符串的某一段

>`NSRange rang = {4,6};`
>//location(起始索引的位置,包含该索引)length(要截取的长度)
>`NSString * tmpStr = [str substringWithRanger:rang];`

##### 5.获取一个字符串的索引位置

>`NSString * str1 = @"www.baidu.com";
>NSString * str2 = @"it";
>NSRange rang = [str1 rangOfString:str2];`
>//可以使用NSStringFromRange把一个Range结构体转换成字符串
>//NSlog(@"location=%d,length=%d",rang.location,rang.length);
>//NSNotFound 没找到
>`if(rang.location==NSNotFound)
>{
>	NSLog(@"str2不在 str1中")
>}else{
>	NSLog(@"rangOfString%@",NSStringFromRange(rang));
>}`

##### 6.获得一个字符串索引范围

>`NSString * str = @"www.baidu.com";
>NSRange rang= [str rangeOfString:@"baidu" option:NSCaseInsensitiviSearch];
>NSLog(@"rangeOfString%@",NSStringFromRange(rang));`

------

1.判断字符串是否为空

>`NSString * str = @"";
>if(str == nil || str.length==0){
>	NSLog(@"字符串为空");
>}`

2.判断字符串是否已指定的内容开头

>`NSString * str = @"www.github.com";
>BOOL isPrefix = [str hasPrefix:@"xww"];
>NSLog(@"hasPrefix:%@".isPrefix?@"Yes":@"No");`

3.判断字符串是否以指定的内容结尾

>//在开发中常用在判断文件格式
>//.txt .avi .rmvb .mp3 .mp4等
>`NSString * str = @"abcd.mp4";
>BOOL isSuffix = [str hasSuffix:@".mp4"];
>NSLog(@"hasSuffix:%@".isSuffix?@"Yes":@"No");`

4.判断两个字符串是否相等















































































































