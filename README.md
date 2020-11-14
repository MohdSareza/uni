# lab 1

//ex1

#include <iostream> 
using namespace std; 
 
main () {    
	int SIZE=5, data[SIZE]={0,1,2,3,4};
	int *p = &data[0];  
	     
	cout << "p[0]   = " << p[0] << endl;     
	cout << "*p     = " << *p << endl;     
	cout << "*(p+0) = " << *(p+0) << endl;     
	cout << "*(p+1) = " << *(p+1) << endl;     
	cout << "*(p+2) = " << *(p+2) << endl;     
	cout << "*p++   = " << *p++ << endl;     
	cout << "*p++   = " << *p++ << endl; 
	
	cout<<"\n";
	
	for (int i=0; i<SIZE; i++){
		cout<< data[i]<< "  ";
    }
    cout<<endl;
    
    p= &data[0];
    for( int i=0; i<SIZE; i++){
    	cout<<*p++<< "  ";
	}	
} 

/*

1. What is *p = &data[0]; 
	*p = 0
	
2. Is p[0] and *p are similar output? Why?
	yes, because *p is pointing to the address that hasn't been added yet.
	
3. What are *(p+0), *(p+1) and *(p+3)?
	*(p+0) = 0 
	*(p+1) = 1
	*(p+3) = 3
	
4. What is *p++? 
	= 1
	
5. Write for loop to output the content of the array data using standard subscript to refer to array elements. 

6. Write for loop to output the content of the array data using pointer to refer to array elements.
   Remember to restart the pointer to point to first element in the array before the while loop. 
   
*/

//ex2

#include<iostream>
using namespace std;

main(){
	int SIZE=5, data[SIZE]={1,3,2,5,4};
	int total =0, *p;
	
	p = data;
	
	cout << *p++ <<endl;
	cout << *++p <<endl;
	cout << *p-- <<endl;
	cout << *--p <<endl;
	
	cout<<"\n";
	
	p = &data[SIZE-1];
	int n=0;
	while (n!=5){
		cout<< *p-n;
		n++;
	}
	
    p = data;
    total = 0;
    for (int i=0; i<SIZE; i++){
		total += *p++;
    }
    
    cout<<"\n\nTotal : "<<total<<endl;
}

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

