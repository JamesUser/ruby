# ruby
ruby学习笔记
Ruby笔记：

一、注释
注释符为#,多行注释为
=begin
多行注释
多行注释
=end

注意ruby中语法大小写敏感

二、数据类型
1.ruby的数据类型有Number、String、Ranges、Symbols,以及true、false、nil这几个特殊值
2.ruby的数据结果有Array和Hash

3.Number数据类型包括整型和浮点型
整型数据可以在前面加先导词定义进制，0代表八进制，0x代表十六进制,0b代表二进制，例如：a=0377;a=0xff;a=0b11
浮点型,例如：a=1.2

运算符有+-*/,特殊的指数运算符为**

4.字符串
ruby中字符串类型有单引号和双引号表示,双引号允许替换变量及转义,单引号不允许替换变量且只能允许\\及\'转义
例如：puts 'this\'s a gun\\' 运行结果为this's a gun\

可以使用#{}替换ruby表达式的值,例如：
#!/usr/bin/ruby

#coding:UTF-8


name="hello"

puts "乘积:#{24*60*60}"

puts "#{name+",world"}"


=begin

输出结果为

86400

hello,world

=end

end

5.数组Array
ruby中数组Array通过[]定义,以逗号","区别数据,数组内数据可以是不同的数据类型。例如:

#!/usr/bin/ruby

#-*- coding:UTF-8 -*-

ary=["hello","world",10,24,]

end


6.Hash类型
ruby中的Hash数据类型是通过多个键值对组成的集合,每组键值对用逗号","隔开,键值对之间用=>隔开,例如：

#!/usr/bin/ruby

hah=color={"red"=>0xf00,"green"=>0x0f0,"blue"=>0x00f}

end


7.范围range数据类型
范围通过一个开始值和一个结束值表示，有三种表示形式：..	...	Range.new
使用..构造的范围包含结束值，而使用...构造的范围不包含结束值
范围当做迭代器使用时会返回序列的每个值，例如：
#!/usr/bin/ruby
(1..5).each do |n|
	print n,' '
end

以上程序执行结果为

1 2 3 4 5
