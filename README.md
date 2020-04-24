# 判断任意大小的矩阵是否为单位矩阵

```
int identity_matrix(int* arr,int num)
{
	for (int i = 0; i < num; i++) {
		for (int j = 0; j <num; j++) {
			if (*arr++ != (i==j)) {
				return 0;
			}
		}
	}

	return 1;
}
```
* 将二位数组“压扁”为一个指向整型的指针使函数可以接受任意大小的二维数组;`声明为int\*\*arr来接受二维数组是错误的`。

