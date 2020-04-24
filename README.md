# 《C和指针》第八章编程练习第二题：计算税额

```
float single_tax(float income)
{
	static float money_limit[] = { 0,23350,56550,117950,256500,1000000000};
	static float tax[] = { 0,3502.5,12798.5,31832.5,81710.5 };
	static float tax_per[] = { 0.15,0.28,0.31,0.36,0.396 };
	
	
	int index = 1;
	for (; income >= money_limit[index]; index++) {
		continue;
	}
	index--;

	return  tax[index] + (income - money_limit[index]) * tax_per[index];
}
```
* 将收入，税率等数据都放入数组（或结构）中，免去了if语句。

# 判断任意大小的矩阵是否为单位矩阵

```
int identity_matrix(int* arr,int num)
{
	for (int rows = 0; rows < num; rows++) {
		for (int cols = 0; cols <num; cols++) {
			if (*arr++ != (rows==cols)) {
				return 0;
			}
		}
	}

	return 1;
}
```
* 将二位数组“压扁”为一个指向整型的指针使函数可以接受任意大小的二维数组;`声明为int**arr来接受二维数组是错误的`。用\*arr++ != (rows==cols)判断二维数组中的每个数。



