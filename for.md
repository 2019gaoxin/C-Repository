```c
         
```

```c++

#include <stdio.h>
//第一题 高昕2019012472
int main(void)
{
    int a;
    int x,k,i;

    printf("请输入行数\n");
    scanf("%d",&a);
    x=2*a-1;    
    for (i=1;i<=a;i++)
    {
        for(x=1;x<=i-1 ;x++)
        {
            printf(" ");
        }
        for(k=1;k<=2*a-2*i+1;k++)
        {
            printf("*");
        }
        printf("\n");
    }            
    return 0;
}
```

```c
#include <stdio.h>
//第二题 高昕2019012472
int main(void)
{
    int a=1,i,sum=0;
    int x=2,m;
    printf("请输入n的值：");
    scanf("%d",&a);
    for(i=2;i<=a;i++)
    {
        //素数求和，先判断素数
        for(m=2;m<=x;m++)//x是要判断的素数
        {

            if(m==x)
            {
                sum = sum + x;
                break;
            }
            if(x%m==0)
            {
                //不是素数
                break;
            }
            if(m==x-1)
            {
                sum = sum + x;
                break;
            }
            else
            {
                //printf("不是素数");
            }             
        }
        x++;       
    }
    printf("2~%d的素数和为%d\n",a,sum);
    return 0;
}
```

```c
#include <stdio.h>
//第三题 高昕2019012472
int main(void)
{
    int i,n;
    double m=0,sum1=0,sum2=0,h;
    scanf("%d",&n);
    for(i=1;i<=n;i++)
    {
       m++;
       sum1=sum1+m;
       sum2=sum2+1/sum1;
       
    }
    printf("%lf",sum2);
    return;
}
```

