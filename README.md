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



三、ruby中的类和变量
ruby中的类定义：

	class User

	end

ruby中的变量有四种：

	1.局部变量，在方法中定义的变量。以小写英文字母或_开头命名
	2.实例变量，实例变量可以跨特定的实例或对象的方法中使用，以@开头命名
	3.类变量，可以跨不同的对象使用，以@@开头命名变量
	4.全局变量，可以跨类使用，以$开头命名变量
	5.常量，大写字母开头
	
*未初始化的变量的值为nil,常量不能定义在方法内，引用一个未初始化的常量会报错
	
例如：

#!/usr/bin/ruby

$global_variable=10	#全局变量

class User	
	
	VAR1=100	#常量
	@@work="teacher"	#类变量
	def initialize(userId,userName,sex)	#局部变量
		@user_id=id
		@user_name=name
		@user_sex=sex			#实例变量
	
	end
	def show
		puts "定义的常量为#{VAR1}"
	end
	
end
	

ruby中通过new创建对象，当需要创建带参数的对象时，类中必须有initialize方法，例如：
user=User.new("001","James","男")

ruby中可以通过def自定义方法，例如：

#!/usr/bin/ruby

$global_variable="James"

class User
		
        def ask
                puts "why?#$global_variable"
        end
end

创建对象调用自定义方法：

user=User.new

user.ask


四、ruby中特殊的运算符

<=>联合比较运算符

	a<=>b

	a等于b时返回0，a大于b时返回1，a小于b时返回-1

.eql?同时比较值和类型
	
	1 == 1.0 返回true
	1.eql?1.0 返回false

equal?比较是否是相同的对象


ruby的并行赋值

	a=10
	b=20
	c=30
可以使用并行赋值，在一条语句中完成赋值
	
	a,b,c = 10,20,30
	
并行赋值在交换两个变量的值很有用处

	a,b = b,c
	
ruby的逻辑运算符

	and 逻辑与，当两个操作数都为真时，结果为真
	or 逻辑或，当两个操作数有一个非零时，结果为真
	&& 逻辑与，当两个操作数都非零，结果为真
	|| 逻辑或，当两个操作数有一个非零，结果为真
	! 逻辑非，逆转条件结果
	not 逻辑非，逆转条件结果
	
	
ruby的三元运算符

	condition？ value1:value2 如果条件为真? 则值为value1：为假值为value2

ruby的defined?运算符

	defined? 判断表达式是否定义，返回表达式的描述字符串，未定义的表达式返回nil，表达式可以是变量、方法
例如：

变量：
	
	foo=10
	$var="var"
	defined? variable #如果variable已定义，返回True
	defined? foo	#返回"local-variable"
	defined? $var	#返回"global_variable"
方法：

	defined? puts	#返回"method"
	defined? puts(bar)	#返回nil，bar没有定义
	defined? show	#返回nil，show方法没有定义
	













