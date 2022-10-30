# Matrix 
//markdown已存档
 ## 矩阵加法
#include <stdio.h>
int main(void)
{
	int i=0;
	int j=0;
	
	int a[3][3]={
		{1,2,3},
		{4,5,6},
		{1,3,5},
	};
	
	int b[3][3]={
		{1,2,3}, 
		{2,3,4},
		{4,5,6},
	};
	
	for (i=0;i<3;i++) {
		for (j=0;j<3;j++) {
			a[i][j]+=b[i][j];
			printf("%d",a[i][j]);
			printf(" ");
			//printf("\n");
		}
		printf("\n");
		//这一行结束，去下一行 
	}
 } 


## 矩阵乘法
week two
#include <stdio.h>

int main(void)
{
	int i;
	int j;
	//定义matrix a; 
	int a[4][7]={
		{12,10,6,7,9,2,5},
		{2,4,1,3,1,12,6},
		{3,1,2,5,0,4,7},
		{5,6,7,8,9,10,2},	
	};
	
	//定义 matrix b 
	int b[7][6]={
		{2,3,4,5,6,9},
		{5,6,7,8,3,4},
		{4,6,1,12,4,5},
		{5,3,5,10,9,0},
		{6,7,9,2,13,8},
		{9,1,6,0,0,3},
		{1,2,3,4,5,5},
	};
	
	int c[4][6]={0};
	
	int idx;
	//找规律 ：idx 就是被吃掉的那个东西 
	for (i=0;i<4;i++) {
		for (j=0;j<6;j++) {
			for (idx=0;idx<7;idx++) {
				c[i][j]+=a[i][idx]*b[idx][j];
			}
			printf("%d",c[i][j]);
			printf(" ");
		}
		printf("\n");
	}
	return 0;	
}

//Q1：一开始出问题了，为什么出现负数，一堆乱码？
// A1：因为我们没有对从c[i][j] 进行初始化，编译器不会自动把里面元素初始化为零
// 本地变量不会默认初始化的 
//solution：初始化数组 c[i][j]={}；  或者  c[i][j]={0}； 

git add "C:\Users\24908\Desktop\练习图片\乘法.png"

## 矩阵转置
已知行列
#include <stdio.h>
int main(void)
{
	int i=0;
	int j=0;
	
	int a[4][7]={
		{12,10,6,7,9,2,5},
		{2,4,1,3,1,12,6,},
		{3,1,2,5,0,4,7},
		{5,6,7,8,9,10,2},	
	};
	
	int aT[7][4];
	
	for (i=0;i<7;i++) {
		for (j=0;j<4;j++) {
			aT[i][j]=a[j][i];
			printf("%d ",aT[i][j]);
			
		}
		printf("\n") ;
	}
	return 0;
}
//注意转置之后i，j交换数值，不要顺手就i,j上去 

