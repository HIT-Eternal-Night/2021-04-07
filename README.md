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

