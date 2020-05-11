

```c
#include <stdio.h>

int main(void) 
{
    /*
            1   2   3   4   5
           18  19  20  21   6
           17  28  29  22   7
           16  27  30  23   8
           15  26  25  24   9
           14  13  12  11  10
    */ 
    int arr[5][5] = {0};
    int num = 1;
    int x, y;
    int i, j;

    x = 0;
    y = -1;

    while (num <= 25) {
        // 从左往右
        while (y+1 < 5 && arr[x][y+1]==0) {  arr[x][++y] = num++;  }
        // 从上往下
        while (x+1 < 5 && arr[x+1][y]==0) {  arr[++x][y] = num++;  }
        // 从右往左
        while (y-1 > -1 && arr[x][y-1]==0) {  arr[x][--y] = num++; }
        // 从下往上
        while (x-1 > -1 && arr[x-1][y]==0) { arr[--x][y] = num++;  }
    }

    for (i=0; i<5; i++) {
        for (j=0; j<5; j++) {
            printf("%2d ", arr[i][j]);
        }
        printf("\n");
    }

    return 0;
}
```
```c
#include <stdio.h>
int main (void)
{
/*一个正整数数如果恰好等于它的因子之和，这个数就称为“完数”。
例如，6的因子为1、2、3，而6=1+2+3，因此6是“完数”。
编程序找出10000以内的所有的“完数”。*/
    int i,j,sum=0; 
    int n=1,arr[10000]={0};
    int m=0,h;
    for(i=1;i<=10000;i++)
    {
        
        for(j=1;j<n;j++)
        {
            if(n%j==0)
            {               
                sum = sum + j;
                arr[m]=j;
                m++;
            }
            
        }
            if( n == sum )
            {
                printf( "%d" ,n );
                printf(":");
                for(m=0;m<=100;m++)
                {
                    if(arr[m]!=0&&n%arr[m]==0)
                    {printf("%d ",arr[m]);}
                   
                }
                printf("\n");
            }
        m=0;    
        n++;
        sum=0;        
    }
    return 0;
}
```

```c
/*编一个程序，输入100个学生的百分制成绩，输出相应的五分制成绩。
成绩为[0,100]之间的正整数，成绩映射关系如下：
[90, 100] : A
[80, 89] : B
[70, 79] : C
[60, 69] : D
[0, 59] : E*/
#include<stdio.h>
int main (void)
{
    int i,a,m=0,arr[99]={0};
    char c[99]={0},j=0;
    for(i=1;i<=100;i++)
    {
        scanf("%d",&a);
        arr[m]=a;
        m++;
    }
    for(m=0;m<=99;m++)
    {
        if(arr[m]>=90&&arr[m]<=100){c[j]='A';j++;}
        if(arr[m]>=80&&arr[m]<=89){c[j]='B';j++;}
        if(arr[m]>=70&&arr[m]<=79){c[j]='C';j++;}
        if(arr[m]>=60&&arr[m]<=69){c[j]='D';j++;}
        if(arr[m]>=0&&arr[m]<=59){c[j]='E';j++;}
    }
    for(j=0;j<=99;j++)
    {
        printf("%c\n",c[j]);
    }
    return 0;
}
```

```c
#include <stdio.h>
#include <math.h>
int main(void)
{
    int a,n,box=0;
    int i,sum=0;
    double m;
    scanf("%d %d",&a,&n);
    for(i=1;i<=n;i++)
    {
        m=i-1;
        box=box+pow(10,m);
        sum=sum+a*box;
    }
    printf("%d",sum);
    return;
}
/* 2 3
sum=2+22+222
   =2*1+2*11+2*111
   =2*1+2*(1+10)+2*(1+10+100)*/
```

```c
#include <stdio.h>
int main(void)
{
    int i,s,e,j;
    scanf("%d %d",&s,&e);
    for(i=s;i<=e;i++)
    {
        for(j=1;j<=i;j++)
        {
            if(i!=1&&j!=1&&i!=j&&i%j==0){break;}
            if(i==j){printf("%d ",i);}
        }
    }
    return;
}

```

```c
#include <stdio.h>
int main(void)
{
    int arr[6][6]={0};//解决了内存溢出的问题
    int i,j,max=0;
    for(j=0;j<=5;j++)
    {     
        scanf("%d %d %d %d %d %d",&arr[0][j],&arr[1][j],&arr[2][j],&arr[3][j],&arr[4][j],&arr[5][j]);      
    }
    max=arr[1][1];
    for(j=0;j<=5;j++)
    {
        for(i=0;i<=5;i++)
        {
            if(max<arr[i][j]){max=arr[i][j];}
        }
    }
     for(j=0;j<=5;j++)
    {
        for(i=0;i<=5;i++)
        {
            if(max == arr[i][j]){printf("%d %d",j,i);break;}
        }
    }
   
    return;
}
```

