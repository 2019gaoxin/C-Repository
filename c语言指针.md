```c
#include<stdio.h>
#include<string.h>
int main(void)
{
    char str[100],str2[100];
    printf("请输入第一个字符串（长度小于10）\n");
    scanf("%s",str);
    if(strlen(str)>=10)
    {
        printf("输入非法");
        return 0;
    }
    printf("请输入第二个字符串（长度小于10）\n");
    scanf("%s",str2);
    if(strlen(str)>=10)
    {
        printf("输入非法");
        return 0;
    }
    printf("拼接结果为：\n");
    printf("%s\n",strcat(str,str2));
    return 0;
}
```

```c
#include<stdio.h>
int main(void)
{
    //2、定义一个整型数组，然后输入10个元素，然后进行从小到大排序并输出。
    int arr[100]={0},k;
    int i,j,box;
    for(i=0;i<10;i++)
    {
        scanf("%d",&arr[i]);
    }
    for(i=0;i<9;i++)
    {
        for(j=0;j<9;j++)
        {
            if(arr[j]>=arr[j+1])
            {
                box=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=box;   
            }
        }
    }
    for(k=0;k<10;k++)
    {
        printf("%d \n",arr[k]);
    }

    return 0;
}
```

```c
/*3、编写程序，首先输入一个4阶矩阵，之后判断该方阵是否
    关于主对角线对称(相等)(主对角线：左上角到右下角)，
    若对称则打印YES，否则打印NO。*/
#include <stdio.h>
int main(void)
{
    int arr[5][5]={0};
    int i,j;
    for(i=0;i<4;i++)
    {
        scanf("%d %d %d %d",&arr[i][0],&arr[i][1],&arr[i][2],&arr[i][3]);
    }
    for(i=0;i<4;i++)
    {
        for(j=0;j<4;j++)
        {
            if(arr[i][j]!=arr[j][i]){break;}
        }
    }
    if(i==4&&j==4){printf("YES");}
    else{printf("NO");}
    return 0;
}
```

