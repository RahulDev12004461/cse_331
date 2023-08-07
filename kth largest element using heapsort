#include<bits/stdc++.h>
using namespace std;
void heapify(int arr[], int n, int i)
{
	int max=i; 
	int left=2*i+1; 
	int r = 2*i+2; 
	if (left<n&&arr[left]>arr[max])
		max=left;
	if (r<n&&arr[r]>arr[max])
		max = r;
	if (max != i) {
		swap(arr[i],arr[max]);
		heapify(arr,n,max);
		}
}

void heapSort(int arr[], int n)
{
	for(int i=n/2-1;i>=0;i--)
	{
		heapify(arr, n, i);
	}
	for(int i=n-1;i>=0;i--)
	{
		swap(arr[0],arr[i]);
		heapify(arr,i,0);
	}
}
int main()
{

	int arr[100];
	int n;
	cout<<"number of elements in array is ";
	cin>>n;
	cout<<endl;
	for(int i=0;i<n;i++)
	{
		cin>>arr[i];
	}

	for(int i=n/2 -1;i>=0;i--){
	heapify(arr,n,i);
}

    cout << "heap is  \n";
    
	for (int i=0;i<n;++i)
		cout<<arr[i]<<" ";
	cout<<"\n";
	heapSort(arr, n);
	cout << "after heapsort \n";
	for (int i=0;i<n;++i)
		cout<<arr[i]<<" ";
	cout<<"\n";
	int k;
	cout<<"enter the kth number is ";
	cin>>k;
	cout<<"\n";
	cout<<arr[n-k];
	
	
return 0;
}
