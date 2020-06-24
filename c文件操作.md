```c
#include <stdio.h>
#include <stdlib.h>
typedef struct 
{
    char name[20];
    int math;
    int computer;
    int english;
    int sum;
    int pass;
}stu;
int main(void)
{
    stu arr[1000];
    int i=1,j=0,m=0;
    char ch='0';
    FILE *student;
    student = fopen("D:/info.txt","r");
    
    if (student == NULL)
    {
        printf("打开失败");             
    }
    else
    {
        printf("所有学生信息如下：\n");

        while(fscanf(student,"%s\t%d\t%d\t%d\n",arr[i].name,&arr[i].math,&arr[i].computer,&arr[i].english)!=EOF)
        {
            printf("name:%s\tmath:%d\tcomputer:%d\tenglish:%d\n",arr[i].name,
                arr[i].math,arr[i].computer,arr[i].english);
            if(arr[i].math<60){arr[i].pass=1;}
            if(arr[i].computer<60){arr[i].pass=1;}
            if(arr[i].english<60){arr[i].pass=1;}
            arr[i].sum=arr[i].math+arr[i].computer+arr[i].english;
            i++;
        }
        printf("以下同学没有通过考试：\n");
        for(j=1;j<=i;j++)
        {
            if(arr[j].pass==1||arr[j].sum<210&&arr[j].sum>0)
            {
                printf("%s\n",arr[j].name);
                m++;
            }
        }
        printf("没有通过考试的人数：%d\n",m);
    }
    fclose(student);
    return 0;
}
```

