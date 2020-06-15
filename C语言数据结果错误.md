1、已知学生信息包括学号、姓名、语文成绩、数学成绩、英语成绩。需求如下，请编写程序实现。

- 学生信息需使用结构体进行存储；
- 成绩均为0~100正整数，学号与姓名均为字符串（最大长度不会超过20）；
- 从键盘输入6名学生基本信息；
- 统计每个学生的平均成绩；
- 找出平均成绩最高的学生。

 ```c
#include<stdio.h>
struct inform{
    char id[21];
    char name[21];
    int chinese,english,math;
};
int main(void)
{
    struct inform informs[10];
    int i,max,aver[10]={0},n;
    for(i=0;i<6;i++)
    {
        scanf("%s %s %d %d %d",&informs[i].id,&informs[i].name,
            &informs[i].chinese,&informs[i].english,&informs[i].math);
    }
    for(i=0;i<6;i++)
    {
        aver[i]=(informs[i].chinese + informs[i].english + informs[i].math)/3;
    }
    for(i=0;i<6;i++)
    {
        printf("%s的平均成绩是%d\n",informs[i].name,aver[i]);
    }
    max = aver[0]; 
    for(i=0;i<5;i++)
    {      
        if(aver[i+1]>=max){max=aver[i+1];n=i+1;}
        else{n=0;}
    }
    printf("平均成绩最高的是%s\n",informs[n].name);
    return 0;
}
 ```

2、现有10个城市名及其春、夏、秋、冬四个季节的平均最高温度，输入10个城市名和四季平均最高温度，计算各个城市的全年平均最高温度，并按照全年平均最高温度从低到高的顺序输出城市名、四季温度及全年平均温度。需求如下，请编写程序实现。

- 城市及四季平均最高温度请定义合适的结构体进行存储；
- 城市名称字符串最大长度不会超过20；
- 四季平均最高温度输入数据均为整数数值；
- 输出全年平均温度时需保留小数点后面两位数字。

输入数据示例：

```
beijing 8 28 31 11
shanghai 12 26 33 18
chongqing 15 27 33 17
xianggang 21 31 33 25
shijiazhuang 8 29 31 13
shenyang 1 24 29 6
nanjing 11 27 32 16
lasa 11 21 23 14
wulumuqi -2 24 28 4
hangzhou 12 27 33 18
```

 ```c
#include<stdio.h>
#include<string.h>
struct weather{
    char place[21];
    int spring,summer,fall,winter;
    double average;
};
int main(void)
{
    int i,j,a;
    double box;    
    char strbox[1000];
    struct weather weathers[10];
    for(i=0;i<=9;i++)
    {
        scanf("%s %d %d %d %d",&weathers[i].place,&weathers[i].spring,&weathers[i].summer,
            &weathers[i].fall,&weathers[i].winter);
    }
    for(i=0;i<=9;i++)
    {
        a=weathers[i].spring+weathers[i].summer+
            weathers[i].fall+weathers[i].winter;
        weathers[i].average= a*1.0/4;    }
    for(j=0;j<9;j++)
    {
       for(i=0;i<=9;i++)
       {
            if(weathers[i].average >= weathers[i+1].average)
            {
                box=weathers[i].average;
                weathers[i].average=weathers[i+1].average;
                weathers[i+1].average=box;

                strcpy(strbox,weathers[i].place);
                strcpy(weathers[i].place,weathers[i+1].place);
                strcpy(weathers[i+1].place,strbox);

                box=weathers[i].spring;
                weathers[i].spring=weathers[i+1].spring;
                weathers[i+1].spring=box;

                box=weathers[i].summer;
                weathers[i].summer=weathers[i+1].summer;
                weathers[i+1].summer=box;

                box=weathers[i].fall;
                weathers[i].fall=weathers[i+1].fall;
                weathers[i+1].fall=box;

                box=weathers[i].winter;
                weathers[i].winter=weathers[i+1].winter;
                weathers[i+1].winter=box;
            }
       }
    }
    for(i=0;i<=9;i++)
    {
        printf("%s            四季温度： %d  %d  %d  %d 平均温度：%.2f\n",weathers[i].place,
            weathers[i].spring,weathers[i].summer,weathers[i].fall,
            weathers[i].winter,weathers[i].average);
    }    
    return 0;
}
 ```

```c
#include <stdio.h>
typedef struct city {
    char name[20];
    int spring,summer,fall,winter;
    double ave;

}City;

int main(void)
{
    City arr[10];
    int i,j;
    for(i=0;i<10;i++)
    {
        scanf("%s%d%d%d%d",arr[i].name,&arr[i].spring,&arr[i].summer,&arr[i].fall,&arr[i].winter);
        arr[i].ave=(arr[i].spring+arr[i].summer+arr[i].fall+arr[i].winter)*1.0/4;
    }
    printf("各城市的全年平均最高温度分别为：\n");
    for(i=0;i<10;i++)
        printf("%.2f\n",arr[i].ave);

     for(i=0;i<9;i++){
        for(j=0;j<9-i;j++){
            if(arr[j].ave>arr[j+1].ave)
            {
                City temp=arr[j];
                arr[j]=arr[j+1];
                arr[j+1]=temp;
            }
        }
     }

     printf("按照全年平均最高温度从低到高的顺序输出城市名、四季温度及全年平均温度：\n");
     for(i=0;i<10;i++){
        printf("%s  %d  %d  %d  %d %.2f\n",arr[i].name,arr[i].spring,arr[i].summer,arr[i].fall,arr[i].winter,arr[i].ave);
     }

   return 0;
}

```



3、链表结点结构已经给出，节点中数据域包括学生学号和成绩，指针域是next结点指针, 请编写链表插入函数Insert（将结点e插入链表末尾），再编写函数Swap（实现链表中第i个结点和第j个结点数据域中学生信息进行交换）。

```
typedef struct node
{
    char ID[20];//学号
    int Score;  //成绩
    struct node * Next;
}Node, * List;

void Insert(List * L, Node e);

void Swap(List * L, int i, int j);
```

PS：结构体定义语句中相当于在定义节点的同时，声明了两种新类型

- typedef struct node Node; （Node的真实类型为 struct node）
- typedef struct node * List;（List的真实类型为 struct node *）

```c
#include <stdio.h>
#include <malloc.h>
typedef struct node
{
    char ID[20];//学号
    int Score;  //成绩
    struct node * Next;
}Node, * List;
void Insert(List * L, Node e)
{
    Node * temp = *L;
    Node * e = (Node *) malloc(sizeof(Node));
    e -> Next = NULL;

    if(temp ==NULL){
        *L=e;}
    else {
        while (temp->Next != NULL)
            temp = temp->Next;
        temp->Next = e;
    }

}
void Swap(List * L, int i, int j)
{
    Node * temp = *L;
    Node * newNode = NULL;
    int size = Swap(temp);
    int i;
    if (i < 0 || i > size)
    {return 0;}
    newNode = (Node *) malloc (sizeof(Node));
    newNode->j= j;
    newNode->Next = NULL;
    if (i == 0) {
        newNode->Next = temp;
        *L= newNode;
        return 1;
    }
    for (k=1; k<i; k++)
        temp = temp->Next;

    newNode->Next = temp->Next;
    temp->Next = newNode;
    return 1;

    Node * temp = *L;
    Node * newNode = NULL;
    int size = Swap(temp);
    int i;
    if (j < 0 || j > size)
        return 0;
    newNode = (Node *) malloc (sizeof(Node));
    newNode->i= i;
    newNode->Next = NULL;
    if (i == 0) {
        newNode->Next = temp;
        *L= newNode;
        return 1;
    }
    for (k=1; k<j; k++)
        temp = temp->Next;

    newNode->Next = temp->Next;
    temp->Next = newNode;
    return 1;

    Node * temp = *L;
    Node * del = NULL;
    while (temp->Next != NULL) {
        if (temp->Next->i != i) {
            temp = temp->Next;
            continue;
        }
        del = temp->    Next;
        temp->Next = del->Next;
        free(del);
    }
    temp = *L;
    if (temp->i == i) {
        *L = temp->Next;
        free(temp);
    }

    Node * temp = *L;
    Node * del = NULL;
    while (temp->Next != NULL) {
        if (temp->Next->j != j) {
            temp = temp->Next;
            continue;
        }
        del = temp->    Next;
        temp->Next = del->Next;
        free(del);
    }
    temp = *L;
    if (temp->j == j) {
        *L = temp->Next;
        free(temp);
    }
}
int main(void)
{
    void Insert(List * L, Node e);
    void Swap(List * L, int i, int j);
    return 0;
}
```

