```c
#include<stdio.h>
#include<string.h>

int main(void)
{
    char a[81];
    char b[27]="abcdefghijklmnopqrstuvwxyz";
    int i,j,n,len;
    scanf("%s",a);
    for(i=0;i<26;i++)
    {
        for(j=0;a[j]!='\0';j++)
        {
            if(b[i]==a[j])
            {
                for(n=j;a[n]!='\0';n++)
                {
                    a[n]=a[n+1];    
                }
                len=strlen(a);
                n--;
                j--;
                i=0;
            }
        }
    }
    len=strlen(a);
    printf("%d\n",len);
    printf("%s\n",a);
    return 0;
} 
```

```c

#include<stdio.h>
int main(void)
{
    int arr[100]={0};
    int i=1,j,b,box;
    scanf("%d",&b);
    do
    {
        scanf("%d",&arr[i]);
        i++;
    }while(getchar()!='\n');
    for(i=1;i<=b;i++)
    {
        for(j=1;j<=b-i;j++)
        {
            if(arr[j]>arr[j+1])
            {
                box=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=box;                
            }
        }
    }
    for(i=1;i<=b;i++)
    {
        printf("%d",arr[i]);
        if(arr[i+1]!=0){printf(" ");}
    }
    return 0;
}


```

```c
#include<stdio.h>
int main(void)
{
    double a,b,c=1;
    double m=1,n=1,j=1,k=3;
    double pi;
    for(a=1;a>=1e-6;)
    {
        m=m*j;
        n=n*k;
        a=m/n;
        j++;
        k=k+2;
        c=c+a;
    }
    pi=c*2.000000-0.000001;
    printf("%.6lf",pi);
}
```

```c
#include<stdio.h>
int main()
{
   int i,n,j,temp;
   scanf("%d",&n);
   int arr[n];
   for(i=0;i<n;i++)
   {
       scanf("%d",&arr[i]);
   }
   for(i=1;i<n;i++)
   {
       for(j=n-1;j>=i;j--)
       {
           if(arr[j]<arr[j-1])
           {
               temp=arr[j-1];
               arr[j-1]=arr[j];
               arr[j]=temp;
           }
       }
   }
   for(i=0;i<n;i++)
   {
       printf("%d ",arr[i]);
   }
   return 0;
}
```

```c
#include<stdio.h>
int main(void)
{
    int a,i,sum=0,sum2=0,box,a1;
    for(a=1;a<3000;a++)
    {
        sum=0;
        sum2=0;
        
        for(i=1;i<a;i++)
        {
            if(a%i==0)
            {
                sum=sum+i;
            }
        }
        for(i=1;i<sum;i++)
        {
            if(sum%i==0)
            {
                sum2=sum2+i;
            }
        }
        a1=a;
        if(sum2==a&&a!=sum)
        {
            if(a>sum)
            {
               box=a1;
               a1=sum;
               sum=box;
            }
            printf("%d %d\n",a1,sum);
            a=sum+1;
        }
    }
    return 0;
}
```

```c
#include<stdio.h>
typedef struct student{
    char name[21];
    int arr[21];
    int sum;
}good;

int main(void)
{
    int a,i,b,j;
    good goods[10];
    scanf("%d",&a);
    for(i=1;i<=a;i++)
    {
        scanf("%s",goods[i].name);
    }
    scanf("%d",&b);
    for(i=1;i<=a*b;i++)
    {
        scanf("%d %s",&goods[i].arr,goods[i].name);
    }




    return 0;
}
```

```c
#include<stdio.h>
#include<string.h>
int main(void)
{
    int i,a,len,j,a1=0,a2=0,a3=0,a4=0,sum[10];
    char arr[10][17];
    scanf("%d",&a);
    for(i=0;i<a;i++)
    {
        scanf("%s",&arr[i]);
        len=strlen(arr[i]);
        for(j=0;j<len;j++)
        {         
            if(arr[i][j]<='Z'&&arr[i][j]>='A')
            {
                a1=1;

            }
            if(arr[i][j]<='z'&&arr[i][j]>='a')
            {
                a2=1;

            }            
            if(arr[i][j]>='0'&&arr[i][j]<='9')
            {
                a3=1;
 
            }
            if(arr[i][j]=='~'||arr[i][j]=='!'||arr[i][j]=='@'||arr[i][j]=='#'||arr[i][j]=='$'||arr[i][j]=='%'||arr[i][j]=='^')
            {
                a4=1; 

            }

        }            
        sum[i]=a1+a2+a3+a4;
        if(len<8||len>16)
        {  
            sum[i]=0;
        }
        a1=0,a2=0,a3=0,a4=0;
    }

    for(i=0;i<a;i++)
    {
        if(sum[i]>=3)
        {
           printf("YES\n");
        }
        else{printf("NO\n");}    
    }
    return 0;

}
```

```c
#include<stdio.h>
#include<string.h>
int main(void)
{
    int M,len,i;
    int a,b,c,d,sum;
    char x[51];
    scanf("%d",&M);
    do
    {
        a=0,b=0,c=0,d=0;
        scanf("%s",x);
        len=strlen(x);
        if(len<8||len>16)
            printf("NO\n");
        else
        {
            for(i=0;i<len;i++)
            { if(x[i]>='A'&&x[i]<='Z')
                    b=1;
                else if(x[i]>='a'&&x[i]<='z')
                    a=1;
               
                else if(x[i]>='0'&&x[i]<='9')
                    c=1;
                else d=1;
            }
            sum=a+b+c+d;
            if(sum>2)
                printf("YES\n");
            else  printf("NO\n");
        }
   M--;
    }while(M>0);
    return 0;
}

```

```c
#include <stdio.h>
#include <math.h>

int main()
{
    int n;
    long long int m;
    while (scanf("%d", &n) != EOF) {
        m = 1;
        m = pow(-1, n) * 3 + pow(3, n);
        printf("%lld\n", m);
    }
    return 0;
}
```

```c
#include <stdio.h>
#include <math.h>

int main()
{
    int a;
    int b;
    while (scanf("%d", &a) != EOF) {
        if(a==2){printf("12\n");}
        if(a==3){printf("24\n");}
        if(a>3){
            b= pow(-1.0,a)*3+pow(3.0,a);
            printf("%lld\n",b);
        }
    }
    return 0;
}
```

```c
#include <stdio.h>
#include <math.h>

int main()
{
    int a;
    int b;
    while (scanf("%d", &a) != EOF) {
        if(a==2){printf("12\n");}
        if(a==3){printf("24\n");}
        if(a>3){
            b= pow(-1.0,a)*3+pow(3.0,a);
            printf("%lld\n",b);
        }
    }
    return 0;
}
```

