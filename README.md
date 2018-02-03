# -
一些基础算法和代码
echo“＃ - ”>> README.md 
下面是一些排序方法
void selectionsort(int a[],int size)//选择排序
{
	for(int i=0;i<size-1;++i){
		int tmpmin=i;
		for(int j=i+1;j<size;++j){
			if(a[j]<a[tmpmin]){
				tmpmin=j;}
			int tmp=a[i];//交换a[i]和a[tmpmin]
			a[i]=a[tmpmin];
			a[tmpmin]=a[i];
		}
	}
}
void insertionsort(int a[],int size)//插入排序
{
	for(int i=1;i<size;++i){
		for(int j=0;j<i;++j)
			if(a[j]>a[i]){
				int tmp=a[i];
				for(int k=i;k>j;--k)
					a[k]=a[k-1];
				a[j]=tmp;
				break;
			}
	}
}
void bubblesort(int a[],int size)//冒泡排序
{
	for(int i=size-1;i>0;--i){
		for(int j=0;j<i;++j)
			if(a[j]>a[j+1]){
				int tmp=a[j];
				a[j]=a[j+1];
				a[j+1]=tmp;
			}
	}
}
