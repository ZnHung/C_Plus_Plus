# 第一，二，三章，C++简介，数据类型，选择结构，循环结构

参考视频：
清华大学-郑莉-C++语言程序设计
https://www.bilibili.com/video/BV1PA411b75a?p=2&amp;spm_id_from=pageDriver



## 预定义的插入符和提取符

### 插入符

“<<”是预定义的插入符，作用是在流类对象cout上面便可以实现向标准输出设备输出

```
cout<<表达式<<表达式;
```

### 提取符

“>>”提取符可以连续写多个，每个后面跟着一个表达式，该表达式通常是用于存放输入值的变量

```
cin>>表达式>>表达式;
```

例如：

```
int a,b;
cin>>a>>b;   //从键盘中依次提取数据，分别放到变量a,b之中
```

## 常用的I/O流类操纵符

| 操纵符名(操纵算子) | 含义                                                 |
| ------------------ | ---------------------------------------------------- |
| dec                | 设置数值数据采用十进制表示                           |
| hex                | 设置数值数据采用十六进制表示                         |
| oct                | 设置数值数据采用八进制表示                           |
| ws                 | 提取空白符                                           |
| endl               | 插入换行符并且刷新流                                 |
| ends               | 插入空字符                                           |
| setprecision(int)  | 设置浮点数的小数的位数（包括小数点），也就是设置精度 |
| setw(int)          | 设置域宽，设置占用几个字符的位置                     |

例如：[清华大学-郑莉-C++语言程序设计]: https://www.bilibili.com/video/BV1PA411b75a?p=2&amp;spm_id_from=pageDriver

```
cout<<setw(5)<<setprecision(3)<<3.1415
```

#### 例题；if选择在C++中的实现

```
#include<iostream>
using namespace std;

int main()
{
	int x, y;
	cout << "please enter 2 number :" << "\n";
	cin >> x >> y;
	if (x != y)
	{
		if (x > y)
		{
			cout << "the max is:" << x<<"\n";
		}
		else
		{
			cout << "the max is :" << y<<"\n";
		}
	}
	else
		cout << "x = y"<<"\n";

	return 0;
}
```

#### 例题；switch选择在C++中的实现

```
#include<iostream>
using namespace std;

int main()
{
	int day;
	cout << "please enter a number :" << "\n";
	cin >> day;
	switch (day)
	{
	case 1:cout << "Monday" << endl; break;
	case 2:cout << "Tuesday" <<endl; break;
	case 3:cout << "Wednesday" << endl; break;
	case 4:cout << "Thursday" << endl; break;
	case 5:cout << "Friday" << endl; break;
	case 6:cout << "Saturday" << endl; break;
	case 7:cout << "Sunday" << endl; break;
	default:cout << "Error" << endl; break;
	}
	return 0;
}
```

#### 例题；while循环在C++中的实现

```
#include<iostream>
using namespace std;
int main()
{
	int i = 1, sum = 0;
	while (i <= 10)
	{
		sum = sum + i;
		i++;
	}
	cout << "sum=" << sum << endl;
	return 0;
}
```

#### 例题：for循环在C++中的实现

```
#include<iostream>
using namespace std;
int main()
{
	int i = 1, sum = 0;
	int n;
	cout << "enter n :" << endl;
	cin >> n;
	for (i = 1; i <= n; i++)
	{
		sum = sum + i;
	}
	cout << "sum = " << sum << endl;
	return 0;
}
```

#### 例题：do....while循环在C++中的实现

```
#include<iostream>
using namespace std;
int main()
{
	int num, right_digit, new_num;
	cout << "enter a number :" << endl;
	cin >> num;
	do {
		right_digit = num % 10;
		cout << right_digit;
		num = num / 10;
	} while (num != 0);
	cout << endl;
	return 0;
}
```

```
#include<iostream>
using namespace std;
int main()
{
	int i=1, sum = 0,n;
	cout << "enter n :" << endl;
	cin >> n;
	do {
		sum = sum + i;
		i++;
	} while (i <= n);
	cout << "sum =" << sum << endl;
	return 0;
}
```

## C++中的类型别名：

#### typedef

```
typedef 已有类型名 新的类型名；
typedef int zhengshu;
```

#### using

```
using 新类型名=已有类型名；
using zhengshu=int;
```

### 枚举类型(不限定作用域的枚举类型)

```
enum Weekday
{SUN,MON,TUE,WED,THU,FRI,SAT}
```

### auto类型

编译器通过初始值来自动推断变量的类型

```
auto val = val1 + val2
//若val1+val2是int类型，则被初始化的val是int类型
//若val1+val2是double类型，则被初始化的val是double类型
```

### decltype类型

当希望定义一个变量与另一个表达式类型相同时，可以使用decltype来定义，是这个变量和另一个变量具有同样的类型。

```
decltype (i)j=2;
//定义变量j，使得j和i具有同样的数据类型。
```

### 章节例题：

**例题1：使用循环语句，求自然数1~10的和**

```
//do....while 循环
#include<iostream>
using namespace std;
int main()
{
	int i=1,sum=0;
	do{
		sum=sum+i;
		i++;
	}while(i<=10);
	cout<<"sum = "<<sum<<endl;
	return 0;
} 
```

```
//for循环
#include<iostream>
using namespace std;
int main()
{
	int i=1,sum=0;
	for(i=1;i<=10;i++)
	{
		sum=sum+i;
	}
	cout<<"sum = "<<sum<<endl;
	return 0;
} 
```

**例题2，计算图形的面积**

计算圆形，长方形，正方形的面积，在运行的时候先提示用户选择图形的类型，然后对圆形要求用户输入半径的值，对长方形要求用户输入长和宽的值，对正方形要求用户输入边长的值，计算出面积之后将其显示出来。

```
#include<iostream>
using namespace std;
int main()
{
	int itype;		//用来标记图形的类型
	float radius,length,width,square;
	cout<<"please choose the type of the graph:(1:circle,  2:rectangle,  3:square)" <<endl;
	cin>>itype;
	switch(itype)
	{
		case 1:
			cout<<"please enter the radius:"<<endl;
			cin>>radius;
			cout<<"area = "<<3.14*radius*radius<<endl;
			break;
		case 2:
			cout<<"please enter the length and width:"<<endl;
			cin>>length>>width;
			cout<<"area = "<<length*width<<endl;
			break;
		case 3:
			cout<<"please enter the sqare:"<<endl;
			cin>>square;
			cout<<"area = "<<square*square<<endl;
			break;
		default:
			cout<<"Error! please enter 1, 2 or 3"<<endl;
			break;				
	}
	return 0;
}
```

**例题3：声明一个表示时间的结构体**

提示用户输入年、月、日、小时、分、秒；

精确的表示年、月、日、小时、分、秒，然后完整的进行输出。

```
#include<iostream>
using namespace std;
struct Date{
	unsigned int year;
	unsigned int month;
	unsigned int day;
	
	unsigned int hour;
	unsigned int min;
	unsigned int sec;
};

int main()
{
	struct Date Time = {2021,4,9,21,18,00};
	
	cout<<"please enter the year:"<<endl;
	cin>>Time.year;
	
	cout<<"please enter the month:"<<endl;
	cin>>Time.month;
	
	cout<<"please enter the day:"<<endl;
	cin>>Time.day;
	
	cout<<"please enter the hour:"<<endl;
	cin>>Time.hour;
	
	cout<<"please enter the min:"<<endl;
	cin>>Time.min;
	
	cout<<"please enter the sec:"<<endl;
	cin>>Time.sec;
	
	cout<<"NOW!  The time is : "<<Time.year<<"/"
								<<Time.month<<"/"
								<<Time.day<<"\t"
								<<Time.hour<<":"
								<<Time.min<<":"
								<<Time.sec<<endl;
	return 0; 
}
```


