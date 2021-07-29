# The C++ Standard Template Library (STL)
The Standard Template Library (STL) is a set of C++ template classes to provide common programming data structures and functions such as lists, stacks, arrays, etc. It is a library of container classes, algorithms, and iterators. It is a generalized library and so, its components are parameterized. A working knowledge of template classes is a prerequisite for working with STL.

## STL has four components
1. [Algorithms](#1)
    1. [Algorithm](#1a)
        1. [Sorting](#1a1)
        1. [Searching](#1a2)
        1. [Important STL Algorithms](#1a3)
            1. [sort(first_iterator, last_iterator)](#1a3a1)
            1. [reverse(first_iterator, last_iterator)](#1a3a2)
            1. [*max_element (first_iterator, last_iterator)](#1a3a3)
            1. [*min_element (first_iterator, last_iterator)](#1a3a4)
            1. [accumulate(first_iterator, last_iterator, initial value of sum)](#1a3a5)
            1. [count(first_iterator, last_iterator,x)](#1a3a6)
            1. [find(first_iterator, last_iterator, x)](#1a3a7)
            1. [binary_search(first_iterator, last_iterator, x)](#1a3a8)
            1. [lower_bound(first_iterator, last_iterator, x)](#1a3a9)
            1. [upper_bound(first_iterator, last_iterator, x)](#1a3a10)
            1. [arr.erase(position to be deleted)](#1a3b1)
            1. [arr.erase(unique(arr.begin(),arr.end()),arr.end())](#1a3b2)
            1. [next_permutation(first_iterator, last_iterator)](#1a3b3)
            1. [prev_permutation(first_iterator, last_iterator)](#1a3b4)
            1. [distance(first_iterator,desired_position)](#1a3b5)
        1. [Useful Array algorithms](#1a4)
            1. [all_of](#1a4a)
            1. [any_of](#1a4b)
            1. [none_of](#1a4c)
            1. [copy_n](#1a4d)
            1. [iota](#1a4e)
        1. [Partition Operations](#1a5)
            1. [partition(beg, end, condition)](#1a5a)
            1. [is_partitioned(beg, end, condition)](#1a5b)
            1. [partition_point(beg, end, condition)](#1a5c)
            1. [stable_partition(beg, end, condition)](#1a5d)
            1. [partition_copy(beg, end, beg1, beg2, condition)](#1a5e)
    1. [Numeric](#1b)
        1. [valarray class](#1b1)
            1. [apply()](#1b1a)
            1. [sum()](#1b1b)
            1. [min()](#1b1c)
            1. [max()](#1b1d)
            1. [shift()](#1b1e)
            1. [Cshift()](#1b1f)
            1. [swap()](#1b1g)

1. [Containers](#2)
    1. [Sequence Containers](#2a)
        1. [vector](#2a1)
		    1. [Iterators](#2a1a)
			1. [Capacity](#2a1b)
			1. [Element access](#2a1c)
			1. [Modifiers](#2a1d)
        1. [list](#2a2)
        1. [deque](#2a3)
        1. [arrays](#2a4)
		    1. [at()](#2a4a)
			1. [get()](#2a4b)
			1. [operator[]](#2a4c)
			1. [front()](#2a4d)
			1. [back()](#2a4e)
			1. [size()](#2a4f)
			1. [max_size()](#2a4g)
			1. [swap()](#2a4h)
			1. [empty()](#2a4i)
			1. [fille()](#2a4j)
        1. [forward_list >= C++11](#2a5)
		    1. [assign()](#2a5a)
			1. [push_front()](#2a5b)
			1. [emplace_front()](#2a5c)
			1. [pop_front()](#2a5d)
			1. [insert_after()](#2a5e)
			1. [emplace_after()](#2a5f)
			1. [erase_after()](#2a5g)
			1. [remove()](#2a5h)
			1. [remove_if()](#2a5i)
			1. [splice_after()](#2a5j)
    1. [Container Adaptors](#2b)
        1. [queue](#2b1)
        1. [priority_queue](#2b2)
        1. [stack](#2b3)        
    1. [Associative Containers](#2C)
        1. [set](#2C1)
        1. [multiset](#2C2)
        1. [map](#2C3)
        1. [multimap](#2C4)
    1. [Unordered Associative Containers](#2d)
        1. [unordered_set >=C++11](#2d)
        1. [unordered_multiset >=C++11](#2d)
        1. [unordered_map >=C++11](#2d)
        1. [unordered_multimap >=C++11](#2d)

1. [Functions](#3)
    1. [Functors](#3a)

1. [Iterators](#4)
    1. [Iterators](#4a)

1. [Utility Library](#5)
    1. [Pair](#5a)



<a name="1"></a>
## Algorithms

<a name="1a"></a>
### Algorithm

<a name="1a1"></a>
* Sorting

<div class="text"><p><a href="https://www.geeksforgeeks.org/sorting-algorithms/">Sorting</a>
<p>The prototype for sort is :&nbsp;</p><pre>sort(startaddress, endaddress)

startaddress: the address of the first 
              element of the array
endaddress: the address of the next 
            contiguous location of the 
            last element of the array.
So actually sort() sorts in the 
range of [startaddress,endaddress)
</pre><div class="responsive-tabs"><h3 class="tabtitle">CPP</h3><div 
div>
```CPP
// C++ progrma to sort an array
#include <algorithm>
#include <iostream>
 
using namespace std;
 
void show(int a[], int array_size)
{
    for (int i = 0; i < array_size; ++i)
        cout << a[i] << " ";
}
 
// Driver code
int main()
{
    int a[] = { 1, 5, 8, 9, 6, 7, 3, 4, 2, 0 };
   
    // size of the array
    int asize = sizeof(a) / sizeof(a[0]);
    cout << "The array before sorting is : \n";
   
    // print the array
    show(a, asize);
 
      // sort the array
    sort(a, a + asize);
 
    cout << "\n\nThe array after sorting is :\n";
   
    // print the array after sorting
    show(a, asize);
 
    return 0;
}
```
<div class="code-output"><strong>Output</strong><pre>The array before sorting is : 
1 5 8 9 6 7 3 4 2 0 

The array after sorting is :
0 1 2 3 4 5 6 7 8 9 </pre></div>
<p>Refer <a href="https://www.geeksforgeeks.org/sort-c-stl/">std::sort()</a> for more details.


<a name="1a2"></a>
* Searching
<br>The prototype for binary search is :&nbsp;</p><pre><strong>binary_search(startaddress, 
              endaddress, valuetofind)</strong>
<strong>Parameters :</strong>
startaddress: the address of the first 
              element of the array.
endaddress: the address of the next contiguous 
            location of the last element of the array.
valuetofind: the target value which we have 
             to search for.
<strong>Returns :</strong>
true if an element equal to valuetofind is found, else false.</pre>

</pre><div class="responsive-tabs"><h3 class="tabtitle">CPP</h3><div 
div>

```CPP
// CPP program to implement
// Binary Search in
// Standard Template Library (STL)
#include <algorithm>
#include <iostream>

using namespace std;

void show(int a[], int arraysize)
{
	for (int i = 0; i < arraysize; ++i)
		cout << a[i] << ",";
}

int main()
{
	int a[] = { 1, 5, 8, 9, 6, 7, 3, 4, 2, 0 };
	int asize = sizeof(a) / sizeof(a[0]);
	cout << "\nThe array is : \n";
	show(a, asize);

	cout << "\n\nLet's say we want to search for ";
	cout << "\n2 in the array So, we first sort the array";
	sort(a, a + asize);
	cout << "\n\nThe array after sorting is : \n";
	show(a, asize);
	cout << "\n\nNow, we do the binary search";
	if (binary_search(a, a + asize, 2))
		cout << "\nElement found in the array";
	else
		cout << "\nElement not found in the array";

	cout << "\n\nNow, say we want to search for 10";
	if (binary_search(a, a + asize, 10))
		cout << "\nElement found in the array";
	else
		cout << "\nElement not found in the array";

	return 0;
}
```

<div class="code-output"><strong>Output</strong><pre>The array is : 
1,5,8,9,6,7,3,4,2,0,

Let's say we want to search for 
2 in the array So, we first sort the array

The array after sorting is : 
0,1,2,3,4,5,6,7,8,9,

Now, we do the binary search
Element found in the array

Now, say we want to search for 10
Element not found in the array</pre></div>
<p><strong>Related Article: </strong><a href="https://www.geeksforgeeks.org/stdbsearch-in-cpp/">std::bsearch in C++</a>&nbsp;


<a name="1a3"></a>
* Important STL Algorithms
<a name="1a3a"></a>
  * Non-Manipulating Algorithms
<a name="1a3a1"></a><a name="1a3a2"></a><a name="1a3a3"></a><a name="1a3a4"></a><a name="1a3a5"></a>

1. sort(first_iterator, last_iterator) – To sort the given vector.
2. reverse(first_iterator, last_iterator) – To reverse a vector.
3. *max_element (first_iterator, last_iterator) – To find the maximum element of a vector.
4. *min_element (first_iterator, last_iterator) – To find the minimum element of a vector.
5. accumulate(first_iterator, last_iterator, initial value of sum) – Does the summation of vector elements
   


```CPP
// A C++ program to demonstrate working of sort(),
// reverse()
#include <algorithm>
#include <iostream>
#include <vector>
#include <numeric> //For accumulate operation
using namespace std;
 
int main()
{
    // Initializing vector with array values
    int arr[] = {10, 20, 5, 23 ,42 , 15};
    int n = sizeof(arr)/sizeof(arr[0]);
    vector<int> vect(arr, arr+n);
 
    cout << "Vector is: ";
    for (int i=0; i<n; i++)
        cout << vect[i] << " ";
 
    // Sorting the Vector in Ascending order
    sort(vect.begin(), vect.end());
 
    cout << "\nVector after sorting is: ";
    for (int i=0; i<n; i++)
       cout << vect[i] << " ";
 
    // Reversing the Vector
    reverse(vect.begin(), vect.end());
 
    cout << "\nVector after reversing is: ";
    for (int i=0; i<6; i++)
        cout << vect[i] << " ";
 
    cout << "\nMaximum element of vector is: ";
    cout << *max_element(vect.begin(), vect.end());
 
    cout << "\nMinimum element of vector is: ";
    cout << *min_element(vect.begin(), vect.end());
 
    // Starting the summation from 0
    cout << "\nThe summation of vector elements is: ";
    cout << accumulate(vect.begin(), vect.end(), 0);
 
    return 0;
}
```
<div class="code-output"><strong>Output</strong><pre>Vector is: 10 20 5 23 42 15 
Vector after sorting is: 5 10 15 20 23 42 
Vector after reversing is: 42 23 20 15 10 5 
Maximum element of vector is: 42
Minimum element of vector is: 5
The summation of vector elements is: 115</pre></div>
  
<br>
<br>
<a name="1a3a6"></a><a name="1a3a7"></a>

6. count(first_iterator, last_iterator,x) – To count the occurrences of x in vector.
7. find(first_iterator, last_iterator, x) – Returns an iterator to the first occurence of x in vector and points to last address of vector ((name_of_vector).end()) if element is not present in vector.



```CPP
// C++ program to demonstrate working of count()
// and find()
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	// Initializing vector with array values
	int arr[] = {10, 20, 5, 23 ,42, 20, 15};
	int n = sizeof(arr)/sizeof(arr[0]);
	vector<int> vect(arr, arr+n);

	cout << "Occurrences of 20 in vector : ";

	// Counts the occurrences of 20 from 1st to
	// last element
	cout << count(vect.begin(), vect.end(), 20);

	// find() returns iterator to last address if
	// element not present
	find(vect.begin(), vect.end(),5) != vect.end()?
						cout << "\nElement found":
					cout << "\nElement not found";

	return 0;
}
```
<div class="code-output"><strong>Output</strong><pre>Occurrences of 20 in vector : 2
Element found</pre></div>


<a name="1a3a8"></a><a name="1a3a9"></a><a name="1a3a10"></a>
<br><br>

8. binary_search(first_iterator, last_iterator, x)<br> – Tests whether x exists in sorted vector or not.

9. lower_bound(first_iterator, last_iterator, x) <br>– returns an iterator pointing to the first element in the range [first,last) which         has a value not less than ‘x’.

10. upper_bound(first_iterator, last_iterator, x) <br>– returns an iterator pointing to the first element in the range [first,last)                  which has a value greater than ‘x’. 


```CPP
// C++ program to demonstrate working of lower_bound()
// and upper_bound().
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	// Initializing vector with array values
	int arr[] = {5, 10, 15, 20, 20, 23, 42, 45};
	int n = sizeof(arr)/sizeof(arr[0]);
	vector<int> vect(arr, arr+n);

	// Sort the array to make sure that lower_bound()
	// and upper_bound() work.
	sort(vect.begin(), vect.end());

	// Returns the first occurrence of 20
	auto q = lower_bound(vect.begin(), vect.end(), 20);

	// Returns the last occurrence of 20
	auto p = upper_bound(vect.begin(), vect.end(), 20);

	cout << "The lower bound is at position: ";
	cout << q-vect.begin() << endl;

	cout << "The upper bound is at position: ";
	cout << p-vect.begin() << endl;

	return 0;
}
```
<div class="code-output"><strong>Output</strong><pre>The lower bound is at position: 3
The upper bound is at position: 5</pre></div>


<a name="1a3b1"></a><a name="1a3b2"></a>

11. arr.erase(position to be deleted) <br>– This erases selected element in vector and shifts and resizes the vector elements accordingly.
12. arr.erase(unique(arr.begin(),arr.end()),arr.end()) <br>– This erases the duplicate occurrences in sorted vector in a single line.
 

```CPP
// C++ program to demonstrate working of erase()
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	// Initializing vector with array values
	int arr[] = {5, 10, 15, 20, 20, 23, 42, 45};
	int n = sizeof(arr)/sizeof(arr[0]);
	vector<int> vect(arr, arr+n);

	cout << "Vector is :";
	for (int i=0; i<vect.size(); i++)
		cout << vect[i]<<" ";

	// Delete second element of vector
	vect.erase(vect.begin()+1);

	cout << "\nVector after erasing the element: ";
	for (int i=0; i<vect.size(); i++)
		cout << vect[i] << " ";

	// sorting to enable use of unique()
	sort(vect.begin(), vect.end());

	cout << "\nVector before removing duplicate "
			" occurrences: ";
	for (int i=0; i<vect.size(); i++)
		cout << vect[i] << " ";

	// Deletes the duplicate occurrences
	vect.erase(unique(vect.begin(),vect.end()),vect.end());

	cout << "\nVector after deleting duplicates: ";
	for (int i=0; i< vect.size(); i++)
		cout << vect[i] << " ";

	return 0;
}
```
<div class="code-output"><strong>Output</strong><pre>Vector is :5 10 15 20 20 23 
Vector after erasing the element: 5 15 20 20 23 
Vector before removing duplicate  occurrences: 5 15 20 20 23 
Vector after deleting duplicates: 5 15 20 23 42 45 </pre></div>

<br><br>

<a name="1a3b4"></a><a name="1a3b3"></a>

13. next_permutation(first_iterator, last_iterator) – This modified the vector to its next permutation.
14. prev_permutation(first_iterator, last_iterator) – This modified the vector to its previous permutation. 


```CPP
// C++ program to demonstrate working
// of next_permutation()
// and prev_permutation()
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	// Initializing vector with array values
	int arr[] = {5, 10, 15, 20, 20, 23, 42, 45};
	int n = sizeof(arr)/sizeof(arr[0]);
	vector<int> vect(arr, arr+n);

	cout << "Given Vector is:\n";
	for (int i=0; i<n; i++)
		cout << vect[i] << " ";

	// modifies vector to its next permutation order
	next_permutation(vect.begin(), vect.end());
	cout << "\nVector after performing next permutation:\n";
	for (int i=0; i<n; i++)
		cout << vect[i] << " ";

	prev_permutation(vect.begin(), vect.end());
	cout << "\nVector after performing prev permutation:\n";
	for (int i=0; i<n; i++)
		cout << vect[i] << " ";

	return 0;
}

```
<div class="code-output"><strong>Output</strong><pre>Given Vector is:
5 10 15 20 20 23 42 45 
Vector after performing next permutation:
5 10 15 20 20 23 45 42 
Vector after performing prev permutation:
5 10 15 20 20 23 42 45 </pre></div>
<br><br>

<a name="1a3b5"></a>

15. distance(first_iterator,desired_position) – It returns the distance of desired position from the first iterator.This function               is very useful while finding the index.


```CPP
// C++ program to demonstrate working of distance()
#include <algorithm>
#include <iostream>
#include <vector>
using namespace std;

int main()
{
	// Initializing vector with array values
	int arr[] = {5, 10, 15, 20, 20, 23, 42, 45};
	int n = sizeof(arr)/sizeof(arr[0]);
	vector<int> vect(arr, arr+n);

	// Return distance of first to maximum element
	cout << "Distance between first to max element: ";
	cout << distance(vect.begin(),
					max_element(vect.begin(), vect.end()));
	return 0;
}
```
<div class="code-output"><strong>Output</strong><pre>Distance between first to max element: 7</pre></div>


<a name="1a4"></a>
* Useful Array algorithms
<a name="1a4a"></a>

1. all_of()<br> This function operates on whole range of array elements and can save time to run a loop to check each elements one by one. It checks for a given property on every element and returns true when each element in range satisfies specified property, else returns false.

```CPP
// C++ code to demonstrate working of all_of()
#include<iostream>
#include<algorithm> // for all_of()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, -6};
  
    // Checking if all elements are positive
    all_of(ar, ar+6, [](int x) { return x>0; })?
          cout << "All are positive elements" :
          cout << "All are not positive elements";
  
    return 0;
  
}
```
<p>Output</p>
<pre>All are not positive elements</pre>
In the above code, -6 being a negative element negates the condition and returns false.
<br>
<br>

<a name="1a4b"></a>

2. any_of() <br> This function checks for a given range if there’s even one element satisfying a given property mentioned in function. Returns true if at least one element satisfies the property else returns false.

```CPP
// C++ code to demonstrate working of any_of()
#include<iostream>
#include<algorithm> // for any_of()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, -6};
  
    // Checking if any element is negative
    any_of(ar, ar+6, [](int x){ return x<0; })?
          cout << "There exists a negative element" :
          cout << "All are positive elements";
  
    return 0;
  
}
```
<p>Output</p>
<pre>There exists a negative element</pre>
In above code, -6 makes the condition positive.
<br>
<br>

<a name="1a4c"></a>
3. none_of() <br>This function returns true if none of elements satisfies the given condition else returns false.

```CPP
// C++ code to demonstrate working of none_of()
#include<iostream>
#include<algorithm> // for none_of()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, 6};
  
    // Checking if no element is negative
    none_of(ar, ar+6, [](int x){ return x<0; })?
          cout << "No negative elements" :
          cout << "There are negative elements";
  
    return 0;
}
```
<p>Output</p>
<pre>No negative elements</pre>
Since all elements are positive, the function returns true.


<br>
<br>
<a name="1a4d"></a>
4. copy_n() <br>
copy_n() copies one array elements to new array. This type of copy creates a deep copy of array. This function takes 3 arguments, source array name, size of array and the target array name.

```CPP
// C++ code to demonstrate working of copy_n()
#include<iostream>
#include<algorithm> // for copy_n()
using namespace std;
int main()
{
    // Initializing array
    int ar[6] =  {1, 2, 3, 4, 5, 6};
  
    // Declaring second array
    int ar1[6];
  
    // Using copy_n() to copy contents
    copy_n(ar, 6, ar1);
  
    // Displaying the copied array
    cout << "The new array after copying is : ";
    for (int i=0; i<6 ; i++)
       cout << ar1[i] << " ";
  
    return 0;
  
}
```
<p>Output</p>
<pre>The new array after copying is : 1 2 3 4 5 6</pre>
In the above code, the elements of ar are copied in ar1 using copy_n()



<a name="1a4e"></a>
5. iota() <br>This function is used to assign continuous values to array. This function accepts 3 arguments, the array name, size, and the starting number.

```CPP
// C++ code to demonstrate working of iota()
#include<iostream>
#include<numeric> // for iota()
using namespace std;
int main()
{
    // Initializing array with 0 values
    int ar[6] =  {0};
  
    // Using iota() to assign values
    iota(ar, ar+6, 20);
  
    // Displaying the new array
    cout << "The new array after assigning values is : ";
    for (int i=0; i<6 ; i++)
       cout << ar[i] << " ";
  
    return 0;
  
}
```
<p>Output</p>
<pre>The new array after assigning values is : 20 21 22 23 24 25</pre>
In the above code, continuous values are assigned to array using iota().


<a name="1a5"></a>
* Partition Operations
<a name="1a5a"></a> <a name="1a5b"></a>
1. partition(beg, end, condition) :<br>- This function is used to partition the elements on basis of condition mentioned in its arguments.
2. is_partitioned(beg, end, condition) :<br>- This function returns boolean true if container is partitioned else returns false.


```CPP
// C++ code to demonstrate the working of
// partition() and is_partitioned()
#include<iostream>
#include<algorithm> // for partition algorithm
#include<vector> // for vector
using namespace std;
int main()
{
	// Initializing vector
	vector<int> vect = { 2, 1, 5, 6, 8, 7 };
	
	// Checking if vector is partitioned
	// using is_partitioned()
	is_partitioned(vect.begin(), vect.end(), [](int x)
	{
		return x%2==0;
		
	})?
	
	cout << "Vector is partitioned":
	cout << "Vector is not partitioned";
	cout << endl;
	
	// partitioning vector using partition()
	partition(vect.begin(), vect.end(), [](int x)
	{
		return x%2==0;
		
	});
	
	// Checking if vector is partitioned
	// using is_partitioned()
	is_partitioned(vect.begin(), vect.end(), [](int x)
	{
		return x%2==0;
		
	})?
	
	cout << "Now, vector is partitioned after partition operation":
	cout << "Vector is still not partitioned after partition operation";
	cout << endl;
	
	// Displaying partitioned Vector
	cout << "The partitioned vector is : ";
	for (int &x : vect) cout << x << " ";
	
	return 0;
	
}
```
<p>Output</p>
Vector is not partitioned
Now, vector is partitioned after partition operation
The partitioned vector is : 2 8 6 5 1 7
<pre></pre>

<br><br>
<a name="1a5c"></a><a name="1a5d"></a>

3. stable_partition(beg, end, condition) :<br>- This function is used to partition the elements on basis of condition mentioned in its arguments in such a way that the relative order of the elements is preserved..
4. partition_point(beg, end, condition) :<br>- This function returns an iterator pointing to the partition point of container i.e. the first element in the partitioned range [beg,end) for which condition is not true. The container should already be partitioned for this function to work.

```CPP
// C++ code to demonstrate the working of
// stable_partition() and partition_point()
#include<iostream>
#include<algorithm> // for partition algorithm
#include<vector> // for vector
using namespace std;
int main()
{
	// Initializing vector
	vector<int> vect = { 2, 1, 5, 6, 8, 7 };
	
	// partitioning vector using stable_partition()
	// in sorted order
	stable_partition(vect.begin(), vect.end(), [](int x)
	{
		return x%2 == 0;	
	});
	
	// Displaying partitioned Vector
	cout << "The partitioned vector is : ";
	for (int &x : vect) cout << x << " ";
	cout << endl;
	
	// Declaring iterator
	vector<int>::iterator it1;
	
	// using partition_point() to get ending position of partition
	auto it = partition_point(vect.begin(), vect.end(), [](int x)
	{
		return x%2==0;
	});
	
	// Displaying partitioned Vector
	cout << "The vector elements returning true for condition are : ";
	for ( it1= vect.begin(); it1!=it; it1++)
	cout << *it1 << " ";
	cout << endl;
	
	return 0;
	
}
```
<p>Output</p>
<pre>The partitioned vector is : 2 6 8 1 5 7 
The vector elements returning true for condition are : 2 6 8</pre>
<br><br>
<a name="1a5e"></a>
5. partition_copy(beg, end, beg1, beg2, condition) :<br>- This function copies the partitioned elements in the differenet containers mentioned in its arguments. It takes 5 arguments. Beginning and ending position of container, beginning position of new container where elements have to be copied (elements returning true for condition), beginning position of new container where other elements have to be copied (elements returning false for condition) and the condition. Resizing new containers is necessary for this function.

```CPP
// C++ code to demonstrate the working of
// partition_copy()
#include<iostream>
#include<algorithm> // for partition algorithm
#include<vector> // for vector
using namespace std;
int main()
{
	// Initializing vector
	vector<int> vect = { 2, 1, 5, 6, 8, 7 };
	
	// Declaring vector1
	vector<int> vect1;
	
	// Declaring vector1
	vector<int> vect2;
	
	// Resizing vectors to suitable size using count_if() and resize()
	int n = count_if (vect.begin(), vect.end(), [](int x)
	{
		return x%2==0;
		
	} );
	vect1.resize(n);
	vect2.resize(vect.size()-n);
	
	// Using partition_copy() to copy partitions
	partition_copy(vect.begin(), vect.end(), vect1.begin(),
									vect2.begin(), [](int x)
	{
		return x%2==0;
	});
	
	
	// Displaying partitioned Vector
	cout << "The elements that return true for condition are : ";
	for (int &x : vect1)
			cout << x << " ";
	cout << endl;
	
	// Displaying partitioned Vector
	cout << "The elements that return false for condition are : ";
	for (int &x : vect2)
			cout << x << " ";
	cout << endl;
	
	return 0;
}
```
<p>Output</p>
<pre>The elements that return true for condition are : 2 6 8 
The elements that return false for condition are : 1 5 7</pre>


<a name="1b"></a>
### Numeric
<a name="1b1"></a>
* valarray class

<a name="1b1a"></a>
Public member functions in valarray class :
1. apply() :- This function applies the manipulation given in its arguments to all the valarray elements at once and returns a new valarray with manipulated values.
<a name="1b1b"></a>
2. sum() :- This function returns the summation of all the elements of valarrays at
```CPP
// C++ code to demonstrate the working of
// apply() and sum()
#include<iostream>
#include<valarray> // for valarray functions
using namespace std;
int main()
{
	// Initializing valarray
	valarray<int> varr = { 10, 2, 20, 1, 30 };
	
	// Declaring new valarray
	valarray<int> varr1 ;
	
	// Using apply() to increment all elements by 5
	varr1 = varr.apply([](int x){return x=x+5;});
	
	// Displaying new elements value
	cout << "The new valarray with manipulated values is : ";
	for (int &x: varr1) cout << x << " ";
	cout << endl;
	
	// Displaying sum of both old and new valarray
	cout << "The sum of old valarray is : ";
	cout << varr.sum() << endl;
	cout << "The sum of new valarray is : ";
	cout << varr1.sum() << endl;

	return 0;
	
}
```
<p>Output</p>
<pre>The new valarray with manipulated values is : 15 7 25 6 35 
The sum of old valarray is : 63
The sum of new valarray is : 88</pre>


<a name="1b1c"></a>
3. min() :- This function returns the smallest element of valarray.
<a name="1b1d"></a>
4. max() :- This function returns the largest element of valarray.
```CPP
// C++ code to demonstrate the working of
// max() and min()
#include<iostream>
#include<valarray> // for valarray functions
using namespace std;
int main()
{
	// Initializing valarray
	valarray<int> varr = { 10, 2, 20, 1, 30 };
	
	// Displaying largest element of valarray
	cout << "The largest element of valarray is : ";
	cout << varr.max() << endl;
	
	// Displaying smallest element of valarray
	cout << "The smallest element of valarray is : ";
	cout << varr.min() << endl;

	return 0;
	
}
```
<p>Output</p>
<pre>The largest element of valarray is : 30
The smallest element of valarray is : 1</pre>


<a name="1b1e"></a>
5. shift() :- This function returns the new valarray after shifting elements by the number mentioned in its argument. If the number is positive, left-shift is applied, if number is negative, right-shift is applied.

<a name="1b1f"></a>
6. cshift() :- This function returns the new valarray after circularly shifting(rotating) elements by the number mentioned in its argument. If the number is positive, left-circular shift is applied, if number is negative, right-circular shift is applied.
```CPP
// C++ code to demonstrate the working of
// shift() and cshift()
#include<iostream>
#include<valarray> // for valarray functions
using namespace std;
int main()
{
	// Initializing valarray
	valarray<int> varr = { 10, 2, 20, 1, 30 };
	
	// Declaring new valarray
	valarray<int> varr1;
	
	// using shift() to shift elements to left
	// shifts valarray by 2 position
	varr1 = varr.shift(2);
	
	// Displaying elements of valarray after shifting
	cout << "The new valarray after shifting is : ";
	for ( int&x : varr1) cout << x << " ";
	cout << endl;
	
	// using cshift() to circulary shift elements to right
	// rotates valarray by 3 position
	varr1 = varr.cshift(-3);
	
	// Displaying elements of valarray after circular shifting
	cout << "The new valarray after circular shifting is : ";
	for ( int&x : varr1) cout << x << " ";
	cout << endl;

	return 0;
	
}
```
<p>Output</p>
<pre>The new valarray after shifting is : 20 1 30 0 0 
The new valarray after circular shifting is : 20 1 30 10 2</pre>

<a name="1b1g"></a>
7. swap() :- This function swaps one valarray with other.
```CPP
// C++ code to demonstrate the working of
// swap()
#include<iostream>
#include<valarray> // for valarray functions
using namespace std;
int main()
{
// Initializing 1st valarray
	valarray<int> varr1 = {1, 2, 3, 4};
	
	// Initializing 2nd valarray
	valarray<int> varr2 = {2, 4, 6, 8};
	
	// Displaying valarrays before swapping
	cout << "The contents of 1st valarray "
			"before swapping are : ";
	for (int &x : varr1)
		cout << x << " ";
	cout << endl;
	cout << "The contents of 2nd valarray "
			"before swapping are : ";
	for (int &x : varr2)
		cout << x << " ";
	cout << endl;
	
	// Use of swap() to swap the valarrays
	varr1.swap(varr2);
	
	// Displaying valarrays after swapping
	cout << "The contents of 1st valarray "
			"after swapping are : ";
	for (int &x : varr1)
		cout << x << " ";
	cout << endl;
	
	cout << "The contents of 2nd valarray "
			"after swapping are : ";
	for (int &x : varr2)
		cout << x << " ";
	cout << endl;

	return 0;
	
}
```
<p>Output</p>
<pre>The contents of 1st valarray before swapping are : 1 2 3 4 
The contents of 2nd valarray before swapping are : 2 4 6 8 
The contents of 1st valarray after swapping are : 2 4 6 8 
The contents of 2nd valarray after swapping are : 1 2 3 4 </pre>





<!----------------------------------->
<!-------------Containers------------>
<!----------------------------------->
<a name="2"></a>
## Containers
<a name="2a"></a>
### Sequence Containers: implement data structures which can be accessed in a sequential manner.
<a name="2a1"></a>

* vector <br>
Certain functions associated with the vector are:
<a name="2a1a"></a>	 

<h4>Iterators</h4>

1. begin() – Returns an iterator pointing to the first element in the vector
end() – Returns an iterator pointing to the theoretical element that follows the last element in the vector
2. rbegin() – Returns a reverse iterator pointing to the last element in the vector (reverse beginning). It moves from last to first element
3. rend() – Returns a reverse iterator pointing to the theoretical element preceding the first element in the vector (considered as reverse end)
4. cbegin() – Returns a constant iterator pointing to the first element in the vector.
5. cend() – Returns a constant iterator pointing to the theoretical element that follows the last element in the vector.
6. crbegin() – Returns a constant reverse iterator pointing to the last element in the vector (reverse beginning). It moves from last to first element
7. crend() – Returns a constant reverse iterator pointing to the theoretical element preceding the first element in the vector (considered as reverse end)
```CPP
// C++ program to illustrate the
// iterators in vector
#include <iostream>
#include <vector>

using namespace std;

int main()
{
	vector<int> g1;

	for (int i = 1; i <= 5; i++)
		g1.push_back(i);

	cout << "Output of begin and end: ";
	for (auto i = g1.begin(); i != g1.end(); ++i)
		cout << *i << " ";

	cout << "\nOutput of cbegin and cend: ";
	for (auto i = g1.cbegin(); i != g1.cend(); ++i)
		cout << *i << " ";

	cout << "\nOutput of rbegin and rend: ";
	for (auto ir = g1.rbegin(); ir != g1.rend(); ++ir)
		cout << *ir << " ";

	cout << "\nOutput of crbegin and crend : ";
	for (auto ir = g1.crbegin(); ir != g1.crend(); ++ir)
		cout << *ir << " ";

	return 0;
}
```
<p>Output</p>
<pre>Output of begin and end: 1 2 3 4 5 
Output of cbegin and cend: 1 2 3 4 5 
Output of rbegin and rend: 5 4 3 2 1 
Output of crbegin and crend : 5 4 3 2 1</pre>

<a name="2a1b"></a>	

<h4>Cpacity</h4>

1. size() – Returns the number of elements in the vector.
2. max_size() – Returns the maximum number of elements that the vector can hold.
3. capacity() – Returns the size of the storage space currently allocated to the vector expressed as number of elements.
4. resize(n) – Resizes the container so that it contains ‘n’ elements.
5. empty() – Returns whether the container is empty.
6. shrink_to_fit() – Reduces the capacity of the container to fit its size and destroys all elements beyond the capacity.
7. reserve() – Requests that the vector capacity be at least enough to contain n elements.
8. std::fill - fill( ForwardIt first, ForwardIt last, const T& value );
```CPP
// C++ program to illustrate the
// capacity function in vector
#include <iostream>
#include <vector>

using namespace std;

int main()
{
	vector<int> g1;

	for (int i = 1; i <= 5; i++)
		g1.push_back(i);

	cout << "Size : " << g1.size();
	cout << "\nCapacity : " << g1.capacity();
	cout << "\nMax_Size : " << g1.max_size();

	// resizes the vector size to 4
	g1.resize(4);

	// prints the vector size after resize()
	cout << "\nSize : " << g1.size();

	// checks if the vector is empty or not
	if (g1.empty() == false)
		cout << "\nVector is not empty";
	else
		cout << "\nVector is empty";

	// Shrinks the vector
	g1.shrink_to_fit();
	cout << "\nVector elements are: ";
	for (auto it = g1.begin(); it != g1.end(); it++)
		cout << *it << " ";

	return 0;
}
```
<p>Output</p>
<pre>
Size : 5
Capacity : 8
Max_Size : 4611686018427387903
Size : 4
Vector is not empty
Vector elements are: 1 2 3 4
</pre>




<a name="2a1c"></a>	

<h4>Element access</h4>

1. reference operator [g] – Returns a reference to the element at position ‘g’ in the vector
2. at(g) – Returns a reference to the element at position ‘g’ in the vector
3. front() – Returns a reference to the first element in the vector
4. back() – Returns a reference to the last element in the vector
5. data() – Returns a direct pointer to the memory array used internally by the vector to store its owned elements.

```CPP
// C++ program to illustrate the
// element accesser in vector
#include <bits/stdc++.h>
using namespace std;

int main()
{
	vector<int> g1;

	for (int i = 1; i <= 10; i++)
		g1.push_back(i * 10);

	cout << "\nReference operator [g] : g1[2] = " << g1[2];

	cout << "\nat : g1.at(4) = " << g1.at(4);

	cout << "\nfront() : g1.front() = " << g1.front();

	cout << "\nback() : g1.back() = " << g1.back();

	// pointer to the first element
	int* pos = g1.data();

	cout << "\nThe first element is " << *pos;
	return 0;
}

```
<p>Output</p>
<pre>Reference operator [g] : g1[2] = 30
at : g1.at(4) = 50
front() : g1.front() = 10
back() : g1.back() = 100
The first element is 10</pre>





<a name="2a1d"></a>	

<h4>Modifiers</h4>


1. assign() – It assigns new value to the vector elements by replacing old ones
2. push_back() – It push the elements into a vector from the back
3. pop_back() – It is used to pop or remove elements from a vector from the back.
4. insert() – It inserts new elements before the element at the specified position
5. erase() – It is used to remove elements from a container from the specified position or range.
6. swap() – It is used to swap the contents of one vector with another vector of same type. Sizes may differ.
7. clear() – It is used to remove all the elements of the vector container
8. emplace() – It extends the container by inserting new element at position
9. emplace_back() – It is used to insert a new element into the vector container, the new element is added to the end of the vector
```CPP
// C++ program to illustrate the
// Modifiers in vector
#include <bits/stdc++.h>
#include <vector>
using namespace std;

int main()
{
	// Assign vector
	vector<int> v;

	// fill the array with 10 five times
	v.assign(5, 10);

	cout << "The vector elements are: ";
	for (int i = 0; i < v.size(); i++)
		cout << v[i] << " ";

	// inserts 15 to the last position
	v.push_back(15);
	int n = v.size();
	cout << "\nThe last element is: " << v[n - 1];

	// removes last element
	v.pop_back();

	// prints the vector
	cout << "\nThe vector elements are: ";
	for (int i = 0; i < v.size(); i++)
		cout << v[i] << " ";

	// inserts 5 at the beginning
	v.insert(v.begin(), 5);

	cout << "\nThe first element is: " << v[0];

	// removes the first element
	v.erase(v.begin());

	cout << "\nThe first element is: " << v[0];

	// inserts at the beginning
	v.emplace(v.begin(), 5);
	cout << "\nThe first element is: " << v[0];

	// Inserts 20 at the end
	v.emplace_back(20);
	n = v.size();
	cout << "\nThe last element is: " << v[n - 1];

	// erases the vector
	v.clear();
	cout << "\nVector size after erase(): " << v.size();

	// two vector to perform swap
	vector<int> v1, v2;
	v1.push_back(1);
	v1.push_back(2);
	v2.push_back(3);
	v2.push_back(4);

	cout << "\n\nVector 1: ";
	for (int i = 0; i < v1.size(); i++)
		cout << v1[i] << " ";

	cout << "\nVector 2: ";
	for (int i = 0; i < v2.size(); i++)
		cout << v2[i] << " ";

	// Swaps v1 and v2
	v1.swap(v2);

	cout << "\nAfter Swap \nVector 1: ";
	for (int i = 0; i < v1.size(); i++)
		cout << v1[i] << " ";

	cout << "\nVector 2: ";
	for (int i = 0; i < v2.size(); i++)
		cout << v2[i] << " ";
}

```
<p>Output</p>
<pre>The vector elements are: 10 10 10 10 10 
The last element is: 15
The vector elements are: 10 10 10 10 10 
The first element is: 5
The first element is: 10
The first element is: 5
The last element is: 20
Vector size after erase(): 0

Vector 1: 1 2 
Vector 2: 3 4 
After Swap 
Vector 1: 3 4 
Vector 2: 1 2</pre>


<strong>All Vector Functions :</strong>

<div>
<div style="width:50%;float:left;text-align:left">
	<ul>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorbegin-vectorend-c-stl/">vector::begin() and vector::end()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vector-rbegin-and-rend-function-in-c-stl/">vector rbegin() and rend()</a></li><li><a href="https://www.geeksforgeeks.org/vector-cbegin-vector-cend-c-stl/">vector::cbegin() and vector::cend()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorcrend-vectorcrbegin-examples/">vector::crend() and vector::crbegin()</a></li><li><a href="https://www.geeksforgeeks.org/vector-assign-in-c-stl/">vector::assign()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/">vector::at()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/">vector::back()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vector-capacity-function-in-c-stl/">vector::capacity()</a></li><li><a href="https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/">vector::clear()</a></li><li><a href="https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/">vector::push_back()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorpush_back-vectorpop_back-c-stl/">vector::pop_back()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/">vector::empty()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorclear-vectorerase-c-stl/">vector::erase()</a>
		</li>
	</ul>
</div>
<div style="width:50%;float:right;text-align:left">
	<ul>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorempty-vectorsize-c-stl/">vector::size()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorat-vectorswap-c-stl/">vector::swap()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/using-stdvectorreserve-whenever-possible/">vector::reserve()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vector-resize-c-stl/">vector::resize()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vector-shrink_to_fit-function-in-c-stl/">vector::shrink_to_fit()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectoroperator-vectoroperator-c-stl/">vector::operator=</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectoroperator-vectoroperator-c-stl/">vector::operator[]</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectorfront-vectorback-c-stl/">vector::front()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vector-data-function-in-c-stl/">vector::data()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vectoremplace_back-c-stl/">vector::emplace_back()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vector-emplace-function-in-c-stl/">vector::emplace()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vector-max_size-function-in-c-stl/">vector::max_size()</a>
		</li>
		<li>
			<a href="https://www.geeksforgeeks.org/vector-insert-function-in-c-stl/">vector::insert()</a>
		</li>
	</ul>	
</div>
</div>





<br><br><br>

<a name="2a2"></a>

* list <br>
Lists are sequence containers that allow non-contiguous memory allocation. As compared to vector, list has slow traversal, but once a position has been found, insertion and deletion are quick. Normally, when we say a List, we talk about doubly linked list. For implementing a singly linked list, we use forward list.

Below is the program to show the working of some functions of List:
```CPP
#include <iostream>
#include <list>
#include <iterator>
using namespace std;

//function for printing the elements in a list
void showlist(list <int> g)
{
	list <int> :: iterator it;
	for(it = g.begin(); it != g.end(); ++it)
		cout << '\t' << *it;
	cout << '\n';
}

int main()
{

	list <int> gqlist1, gqlist2;


	for (int i = 0; i < 10; ++i)
	{
		gqlist1.push_back(i * 2);
		gqlist2.push_front(i * 3);
	}
	cout << "\nList 1 (gqlist1) is : ";
	showlist(gqlist1);

	cout << "\nList 2 (gqlist2) is : ";
	showlist(gqlist2);

	cout << "\ngqlist1.front() : " << gqlist1.front();
	cout << "\ngqlist1.back() : " << gqlist1.back();

	cout << "\ngqlist1.pop_front() : ";
	gqlist1.pop_front();
	showlist(gqlist1);

	cout << "\ngqlist2.pop_back() : ";
	gqlist2.pop_back();
	showlist(gqlist2);

	cout << "\ngqlist1.reverse() : ";
	gqlist1.reverse();
	showlist(gqlist1);

	cout << "\ngqlist2.sort(): ";
	gqlist2.sort();
	showlist(gqlist2);

	return 0;

}
```
<p>Output</p>
<pre>List 1 (gqlist1) is :     0    2    4    6    
8    10    12    14    16    18

List 2 (gqlist2) is :     27    24    21    18    
15    12    9    6    3    0

gqlist1.front() : 0
gqlist1.back() : 18
gqlist1.pop_front() :     2    4    6    8    
10    12    14    16    18

gqlist2.pop_back() :     27    24    21    18    
15    12    9    6    3

gqlist1.reverse() :     18    16    14    12    
10    8    6    4    2

gqlist2.sort():     3    6    9    12    
15    18    21    24    27</pre>

<p><strong>Functions used with List:</strong></p>
<ul><li><a href="https://www.geeksforgeeks.org/list-front-function-in-c-stl/" rel="noopener" target="_blank">front()</a> – Returns the value of the first element in the list.</li><li><a href="https://www.geeksforgeeks.org/list-back-function-in-c-stl/" rel="noopener" target="_blank">back()</a> – Returns the value of the last element in the list .</li><li><a href="https://www.geeksforgeeks.org/list-push_front-function-in-c-stl/" rel="noopener" target="_blank">push_front(g)</a> – Adds a new element ‘g’ at the beginning of the list .</li><li><a href="https://www.geeksforgeeks.org/list-push_back-function-in-c-stl/" rel="noopener" target="_blank">push_back(g)</a> – Adds a new element ‘g’ at the end of the list.</li><li><a href="https://www.geeksforgeeks.org/list-pop_front-function-in-c-stl/" rel="noopener" target="_blank">pop_front()</a> – Removes the first element of the list, and reduces size of the list by 1.</li><li><a href="https://www.geeksforgeeks.org/list-pop_back-function-in-c-stl/" rel="noopener" target="_blank">pop_back()</a> – Removes the last element of the list, and reduces size of the list by 1</li><li><a href="https://www.geeksforgeeks.org/listbegin-listend-c-stl/" rel="noopener" target="_blank">list::begin() and list::end() in C++ STL</a>– <strong>begin()</strong> function returns an iterator pointing to the first element of the list</li><li><a href="https://www.geeksforgeeks.org/list-end-function-in-c-stl/" rel="noopener" target="_blank">end()</a>– <strong>end()</strong> function returns an iterator pointing to the theoretical last element which follows the last element.</li><li><a href="https://www.geeksforgeeks.org/list-rbegin-and-rend-function-in-c-stl/" rel="noopener" target="_blank">list rbegin() and rend() function in C++ STL</a>– <strong>rbegin()</strong> returns a reverse iterator which points to the last element of the list. <strong>rend() </strong>returns a reverse iterator which points to the position before the beginning of the list.</li><li><a href="https://www.geeksforgeeks.org/list-cbegin-and-cend-function-in-c-stl/" rel="noopener" target="_blank">list cbegin() and cend() function in C++ STL</a>– <strong>cbegin()</strong> returns a constant random access iterator which points to the beginning of the list. <strong>cend()</strong> returns a constant random access iterator which points to the end of the list.</li><li><a href="https://www.geeksforgeeks.org/list-crbegin-and-crend-function-in-c-stl/" rel="noopener" target="_blank">list crbegin() and crend() function in C++ STL</a>– <strong>crbegin()</strong> returns a constant reverse iterator which points to the last element of the list i.e reversed beginning of container. <strong>crend()</strong> returns a constant reverse iterator which points to the theoretical element preceding the first element in the list i.e. the reverse end of the list.</li><li><a href="https://www.geeksforgeeks.org/list-empty-function-in-c-stl/" rel="noopener" target="_blank">empty()</a> – Returns whether the list is empty(1) or not(0).</li><li><a href="https://www.geeksforgeeks.org/list-insert-in-c-stl/" rel="noopener" target="_blank">insert()</a> – Inserts new elements in the list before the element at a specified position.</li><li><a href="https://www.geeksforgeeks.org/list-erase-function-in-c-stl/" rel="noopener" target="_blank">erase()</a> – Removes a single element or a range of elements from the list.</li><li><a href="https://www.geeksforgeeks.org/list-assign-function-in-c-stl/" rel="noopener" target="_blank">assign()</a> – Assigns new elements to list by replacing current elements and resizes the list.</li><li><a href="https://www.geeksforgeeks.org/list-remove-function-in-c-stl/" rel="noopener" target="_blank">remove()</a> – Removes all the elements from the list, which are equal to given element.</li><li><a href="https://www.geeksforgeeks.org/listremove-listremove_if-c-stl/" rel="noopener" target="_blank">list::remove_if() in C++ STL</a>– Used to remove all the values from the list that correspond true to the predicate or condition given as parameter to the function.</li><li><a href="https://www.geeksforgeeks.org/list-reverse-function-in-c-stl/" rel="noopener" target="_blank">reverse()</a> – Reverses the list.</li><li><a href="https://www.geeksforgeeks.org/list-size-function-in-c-stl/" rel="noopener" target="_blank">size()</a> – Returns the number of elements in the list.</li><li><a href="https://www.geeksforgeeks.org/list-resize-function-in-c-stl/" rel="noopener" target="_blank">list resize()function in C++ STL</a>– Used to resize a list container.</li><li><a href="https://www.geeksforgeeks.org/stdlistsort-c-stl/" rel="noopener" target="_blank">sort()</a> – Sorts the list in increasing order.</li><li><a href="https://www.geeksforgeeks.org/list-max_size-function-in-c-stl/" rel="noopener" target="_blank">list max_size() function in C++ STL</a>– Returns the maximum number of elements a list container can hold.</li><li><a href="https://www.geeksforgeeks.org/list-unique-in-c-stl/" rel="noopener" target="_blank">list unique() in C++ STL</a>– Removes all duplicate consecutive elements from the list.</li><li><a href="https://www.geeksforgeeks.org/listemplace_front-listemplace_back-c-stl/" rel="noopener" target="_blank">list::emplace_front() and list::emplace_back() in C++ STL</a>– <strong>emplace_front()</strong> function is used to insert a new element into the list container, the new element is added to the beginning of the list. <strong>emplace_back()</strong> function is used to insert a new element into the list container, the new element is added to the end of the list.</li><li><a href="https://www.geeksforgeeks.org/listclear-c-stl/" rel="noopener" target="_blank">list::clear() in C++ STL</a>– <strong>clear() </strong>function is used to remove all the elements of the list container, thus making it size 0.</li><li><a href="https://www.geeksforgeeks.org/listoperator-c-stl/" rel="noopener" target="_blank">list::operator= in C++ STL</a>– This operator is used to assign new contents to the container by replacing the existing contents.</li><li><a href="https://www.geeksforgeeks.org/listswap-c-stl/" rel="noopener" target="_blank">list::swap() in C++ STL</a>– This function is used to swap the contents of one list with another list of same type and size.</li><li><a href="https://www.geeksforgeeks.org/list-splice-function-in-c-stl/" rel="noopener" target="_blank">list splice() function in C++ STL</a>– Used to transfer elements from one list to another.</li><li><a href="https://www.geeksforgeeks.org/list-merge-function-in-c-stl/" rel="noopener" target="_blank">list merge() function in C++ STL</a>– Merges two sorted lists into one</li><li><a href="https://www.geeksforgeeks.org/list-emplace-function-in-c-stl/" rel="noopener" target="_blank">list emplace() function in C++ STL</a>– Extends list by inserting new element at a given position.</li></ul>


<br><br><br>

<a name="2a3"></a>

* deque <br>
Double ended queues are sequence containers with the feature of expansion and contraction on both the ends.
They are similar to vectors, but are more efficient in case of insertion and deletion of elements. Unlike vectors, contiguous storage allocation may not be guaranteed.
Double Ended Queues are basically an implementation of the data structure double ended queue. A queue data structure allows insertion only at the end and deletion from the front. This is like a queue in real life, wherein people are removed from the front and added at the back. Double ended queues are a special case of queues where insertion and deletion operations are possible at both the ends.

The functions for deque are same as vector, with an addition of push and pop operations for both front and back.

```CPP
#include <iostream>
#include <deque>

using namespace std;

void showdq(deque <int> g)
{
	deque <int> :: iterator it;
	for (it = g.begin(); it != g.end(); ++it)
		cout << '\t' << *it;
	cout << '\n';
}

int main()
{
	deque <int> gquiz;
	gquiz.push_back(10);
	gquiz.push_front(20);
	gquiz.push_back(30);
	gquiz.push_front(15);
	cout << "The deque gquiz is : ";
	showdq(gquiz);

	cout << "\ngquiz.size() : " << gquiz.size();
	cout << "\ngquiz.max_size() : " << gquiz.max_size();

	cout << "\ngquiz.at(2) : " << gquiz.at(2);
	cout << "\ngquiz.front() : " << gquiz.front();
	cout << "\ngquiz.back() : " << gquiz.back();

	cout << "\ngquiz.pop_front() : ";
	gquiz.pop_front();
	showdq(gquiz);

	cout << "\ngquiz.pop_back() : ";
	gquiz.pop_back();
	showdq(gquiz);

	return 0;
}
```
<p>Output</p>
<pre>The deque gquiz is :     15    20    10    30

gquiz.size() : 4
gquiz.max_size() : 4611686018427387903
gquiz.at(2) : 10
gquiz.front() : 15
gquiz.back() : 30
gquiz.pop_front() :     20    10    30

gquiz.pop_back() :     20    10</pre>



<p><strong>Methods of Deque:</strong></p>
<ul><li><a href="https://www.geeksforgeeks.org/deque-insert-function-in-c-stl/" rel="noopener" target="_blank">deque insert() function in C++ STL</a>: Inserts an element. And returns an iterator that points to the first of the newly inserted elements.</li><li><a href="https://www.geeksforgeeks.org/deque-rbegin-function-in-c-stl/" rel="noopener" target="_blank">deque rbegin() function in C++ STL</a>: Returns a reverse iterator which points to the last element of the deque (i.e., its reverse beginning).</li><li><a href="https://www.geeksforgeeks.org/deque-rend-function-in-c-stl/" rel="noopener" target="_blank">deque rend() function in C++ STL</a>: Returns a reverse iterator which points to the position before the beginning of the deque (which is considered its reverse end).</li><li><a href="https://www.geeksforgeeks.org/deque-cbegin-in-c-stl/" rel="noopener" target="_blank">deque cbegin() in C++ STL</a>: Returns a constant iterator pointing to the first element of the container, that is, the iterator cannot be used to modify, only traverse the deque.</li><li><a href="https://www.geeksforgeeks.org/deque-max_size-function-in-c-stl/" rel="noopener" target="_blank">deque max_size() function in C++ STL</a>: Returns the maximum number of elements that a deque container can hold.</li><li><a href="https://www.geeksforgeeks.org/deque-assign-function-in-c-stl/" rel="noopener" target="_blank">deque assign() function in C++ STL</a>: Assign values to the same or different deque container.</li><li><a href="https://www.geeksforgeeks.org/deque-resize-function-in-c-stl/" rel="noopener" target="_blank">deque resize() function in C++ STL</a>: Function which changes the size of the deque.</li><li><a href="https://www.geeksforgeeks.org/dequepush_front-c-stl/" rel="noopener" target="_blank">deque::push_front() in C++ STL</a>: This function is used to push elements into a deque from the front.</li><li><a href="https://www.geeksforgeeks.org/dequepush_back-c-stl/" rel="noopener" target="_blank">deque::push_back() in C++ STL</a>: This function is used to push elements into a deque from the back.</li><li><a href="https://www.geeksforgeeks.org/dequepop_front-dequepop_back-c-stl/" rel="noopener" target="_blank">deque::pop_front() and deque::pop_back() in C++ STL</a>: <strong>pop_front()</strong> function is used to pop or remove elements from a deque from the front. <strong>pop_back()</strong> function is used to pop or remove elements from a deque from the back.</li><li><a href="https://www.geeksforgeeks.org/dequefront-dequeback-c-stl/" rel="noopener" target="_blank">deque::front() and deque::back() in C++ STL</a>: <strong>front()</strong> function is used to reference the first element of the deque container. <strong>back()</strong> function is used to reference the last element of the deque container.</li><li><a href="https://www.geeksforgeeks.org/dequeclear-dequeerase-c-stl/" rel="noopener" target="_blank">deque::clear() and deque::erase() in C++ STL</a>: <strong>clear()</strong> function is used to remove all the elements of the deque container, thus making its size 0. <strong>erase()</strong> function is used to remove elements from a container from the specified position or range.</li><li><a href="https://www.geeksforgeeks.org/dequeempty-dequesize-c-stl/" rel="noopener" target="_blank">deque::empty() and deque::size() in C++ STL</a>: <strong>empty()</strong> function is used to check if the deque container is empty or not. <strong>size()</strong> function is used to return the size of the deque container or the number of elements in the deque container.</li><li><a href="https://www.geeksforgeeks.org/dequeoperator-dequeoperator-c-stl/" rel="noopener" target="_blank">deque::operator= and deque::operator[] in C++ STL</a>:<br><strong>operator=</strong> operator is used to assign new contents to the container by replacing the existing contents. <strong>operator[]</strong> operator is used to reference the element present at position given inside the operator.</li><li><a href="https://www.geeksforgeeks.org/dequeat-dequeswap-c-stl/" rel="noopener" target="_blank">deque::at() and deque::swap() in C++ STL</a>: <strong>at()</strong> function is used reference the element present at the position given as the parameter to the function. <strong>swap()</strong> function is used to swap the contents of one deque with another deque of same type and size.</li><li><a href="https://www.geeksforgeeks.org/dequebegin-dequeend-c-stl/" rel="noopener" target="_blank">deque::begin() and deque::end in C++ STL</a>: <strong>begin() </strong>function is used to return an iterator pointing to the first element of the deque container. <strong>end()</strong> function is used to return an iterator pointing to the last element of the deque container.</li><li><a href="https://www.geeksforgeeks.org/deque-emplace_front-deque-emplace_back-cpp-stl/" rel="noopener" target="_blank">deque::emplace_front() and deque::emplace_back() in C++ STL</a>: <strong>emplace_front()</strong> function is used to insert a new element into the deque container. The new element is added to the beginning of the deque. <strong>emplace_back()</strong> function is used to insert a new element into the deque container. The new element is added to the end of the deque.</li></ul>





<br><br><br>

<a name="2a4"></a>

* arrays <br>

<a name="2a4a"></a><a name="2a4b"></a><a name="2a4c"></a>

1. at() :- This function is used to access the elements of array. 
2. get() :- This function is also used to access the elements of array. This function is not the member of array class but overloaded function from class tuple. 
3. operator[] :- This is similar to C-style arrays. This method is also used to access array elements.
```CPP
// C++ code to demonstrate working of array,
// to() and get()
#include<iostream>
#include<array> // for array, at()
#include<tuple> // for get()
using namespace std;
int main()
{
	// Initializing the array elements
	array<int,6> ar = {1, 2, 3, 4, 5, 6};

	// Printing array elements using at()
	cout << "The array elements are (using at()) : ";
	for ( int i=0; i<6; i++)
	cout << ar.at(i) << " ";
	cout << endl;

	// Printing array elements using get()
	cout << "The array elements are (using get()) : ";
	cout << get<0>(ar) << " " << get<1>(ar) << " ";
	cout << get<2>(ar) << " " << get<3>(ar) << " ";
	cout << get<4>(ar) << " " << get<5>(ar) << " ";
	cout << endl;

	// Printing array elements using operator[]
	cout << "The array elements are (using operator[]) : ";
	for ( int i=0; i<6; i++)
	cout << ar[i] << " ";
	cout << endl;

	return 0;

}
```
<p>Output</p>
<pre>The array elements are (using at()) : 1 2 3 4 5 6 
The array elements are (using get()) : 1 2 3 4 5 6 
The array elements are (using operator[]) : 1 2 3 4 5 6 </pre>
<br><br>

<a name="2a4d"></a><a name="2a4e">

4. front() :- This returns the first element of array. 
5. back() :- This returns the last element of array.
```CPP
// C++ code to demonstrate working of
// front() and back()
#include<iostream>
#include<array> // for front() and back()
using namespace std;
int main()
{
	// Initializing the array elements
	array<int,6> ar = {1, 2, 3, 4, 5, 6};

	// Printing first element of array
	cout << "First element of array is : ";
	cout << ar.front() << endl;

	// Printing last element of array
	cout << "Last element of array is : ";
	cout << ar.back() << endl;

	return 0;

}
```
<p>Output</p>
<pre>First element of array is : 1
Last element of array is : 6</pre>
<br><br>

<a name="2a4f"></a><a name="2a4g">

6. size() :- It returns the number of elements in array. This is a property that C-style arrays lack. 
7. max_size() :- It returns the maximum number of elements array can hold i.e, the size with which array is declared. The size() and max_size() return the same value.
```CPP
// C++ code to demonstrate working of
// size() and max_size()
#include<iostream>
#include<array> // for size() and max_size()
using namespace std;
int main()
{
	// Initializing the array elements
	array<int,6> ar = {1, 2, 3, 4, 5, 6};

	// Printing number of array elements
	cout << "The number of array elements is : ";
	cout << ar.size() << endl;

	// Printing maximum elements array can hold
	cout << "Maximum elements array can hold is : ";
	cout << ar.max_size() << endl;

	return 0;

}
```
<p>Output</p>
<pre>The number of array elements is : 6
Maximum elements array can hold is : 6</pre>
<br><br>

<a name="2a4h"></a>

8. swap() :- The swap() swaps all elements of one array with other.
```CPP
// C++ code to demonstrate working of swap()
#include<iostream>
#include<array> // for swap() and array
using namespace std;
int main()
{

	// Initializing 1st array
	array<int,6> ar = {1, 2, 3, 4, 5, 6};

	// Initializing 2nd array
	array<int,6> ar1 = {7, 8, 9, 10, 11, 12};

	// Printing 1st and 2nd array before swapping
	cout << "The first array elements before swapping are : ";
	for (int i=0; i<6; i++)
	cout << ar[i] << " ";
	cout << endl;
	cout << "The second array elements before swapping are : ";
	for (int i=0; i<6; i++)
	cout << ar1[i] << " ";
	cout << endl;

	// Swapping ar1 values with ar
	ar.swap(ar1);

	// Printing 1st and 2nd array after swapping
	cout << "The first array elements after swapping are : ";
	for (int i=0; i<6; i++)
	cout << ar[i] << " ";
	cout << endl;
	cout << "The second array elements after swapping are : ";
	for (int i=0; i<6; i++)
	cout << ar1[i] << " ";
	cout << endl;

	return 0;

}
```
<p>Output</p>
<pre>The first array elements before swapping are : 1 2 3 4 5 6 
The second array elements before swapping are : 7 8 9 10 11 12 
The first array elements after swapping are : 7 8 9 10 11 12 
The second array elements after swapping are : 1 2 3 4 5 6 </pre>
<br><br>


<a name="2a4i"></a><a name="2a4j">

9. empty() :- This function returns true when the array size is zero else returns false. 
10. fill() :- This function is used to fill the entire array with a particular value.
```CPP
// C++ code to demonstrate working of empty()
// and fill()
#include<iostream>
#include<array> // for fill() and empty()
using namespace std;
int main()
{

	// Declaring 1st array
	array<int,6> ar;

	// Declaring 2nd array
	array<int,0> ar1;

	// Checking size of array if it is empty
	ar1.empty()? cout << "Array empty":
		cout << "Array not empty";
	cout << endl;

	// Filling array with 0
	ar.fill(0);

	// Displaying array after filling
	cout << "Array after filling operation is : ";
	for ( int i=0; i<6; i++)
		cout << ar[i] << " ";

	return 0;

}
```
<p>Output</p>
<pre>Array empty
Array after filling operation is : 0 0 0 0 0 0 </pre>




<br><br><br>

<a name="2a5"></a>

* forward_list >= C++11 <br>

<a name="2a5a"></a>

1. assign() :- This function is used to assign values to forward list, its another variant is used to assign repeated elements

```CPP
// C++ code to demonstrate forward list
// and assign()
#include<iostream>
#include<forward_list>
using namespace std;

int main()
{
	// Declaring forward list
	forward_list<int> flist1;

	// Declaring another forward list
	forward_list<int> flist2;

	// Assigning values using assign()
	flist1.assign({1, 2, 3});

	// Assigning repeating values using assign()
	// 5 elements with value 10
	flist2.assign(5, 10);

	// Displaying forward lists
	cout << "The elements of first forward list are : ";
	for (int&a : flist1)
		cout << a << " ";
	cout << endl;
	
	cout << "The elements of second forward list are : ";
	for (int&b : flist2)
		cout << b << " ";
	cout << endl;

	return 0;
}
```
<p>Output</p>
<pre>The elements of first forward list are : 1 2 3 
The elements of second forward list are : 10 10 10 10 10</pre>
<br><br>



<a name="2a5b"></a><a name="2a5c"></a><a name="2a5d"></a>

2. push_front() :- This function is used to insert the element at the first position on forward list. The value from this function is copied to the space before first element in the container. The size of forward list increases by 1.
3. emplace_front() :- This function is similar to the previous function but in this no copying operation occurs, the element is created directly at the memory before the first element of the forward list.
4. pop_front() :- This function is used to delete the first element of list.
```CPP
// C++ code to demonstrate working of
// push_front(), emplace_front() and pop_front()
#include<iostream>
#include<forward_list>
using namespace std;

int main()
{
	// Initializing forward list
	forward_list<int> flist = {10, 20, 30, 40, 50};

	// Inserting value using push_front()
	// Inserts 60 at front
	flist.push_front(60);
	
	// Displaying the forward list
	cout << "The forward list after push_front operation : ";
	for (int&c : flist)
		cout << c << " ";
	cout << endl;
	
	// Inserting value using emplace_front()
	// Inserts 70 at front
	flist.emplace_front(70);
	
	// Displaying the forward list
	cout << "The forward list after emplace_front operation : ";
	for (int&c : flist)
	cout << c << " ";
	cout << endl;
	
	// Deleting first value using pop_front()
	// Pops 70
	flist.pop_front();
	
	// Displaying the forward list
	cout << "The forward list after pop_front operation : ";
	for (int&c : flist)
		cout << c << " ";
	cout << endl;

	return 0;
}
```
<p>Output</p>
<pre>The forward list after push_front operation : 60 10 20 30 40 50 
The forward list after emplace_front operation : 70 60 10 20 30 40 50 
The forward list after pop_front operation : 60 10 20 30 40 50</pre>
<br><br>



<a name="2a5e"></a><a name="2a5f"></a><a name="2a5g"></a>

5. insert_after() This function gives us a choice to insert elements at any position in forward list. The arguments in this function are copied at the desired position.
6. emplace_after() This function also does the same operation as above function but the elements are directly made without any copy operation.
7. erase_after() This function is used to erase elements from a particular position in the forward list.
```CPP
// C++ code to demonstrate working of
// insert_after(), emplace_after() and erase_after()
#include<iostream>
#include<forward_list>
using namespace std;

int main()
{
	// Initializing forward list
	forward_list<int> flist = {10, 20, 30} ;
	
	// Declaring a forward list iterator
	forward_list<int>::iterator ptr;

	// Inserting value using insert_after()
	// starts insertion from second position
	ptr = flist.insert_after(flist.begin(), {1, 2, 3});
	
	// Displaying the forward list
	cout << "The forward list after insert_after operation : ";
	for (int&c : flist)
		cout << c << " ";
	cout << endl;
	
	// Inserting value using emplace_after()
	// inserts 2 after ptr
	ptr = flist.emplace_after(ptr,2);
	
	// Displaying the forward list
	cout << "The forward list after emplace_after operation : ";
	for (int&c : flist)
		cout << c << " ";
	cout << endl;
	
	// Deleting value using erase.after Deleted 2
	// after ptr
	ptr = flist.erase_after(ptr);
	
	// Displaying the forward list
	cout << "The forward list after erase_after operation : ";
	for (int&c : flist)
		cout << c << " ";
	cout << endl;

	return 0;
}
```
<p>Output</p>
<pre>The forward list after insert_after operation : 10 1 2 3 20 30 
The forward list after emplace_after operation : 10 1 2 3 2 20 30 
The forward list after erase_after operation : 10 1 2 3 2 30</pre>
<br><br>


<a name="2a5h"></a><a name="2a5i"></a>

8. remove() :- This function removes the particular element from the forward list mentioned in its argument.
9. remove_if() :- This function removes according to the condition in its argument.
```CPP
// C++ code to demonstrate working of remove() and
// remove_if()
#include<iostream>
#include<forward_list>
using namespace std;

int main()
{
	// Initializing forward list
	forward_list<int> flist = {10, 20, 30, 25, 40, 40};
	
	// Removing element using remove()
	// Removes all occurrences of 40
	flist.remove(40);
	
	// Displaying the forward list
	cout << "The forward list after remove operation : ";
	for (int&c : flist)
		cout << c << " ";
	cout << endl;
	
	// Removing according to condition. Removes
	// elements greater than 20. Removes 25 and 30
	flist.remove_if([](int x){ return x>20;});
	
	// Displaying the forward list
	cout << "The forward list after remove_if operation : ";
	for (int&c : flist)
	cout << c << " ";
	cout << endl;

	return 0;

}
```
<p>Output</p>
<pre>The forward list after remove operation : 10 20 30 25 
The forward list after remove_if operation : 10 20</pre>
<br><br>


<a name="2a5j"></a>

10. splice_after() :- This function transfers elements from one forward list to other. 
```CPP
// C++ code to demonstrate working of
// splice_after()
#include<iostream>
#include<forward_list> // for splice_after()
using namespace std;

int main()
{
	// Initializing forward list
	forward_list<int> flist1 = {10, 20, 30};
	
	// Initializing second list
	forward_list<int> flist2 = {40, 50, 60};
	
	// Shifting elements from first to second
	// forward list after 1st position
	flist2.splice_after(flist2.begin(),flist1);
	
	// Displaying the forward list
	cout << "The forward list after splice_after operation : ";
	for (int&c : flist2)
	cout << c << " ";
	cout << endl;

	return 0;
}
```
<p>Output</p>
<pre>The forward list after splice_after operation : 40 10 20 30 50 60</pre>
<br><br>

<p><strong>Some more methods of forward_list:</strong></p>
<ul><li><a href="https://www.geeksforgeeks.org/forward_listfront-forward_listempty-c-stl/">front()</a>– This function is used to reference the first element of the forward list container.</li><li><a href="https://www.geeksforgeeks.org/forward_listbegin-forward_listend-c-stl/">begin()</a>– begin() function is used to return an iterator pointing to the first element of the forward list container.</li><li><a href="https://www.geeksforgeeks.org/forward_listbegin-forward_listend-c-stl/">end()</a>– end() function is used to return an iterator pointing to the last element of the list container.</li><li><a href="https://www.geeksforgeeks.org/forward_list-cbegin-in-c-stl/">cbegin()</a>– Returns a constant iterator pointing to the first element of the forward_list.</li><li><a href="https://www.geeksforgeeks.org/forward_listcend-in-c-stl-with-example/">cend()</a>– Returns a constant iterator pointing to the past-the-last element of the forward_list.</li><li><a href="https://www.geeksforgeeks.org/forward_listbefore_begin-in-c-stl/">before_begin()</a>– Returns a iterator which points to the position before the first element of the forward_list.</li><li><a href="https://www.geeksforgeeks.org/forward_listcbefore_begin-in-c-stl/">cbefore_begin()</a>– Returns a constant random access iterator which points to the position before the first element of the forward_list.</li><li><a href="https://www.geeksforgeeks.org/forward_listmax_size-in-c-stl/">max_size()</a>– Returns the maximum number of elements can be held by forward_list.</li><li><a href="https://www.geeksforgeeks.org/forward_list-resize-function-in-c-stl/">resize()</a>– Changes the size of forward_list.</li></ul>



<a name="2b"></a>
### Container Adaptors : provide a different interface for sequential containers.
<br>
<p align="center">
  <img width="987" height="585" src="images/Container_Adaptors.png">
</p>
<p align="center">
  <img width="987" height="585" src="images/Container_sequence.png">
</p>

<br>
<a name="2b1"></a>

1. empty() – Returns whether the queue is empty.
2. size() – Returns the size of the queue.
3. queue::swap() in C++ STL: Exchange the contents of two queues but the queues must be of same type, although sizes may differ.
4. queue::emplace() in C++ STL: Insert a new element into the queue container, the new element is added to the end of the queue.
5. queue::front() and queue::back() in C++ STL– front() function returns a reference to the first element of the queue. back() function returns a reference to the last element of the queue.
6. push(g) and pop() – push() function adds the element ‘g’ at the end of the queue. pop() function deletes the first element of the queue.
* queue
```CPP
// CPP code to illustrate
// Queue in Standard Template Library (STL)
#include <iostream>
#include <queue>

using namespace std;

// Print the queue
void showq(queue<int> gq)
{
	queue<int> g = gq;
	while (!g.empty()) {
		cout << '\t' << g.front();
		g.pop();
	}
	cout << '\n';
}

// Driver Code
int main()
{
	queue<int> gquiz;
	gquiz.push(10);
	gquiz.push(20);
	gquiz.push(30);

	cout << "The queue gquiz is : ";
	showq(gquiz);

	cout << "\ngquiz.size() : " << gquiz.size();
	cout << "\ngquiz.front() : " << gquiz.front();
	cout << "\ngquiz.back() : " << gquiz.back();

	cout << "\ngquiz.pop() : ";
	gquiz.pop();
	showq(gquiz);

	return 0;
}
```
<p>Output</p>
<pre>The queue gquiz is :     10    20    30

gquiz.size() : 3
gquiz.front() : 10
gquiz.back() : 30
gquiz.pop() :     20    30</pre>
<br><br>


* priority_queue
<a name="2b2"></a>

* queue
```CPP
```
<p>Output</p>
<pre></pre>
<br><br>




<a name="2b3"></a>


* priority_queue
```CPP
// CPP code to illustrate
// Queue in Standard Template Library (STL)
#include <iostream>
#include <queue>

using namespace std;

// Print the queue
void showq(queue<int> g)
{
	while (!g.empty()) {
		cout << '\t' << g.front();
		g.pop();
	}
	cout << '\n';
}

// Driver Code
int main()
{
	queue<int> gquiz;
	gquiz.push(10);
	gquiz.push(20);
	gquiz.push(30);

	cout << "The queue gquiz is : ";
	showq(gquiz);

	cout << "\ngquiz.size() : " << gquiz.size();
	cout << "\ngquiz.front() : " << gquiz.front();
	cout << "\ngquiz.back() : " << gquiz.back();

	cout << "\ngquiz.pop() : ";
	gquiz.pop();
	showq(gquiz);

	return 0;
}
```
<p>Output</p>
<pre>The priority queue gquiz is :     30    20    10    5    1

gquiz.size() : 5
gquiz.top() : 30
gquiz.pop() :     20    10    5    1</pre>
<br><br>

How to create a min heap for priority queue?
```CPP
// C++ program to demonstrate min heap
#include <iostream>
#include <queue>

using namespace std;

void showpq(
	priority_queue<int, vector<int>, greater<int> > g)
{
	while (!g.empty()) {
		cout << '\t' << g.top();
		g.pop();
	}
	cout << '\n';
}

int main()
{
	priority_queue<int, vector<int>,
					greater<int> > gquiz;
	gquiz.push(10);
	gquiz.push(30);
	gquiz.push(20);
	gquiz.push(5);
	gquiz.push(1);

	cout << "The priority queue gquiz is : ";
	showpq(gquiz);

	cout << "\ngquiz.size() : " << gquiz.size();
	cout << "\ngquiz.top() : " << gquiz.top();

	cout << "\ngquiz.pop() : ";
	gquiz.pop();
	showpq(gquiz);

	return 0;
}
```
<p>Output</p>
<pre>The priority queue gquiz is :     1    5    10    20    30

gquiz.size() : 5
gquiz.top() : 1
gquiz.pop() :     5    10    20    30</pre>
<br><br>

<p><strong>Methods of priority queue are:</strong></p>
<ul><li><a href="https://www.geeksforgeeks.org/priority_queueempty-priority_queuesize-c-stl/">priority_queue::empty() in C++ STL</a>– <strong>empty()</strong> function returns whether the queue is empty.</li><li><a href="https://www.geeksforgeeks.org/priority_queueempty-priority_queuesize-c-stl/">priority_queue::size() in C++ STL</a>– <strong>size()</strong> function returns the size of the queue.</li><li><a href="https://www.geeksforgeeks.org/priority_queuetop-c-stl/">priority_queue::top() in C++ STL</a>– Returns a reference to the top most element of the queue</li><li><a href="https://www.geeksforgeeks.org/priority_queuepush-priority_queuepop-c-stl/">priority_queue::push() in C++ STL</a><strong>– push(g)</strong> function adds the element ‘g’ at the end of the queue.</li><li><a href="https://www.geeksforgeeks.org/priority_queuepush-priority_queuepop-c-stl/">priority_queue::pop() in C++ STL</a>– <strong>pop()</strong> function deletes the first element of the queue.</li><li><a href="https://www.geeksforgeeks.org/priority_queueswap-c-stl/">priority_queue::swap() in C++ STL</a>– This function is used to swap the contents of one priority queue with another priority queue of same type and size.</li><li><a href="https://www.geeksforgeeks.org/priority_queueemplace-c-stl/">priority_queue::emplace() in C++ STL </a>– This function is used to insert a new element into the priority queue container, the new element is added to the top of the priority queue.</li><li><a href="https://www.geeksforgeeks.org/priority_queue-value_type-in-c-stl/">priority_queue value_type in C++ STL</a>– Represents the type of object stored as an element in a priority_queue. It acts as a synonym for the template parameter.</li></ul>

<br><br>

<a name="2b4"></a>

* stack
<br>The functions associated with stack are:&nbsp;<br><a href="https://www.geeksforgeeks.org/stack-empty-and-stack-size-in-c-stl/">empty()</a> – Returns whether the stack is empty – Time Complexity : O(1)&nbsp;<br><a href="https://www.geeksforgeeks.org/stack-empty-and-stack-size-in-c-stl/">size()</a> – Returns the size of the stack – Time Complexity : O(1)&nbsp;<br><a href="https://www.geeksforgeeks.org/stack-top-c-stl/">top()</a> – Returns a reference to the top most element of the stack – Time Complexity : O(1)&nbsp;<br><a href="https://www.geeksforgeeks.org/stack-push-and-pop-in-c-stl/">push(g)</a> – Adds the element ‘g’ at the top of the stack – Time Complexity : O(1)&nbsp;<br><a href="https://www.geeksforgeeks.org/stack-push-and-pop-in-c-stl/">pop()</a> – Deletes the top most element of the stack – Time Complexity : O(1)&nbsp;</p> 

```CPP
#include <iostream>
#include <stack>
using namespace std;
int main() {
	stack<int> stack;
	stack.push(21);
	stack.push(22);
	stack.push(24);
	stack.push(25);
	
		stack.pop();
	stack.pop();

	while (!stack.empty()) {
		cout << ' ' << stack.top();
		stack.pop();
	}
}
```
<p>Output</p>
<pre>22 21</pre>
<p><strong>List of functions of Stack:</strong></p>
<ul><li><a href="https://www.geeksforgeeks.org/stacktop-c-stl/">stack::top() in C++ STL</a></li><li><a href="https://www.geeksforgeeks.org/stackempty-stacksize-c-stl/">stack::empty() and stack::size() in C++ STL</a></li><li><a href="https://www.geeksforgeeks.org/stackpush-stackpop-c-stl/">stack::push() and stack::pop() in C++ STL</a></li><li><a href="https://www.geeksforgeeks.org/stackswap-c-stl/">stack::swap() in C++ STL</a></li><li><a href="https://www.geeksforgeeks.org/stackemplace-c-stl/">stack::emplace() in C++ STL</a></li><li><a href="https://www.geeksforgeeks.org/tag/cpp-stack/">Recent Articles on C++ Stack</a></li></ul>
<br><br>

<a name="2c"></a>

### Associative Containers : implement sorted data structures that can be quickly searched (O(log n) complexity).

<a name="2c1"></a>

* set 
Some basic functions associated with Set:
	<ul><li><a href="https://www.geeksforgeeks.org/setbegin-setend-c-stl/">begin()</a> – Returns an iterator to the first element in the set.</li><li><a href="https://www.geeksforgeeks.org/setbegin-setend-c-stl/">end()</a> – Returns an iterator to the theoretical element that follows last element in the set.</li><li><a href="https://www.geeksforgeeks.org/setsize-c-stl/">size()</a> – Returns the number of elements in the set.</li><li><a href="https://www.geeksforgeeks.org/set-max_size-function-in-c-stl/">max_size()</a> – Returns the maximum number of elements that the set can hold.</li><li><a href="https://www.geeksforgeeks.org/setempty-c-stl/">empty()</a> – Returns whether the set is empty.</li></ul>

```CPP
#include <iostream>
#include <iterator>
#include <set>

using namespace std;

int main()
{
	// empty set container
	set<int, greater<int> > s1;

	// insert elements in random order
	s1.insert(40);
	s1.insert(30);
	s1.insert(60);
	s1.insert(20);
	s1.insert(50);
	
	// only one 50 will be added to the set
	s1.insert(50);
	s1.insert(10);

	// printing set s1
	set<int, greater<int> >::iterator itr;
	cout << "\nThe set s1 is : \n";
	for (itr = s1.begin(); itr != s1.end(); itr++)
	{
		cout << *itr<<" ";
	}
	cout << endl;

	// assigning the elements from s1 to s2
	set<int> s2(s1.begin(), s1.end());

	// print all elements of the set s2
	cout << "\nThe set s2 after assign from s1 is : \n";
	for (itr = s2.begin(); itr != s2.end(); itr++)
	{
		cout << *itr<<" ";
	}
	cout << endl;

	// remove all elements up to 30 in s2
	cout
		<< "\ns2 after removal of elements less than 30 :\n";
	s2.erase(s2.begin(), s2.find(30));
	for (itr = s2.begin(); itr != s2.end(); itr++) {
		cout <<*itr<<" ";
	}

	// remove element with value 50 in s2
	int num;
	num = s2.erase(50);
	cout << "\ns2.erase(50) : ";
	cout << num << " removed\n";
	for (itr = s2.begin(); itr != s2.end(); itr++)
	{
		cout <<*itr<<" ";
	}

	cout << endl;

	// lower bound and upper bound for set s1
	cout << "s1.lower_bound(40) : \n"
		<< *s1.lower_bound(40)
		<< endl;
	cout << "s1.upper_bound(40) : \n"
		<< *s1.upper_bound(40)
		<< endl;

	// lower bound and upper bound for set s2
	cout << "s2.lower_bound(40) :\n"
		<< *s2.lower_bound(40)
		<< endl;
	cout << "s2.upper_bound(40) : \n"
		<< *s2.upper_bound(40)
		<< endl;

	return 0;
}
```
<p>Output</p>
<pre>The set s1 is : 
60 50 40 30 20 10 

The set s2 after assign from s1 is : 
10 20 30 40 50 60 

s2 after removal of elements less than 30 :
30 40 50 60 
s2.erase(50) : 1 removed
30 40 60 
s1.lower_bound(40) : 
40
s1.upper_bound(40) : 
30
s2.lower_bound(40) :
40
s2.upper_bound(40) : 
60</pre>
<p><strong>Methods of set:</strong></p>
<ul><li><a href="https://www.geeksforgeeks.org/setbegin-setend-c-stl/">begin()</a> – Returns an iterator to the first element in the set.</li><li><a href="https://www.geeksforgeeks.org/setbegin-setend-c-stl/">end()</a> – Returns an iterator to the theoretical element that follows last element in the set.</li><li><a href="https://www.geeksforgeeks.org/setrbegin-and-setrend-in-c-stl/">rbegin()</a>– Returns a reverse iterator pointing to the last element in the container.</li><li><a href="https://www.geeksforgeeks.org/setrbegin-and-setrend-in-c-stl/">rend()</a>– Returns a reverse iterator pointing to the theoretical element right before the first element in the set container.</li><li><a href="https://www.geeksforgeeks.org/set-crbegin-and-crend-function-in-c-stl/">crbegin()</a>– Returns a constant iterator pointing to the last element in the container.</li><li><a href="https://www.geeksforgeeks.org/set-crbegin-and-crend-function-in-c-stl/">crend() </a>– Returns a constant iterator pointing to the position just before the first element in the container.</li><li><a href="https://www.geeksforgeeks.org/set-cbegin-and-cend-function-in-c-stl/">cbegin()</a>– Returns a constant iterator pointing to the first element in the container.</li><li><a href="https://www.geeksforgeeks.org/set-cbegin-and-cend-function-in-c-stl/">cend() </a>– Returns a constant iterator pointing to the position past the last element in the container.</li><li><a href="https://www.geeksforgeeks.org/setsize-c-stl/">size()</a> – Returns the number of elements in the set.</li><li><a href="https://www.geeksforgeeks.org/set-max_size-function-in-c-stl/">max_size()</a> – Returns the maximum number of elements that the set can hold.</li><li><a href="https://www.geeksforgeeks.org/setempty-c-stl/">empty()</a> – Returns whether the set is empty.</li><li><a href="https://www.geeksforgeeks.org/set-insert-function-in-c-stl/">insert(const g)</a> – Adds a new element ‘g’ to the set.</li><li><a href="https://www.geeksforgeeks.org/set-insert-function-in-c-stl/">iterator insert (iterator position, const g)</a> – Adds a new element ‘g’ at the position pointed by iterator.</li><li><a href="https://www.geeksforgeeks.org/seterase-c-stl/">erase(iterator position)</a> – Removes the element at the position pointed by the iterator.</li><li><a href="https://www.geeksforgeeks.org/seterase-c-stl/">erase(const g)</a>– Removes the value ‘g’ from the set.</li><li><a href="https://www.geeksforgeeks.org/setclear-c-stl/">clear()</a> – Removes all the elements from the set.</li><li><a href="https://www.geeksforgeeks.org/setkey_comp-in-c-stl/">key_comp()</a> / <a href="https://www.geeksforgeeks.org/set-value_comp-function-in-c-stl/">value_comp()</a> – Returns the object that determines how the elements in the set are ordered (‘&lt;‘ by default).</li><li><a href="https://www.geeksforgeeks.org/set-find-function-in-c-stl/">find(const g)</a> – Returns an iterator to the element ‘g’ in the set if found, else returns the iterator to end.</li><li><a href="https://www.geeksforgeeks.org/set-count-function-in-c-stl/">count(const g)</a> – Returns 1 or 0 based on the element ‘g’ is present in the set or not.</li><li><a href="https://www.geeksforgeeks.org/set-lower_bound-function-in-c-stl/">lower_bound(const g)</a> – Returns an iterator to the first element that is equivalent to ‘g’ or definitely will not go before the element ‘g’ in the set.</li><li><a href="https://www.geeksforgeeks.org/set-upper_bound-function-in-c-stl/">upper_bound(const g)</a> – Returns an iterator to the first element that will go after the element ‘g’ in the set.</li><li><a href="https://www.geeksforgeeks.org/set-equal_range-function-in-c-stl/">equal_range()</a>– The function returns an iterator of pairs. (key_comp). The pair refers to the range that includes all the elements in the container which have a key equivalent to k.</li><li><a href="https://www.geeksforgeeks.org/setemplace-c-stl/">emplace()</a>– This function is used to insert a new element into the set container, only if the element to be inserted is unique and does not already exists in the set.</li><li><a href="https://www.geeksforgeeks.org/set-emplace_hint-function-in-c-stl/">emplace_hint()</a>– Returns an iterator pointing to the position where the insertion is done. If the element passed in the parameter already exists, then it returns an iterator pointing to the position where the existing element is.</li><li><a href="https://www.geeksforgeeks.org/setswap-c-stl/">swap()</a>– This function is used to exchange the contents of two sets but the sets must be of same type, although sizes may differ.</li><li><a href="https://www.geeksforgeeks.org/set-operator-in-c-stl/">operator= </a>– The ‘=’ is an operator in C++ STL which copies (or moves) a set to another set and set::operator= is the corresponding operator function.</li><li><a href="https://www.geeksforgeeks.org/set-get_allocator-in-c-stl/">get_allocator()</a>– Returns the copy of the allocator object associated with the set.</li></ul>

<br><br>

<a name="2c2"></a>

* multiset

Some Basic Functions associated with multiset: 
<br><a href="https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/">begin()</a> – Returns an iterator to the first element in the multiset&nbsp;<br><a href="https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/">end()</a> – Returns an iterator to the theoretical element that follows last element in the multiset&nbsp;<br><a href="https://www.geeksforgeeks.org/multiset-size-in-c-stl-with-examples/">size()</a> – Returns the number of elements in the multiset&nbsp;<br><a href="https://www.geeksforgeeks.org/multiset-max_size-in-c-stl/">max_size()</a> – Returns the maximum number of elements that the multiset can hold&nbsp;<br><a href="https://www.geeksforgeeks.org/multiset-empty-function-in-c-stl/">empty()</a> – Returns whether the multiset is empty</p>

```CPP
#include <iostream>
#include <set>
#include <iterator>

using namespace std;

int main()
{
	// empty multiset container
	multiset <int, greater <int> > gquiz1;	

	// insert elements in random order
	gquiz1.insert(40);
	gquiz1.insert(30);
	gquiz1.insert(60);
	gquiz1.insert(20);
	gquiz1.insert(50);
	
	// 50 will be added again to
	// the multiset unlike set
	gquiz1.insert(50);
	gquiz1.insert(10);

	// printing multiset gquiz1
	multiset <int, greater <int> > :: iterator itr;
	cout << "\nThe multiset gquiz1 is : \n";
	for (itr = gquiz1.begin(); itr
		!= gquiz1.end(); ++itr)
	{
		cout << *itr << " ";
	}
	cout << endl;

	// assigning the elements from gquiz1 to gquiz2
	multiset <int> gquiz2(gquiz1.begin()
						, gquiz1.end());

	// print all elements of the multiset gquiz2
	cout << "\nThe multiset gquiz2 \n"
			"after assign from gquiz1 is : \n";
	for (itr = gquiz2.begin(); itr
		!= gquiz2.end(); ++itr)
	{
		cout << *itr <<" ";
	}
	cout << endl;

	// remove all elements up to element
// with value 30 in gquiz2
	cout << "\ngquiz2 after removal \n"
			"of elements less than 30 : \n";
	gquiz2.erase(gquiz2.begin()
				, gquiz2.find(30));
	for (itr = gquiz2.begin(); itr
		!= gquiz2.end(); ++itr)
	{
		cout << *itr << " " ;
	}

	// remove all elements with value 50 in gquiz2
	int num;
	num = gquiz2.erase(50);
	cout << "\ngquiz2.erase(50) : \n";
	cout << num << " removed \n" ;
	for (itr = gquiz2.begin(); itr
		!= gquiz2.end(); ++itr)
	{
		cout << *itr << " ";
	}

	cout << endl;

	//lower bound and upper bound for multiset gquiz1
	cout << "\ngquiz1.lower_bound(40) : \n"
		<< *gquiz1.lower_bound(40) << endl;
	cout << "gquiz1.upper_bound(40) : \n"
		<< *gquiz1.upper_bound(40) << endl;

	//lower bound and upper bound for multiset gquiz2
	cout << "gquiz2.lower_bound(40) : \n"
		<< *gquiz2.lower_bound(40) << endl;
	cout << "gquiz2.upper_bound(40) : \n"
		<< *gquiz2.upper_bound(40) << endl;
		
		return 0;

}
```
<p>Output</p>
<pre>The multiset gquiz1 is : 
60 50 50 40 30 20 10 

The multiset gquiz2 
after assign from gquiz1 is : 
10 20 30 40 50 50 60 

gquiz2 after removal 
of elements less than 30 : 
30 40 50 50 60 
gquiz2.erase(50) : 
2 removed 
30 40 60 

gquiz1.lower_bound(40) : 
40
gquiz1.upper_bound(40) : 
30
gquiz2.lower_bound(40) : 
40
gquiz2.upper_bound(40) : 
60</pre>


Removing Element from multiset which have same value
1. erase() – Remove all instance of element from multiset having same value
2. erase(a.find()) – Remove only one instance of element from multiset having same value
```CPP
#include <bits/stdc++.h>
using namespace std;

int main()
{
	multiset<int> a;
	a.insert(10);
	a.insert(10);
	a.insert(10);

	// it will give output 3
	cout << a.count(10) << endl;

	// removing single instance from multiset

	// it will remove only one value of
	// 10 from multiset
	a.erase(a.find(10));
	
	// it will give output 2
	cout << a.count(10) << endl;

	// removing all instance of element from multiset
	// it will remove all instance of value 10
	a.erase(10);

	// it will give output 0 because all
	// instance of value is removed from
	// mulitset
	cout << a.count(10)
		<< endl;

	return 0;
}
```
<p>Output</p>
<pre>3
2
0</pre>

<p><strong>List of functions of Multiset:</strong>&nbsp;</p>
<ul><li><a href="https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/">begin()</a> – Returns an iterator to the first element in the multiset.</li><li><a href="https://www.geeksforgeeks.org/multiset-begin-and-end-function-in-c-stl/">end()</a> – Returns an iterator to the theoretical element that follows last element in the multiset.</li><li><a href="https://www.geeksforgeeks.org/multiset-size-in-c-stl-with-examples/">size()</a> – Returns the number of elements in the multiset.</li><li><a href="https://www.geeksforgeeks.org/multiset-max_size-in-c-stl/">max_size()</a>– Returns the maximum number of elements that the multiset can hold.</li><li><a href="https://www.geeksforgeeks.org/multiset-empty-function-in-c-stl/">empty()</a> – Returns whether the multiset is empty.</li><li><a href="https://www.geeksforgeeks.org/multiset-insert-function-in-c-stl/">pair insert(const g)</a> – Adds a new element ‘g’ to the multiset.</li><li><a href="https://www.geeksforgeeks.org/multiset-insert-function-in-c-stl/">iterator insert (iterator position,const g)</a> – Adds a new element ‘g’ at the position pointed by iterator.</li><li><a href="https://www.geeksforgeeks.org/multiset-erase-in-c-stl/">erase(iterator position)</a>– Removes the element at the position pointed by the iterator.</li><li><a href="https://www.geeksforgeeks.org/multiset-erase-in-c-stl/">erase(const g)</a>– Removes the value ‘g’ from the multiset.</li><li><a href="https://www.geeksforgeeks.org/multiset-clear-function-in-c-stl/">clear()</a>– Removes all the elements from the multiset.</li><li><a href="https://www.geeksforgeeks.org/multiset-key_comp-function-in-c-stl/">key_comp()</a> / <a href="https://www.geeksforgeeks.org/multiset-value_comp-method-in-c-stl/">value_comp()</a>– Returns the object that determines how the elements in the multiset are ordered (‘&lt;‘ by default).</li><li><a href="https://www.geeksforgeeks.org/multiset-find-function-in-c-stl/">find(const g)</a>– Returns an iterator to the element ‘g’ in the multiset if found, else returns the iterator to end.</li><li><a href="https://www.geeksforgeeks.org/multiset-count-function-in-c-stl/">count(const g)</a>– Returns the number of matches to element ‘g’ in the multiset.</li><li><a href="https://www.geeksforgeeks.org/multiset-lower_bound-in-cpp-stl-with-examples/">lower_bound(const g)</a>– Returns an iterator to the first element that is equivalent to ‘g’ or definitely will not go before the element ‘g’ in the multiset if found, else returns the iterator to end.</li><li><a href="https://www.geeksforgeeks.org/multiset-upper_bound-in-cpp-stl-with-examples/">upper_bound(const g)</a>– Returns an iterator to the first element that is equivalent to ‘g’ or definitely will go after the element ‘g’ in the multiset if found, else returns the iterator to end.</li><li><a href="https://www.geeksforgeeks.org/multisetswap-c-stl/">multiset::swap()</a>– This function is used to exchange the contents of two multisets but the sets must be of same type, although sizes may differ.</li><li><a href="https://www.geeksforgeeks.org/multisetoperator-c-stl/">multiset::operator=</a>– This operator is used to assign new contents to the container by replacing the existing contents.</li><li><a href="https://www.geeksforgeeks.org/multisetemplace-c-stl/">multiset::emplace()</a>– This function is used to insert a new element into the multiset container.</li><li><a href="https://www.geeksforgeeks.org/multiset-equal_range-function-in-c-stl/">multiset equal_range()</a>– Returns an iterator of pairs. The pair refers to the range that includes all the elements in the container which have a key equivalent to k.</li><li><a href="https://www.geeksforgeeks.org/multiset-emplace_hint-function-in-c-stl/">multiset::emplace_hint() </a>– Inserts a new element in the multiset.</li><li><a href="https://www.geeksforgeeks.org/multiset-rbegin-and-rend-function-in-c-stl/">multiset::rbegin()</a>– Returns a reverse iterator pointing to the last element in the multiset container.</li><li><a href="https://www.geeksforgeeks.org/multiset-rbegin-and-rend-function-in-c-stl/">multiset::rend()</a>– Returns a reverse iterator pointing to the theoretical element right before the first element in the multiset container.</li><li><a href="https://www.geeksforgeeks.org/multiset-cbegin-and-cend-function-in-c-stl/">multiset::cbegin()</a>– Returns a constant iterator pointing to the first element in the container.</li><li><a href="https://www.geeksforgeeks.org/multiset-cbegin-and-cend-function-in-c-stl/">multiset::cend()</a>– Returns a constant iterator pointing to the position past the last element in the container.</li><li><a href="https://www.geeksforgeeks.org/multiset-crbegin-and-crend-function-in-c-stl/">multiset::crbegin()</a>– Returns a constant reverse iterator pointing to the last element in the container.</li><li><a href="https://www.geeksforgeeks.org/multiset-crbegin-and-crend-function-in-c-stl/">multiset::crend()</a>– Returns a constant reverse iterator pointing to the position just before the first element in the container.</li><li><a href="https://www.geeksforgeeks.org/multiset-get_allocator-function-in-c-stl/">multiset::get_allocator()</a>– Returns a copy of the allocator object associated with the multiset.</li></ul>