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
int BinarySearch(int a[],int size,int p)//二分查找
{
	int L=0;
	int R=size-1;
	while(L<=R){
		int mid=L+(R-L)/2;
		if(p==a[mid])
			return mid;
		else if(p>a[mid])
			L=mid+1;
		else
			R=mid-1;
	}
	return -1;
}
int LowerBound(int a[],int size,int p)//在包含size个元素的，从小到大排序的数组a中查找比给定正数p小的，下标最大的元素，找到则返回其下标
{
	int L=0;
	int R=size-1;
	int lastpos=-1;
	while(L<=R){
		int mid=L+(R-L)/2;
		if(a[mid]>=p)
			R=mid-1;
		else{
			lastpos=mid;
			L=mid+1;
		}
	}
	return lastpos;
}
//注意在二分查找中不要写mid=(L+R)/2，要写mid=L+(R-L)/2
//用二分法求方程的根
double eps=1e-6;
double f(double x){return x*x*x-5*x*x+10*x-80;}
int main(){
	double root,x1=0,x2=100,y;
	root=x1+(x2-x1)/2;
	int triedtimes=1;
	y=f(root);
	while(fabs(y)>eps){
		if(y>0)
			x2=root;
		else
			x1=root;
		root=x1+(x2-x1)/2;
		y=f(root);
		triedtimes++;
	}
	cout<<root<<endl;
	cout<<triedtimes<<endl;
	return 0;
}
