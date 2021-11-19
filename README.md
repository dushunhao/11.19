#define _CRT_SECURE_NO_WARNINGS

#include <stdio.h>


struct B

{

	char c;
	short s;
	double d;
};
struct Stu

{

	//成员变量
	struct B sb;
	char name[20];
	int age;
	char id[20];
}s1,s2;//s1,s2也是结构体变量
//s1,s2是全局变量

int main()

{

	struct Stu s;//s是局部变量
	//初始化
	struct Stu s = { {'w',20,3.14},"张三",30,"20200534" };
	struct Stu* ps = &s;
	printf("%c\n", (*ps).sb.c);
	printf("%f\n", (*ps).sb.d);
	printf("%s", (*ps).name);

	return 0;
}



void print1(struct Stu t)

{

	printf("%c %d %.2lf %s %d %s\n", t.sb.c, t.sb.s, t.sb.d, t.name, t.age, t.id);
}
void print2(struct Stu* ps)

{

	printf("%c %d %.2lf %s %d %s\n", ps->sb.c, (*ps).sb.s, (*ps).sb.d, (*ps).name, (*ps).age, (*ps).id);
}
int main()

{

	//struct Stu s;//s是局部变量，初始化
	struct Stu s = { {'w',20,3.14},"张三",30,"20200534" };

	//写一个函数，打印s的内容
	print1(s);//传值调用，要浪费一部分空间来接收传过去的值，也浪费时间
	print2(&s);//传址调用，效率高

	return 0;

}

//函数调用的参数压栈：
//栈，是一种数据结构
//先进的后出，后进的先出


int main(void)

{

	//char c1 = 'a', c2 = 'b', c3, c4;
	//int a = 12, b = 15, c;
	//scanf("%c%c%d", &c3, &c4, &c);
	//printf("a%cb%c\n", c1, c2);
	//printf("a=%d%%,b=%d%%\n", a, b);
	//printf("%-2c%-2c%5d\n", c3, c4, c);
	int a = 0;
	int b = 0;
	int c = 0;
	scanf("%2d%3d%4d", &a, &b, &c);
	printf("%d %d %d", a, b, c);

	return 0;

}

#include<assert.h>

void my_strcpy(char* dest, const char* src)

{

	assert(dest != NULL && src != NULL);//断言
	while (*dest++ = *src++)
	{
		;
	}
}
int main()

{

	char arr1[20] = "xxxxxxxxxx";
	char arr2[] = "hello";
	my_strcpy(arr1, arr2);//1.目标空间的起始地址 2.源空间的起始地址
	printf("%s\n", arr1);

	return 0;

}

int main()

{

	//const 修饰变量，这个变量就被称为常变量，不能被修改，但是本质上还是变量
	const int num = 10;

	//const int* p = &num;
	//int n=100;
	//*p = 20;
	//p = &n;
	//const 修饰指针变量的时候
	//      如果放在*的左边，修饰的是*p，表示指针指向的内容，是不能通过指针来改变的
	//      但是指针本身是可以修改的  

	//int* const p = &num;
	//int n=100;
	//*p = 20;
	//p = &n;
	//const 修饰指针变量的时候
	//      如果放在*的右边，修饰的是指针变量p，表示指针变量不能被改变
	//      但是指针指向的内容是可以修改的

	printf("%d ", num);

	return 0;

}
