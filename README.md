# lab 1

//ex3

#include <iostream> 
using namespace std; 
 
void ChangeIt_1(int n)
{
	n = 5;   
}                            
 
void ChangeIt_2(int *n)
{
    *n = 6;    
}                            
 
void ChangeIt_3(int &n)
{
    n = 7;  
}                            
 
int ChangeIt_4(int n)
{
    n = 8;   
	return n; 
} 
	
void swap (int &n, int *m)
{
	if (n>*m) {
		int temp = n;
		n = *m;
		*m = temp;
	}
	
} 

double getAverage (int *array, int SIZE)
{
	double total, average;
	for (int i=0;i<SIZE;i++) {
		total = total + *array;
		*array++;
	}
	
	average = total / 5;
	return average;
}
 
const int SIZE=5;
main()
{     
	int *p;    
	int x=10, y=7, z; 
	int data [SIZE]={1,3,2,5,4};     
	p=&x;
	       
	ChangeIt_1(x);      
	cout << "ChangeIt_1  : " << *p << endl; 
	         
	ChangeIt_2(&x);     
	cout << "ChangeIt_2  : " << *p << endl;    
	      
	ChangeIt_3(x);     
	cout << "ChangeIt_3  : " << *p << endl; 
	         
	x = ChangeIt_4(x);     
	cout << "ChangeIt_4  : " << *p << endl; 
	
} 

