# 2021-04-07
复习所学，一步一回头。

1、最大公约数：
方法一、穷举法
#include<stdio.h>

int main(int argc,char const *argv[])
{
	int a,b;
	scanf("%d %d",&a,&b);

	int gcd = 0;
	int i;
	for(i=1 ; i<=a && i<=b ; i++)
	{
		if(a % i == 0)
		{
			if(b % i == 0)
			{
				gcd = i;
			}
		}
	}
	
	printf("%d和%d的最大公约数是%d",a,b,gcd);
	return 0; 
}

方法二、辗转相除法
#include<stdio.h>

int main(int argc,char const *argv[])
{
	int a,b;
	int temp;
	scanf("%d %d",&a,&b);
	
	while (b != 0)
	{
		temp = a % b;
		a = b;
		b = temp;
	}
	
  printf("gcd=%d\n",a);	
	return 0;
}

2、最小公倍数
下面直接给出函数体
int LCM(int a, int b)
{
	int i;
	for (i=a>b?a:b ; ; i++)
	{
		if (i%a == 0 && i%b == 0)
		return i;
	} 
}

3、正序输出整数的思路：核心do——while语句
逆序再逆序——适用于末尾不含0的数
先判断位数再做除法——万能

4、逆序输出字符串
#include<stdio.h>
#include<string.h>
#define len 1000

int main(int argc,char const *argv[])
{
	char a[len];
	printf("请输入一个字符串：");
	scanf("%s",a);
	
	int l = strlen(a);				//字符串长度 
	int temp,i;						//中间变量 
	
	for(i=0 ; i<l/2 ; i++)			//中间对折，两头调换！！！切记切记！！ 
	{
		temp = a[i];
		a[i] = a[l-i-1];
		a[l-i-1] = temp;
	}
	
	printf("该字符串逆反后为%s\n",a);
    return 0;
}
