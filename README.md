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
            1. [Test](#f)
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
        1. [list](#2a2)
        1. [deque](#2a3)
        1. [arrays](#2a4)
        1. [forward_list >= C++11](#2a5)
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


<a name="f"></a>
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


<a name="#1a3b1"></a><a name="#1a3b2"></a>

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

<a name="#1a3b4"></a><a name="#1a3b3"></a>

3. next_permutation(first_iterator, last_iterator) – This modified the vector to its next permutation.
4. prev_permutation(first_iterator, last_iterator) – This modified the vector to its previous permutation. 


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

<a name="#1a3b5"></a>

5. distance(first_iterator,desired_position) – It returns the distance of desired position from the first iterator.This function               is very useful while finding the index.


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


<a name="#1a4"></a>
* Useful Array algorithms
  * all_of()<br> This function operates on whole range of array elements and can save time to run a loop to check each elements one by one. It checks for a given property on every element and returns true when each element in range satisfies specified property, else returns false.
<br>
<br>
  * any_of() <br> This function checks for a given range if there’s even one element satisfying a given property mentioned in function. Returns true if at least one element satisfies the property else returns false.
<br>
  * none_of() <br>This function returns true if none of elements satisfies the given condition else returns false.
  <br>
<br>
  * copy_n() <br>
copy_n() copies one array elements to new array. This type of copy creates a deep copy of array. This function takes 3 arguments, source array name, size of array and the target array name.
<br>
<br>
  * iota() <br>This function is used to assign continuous values to array. This function accepts 3 arguments, the array name, size, and the starting number.

<br>
<br>



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
  * partition(beg, end, condition) :<br>- This function is used to partition the elements on basis of condition mentioned in its arguments.
  * is_partitioned(beg, end, condition) :<br>- This function returns boolean true if container is partitioned else returns false.
<br>
<br>
  * stable_partition(beg, end, condition) :<br>- This function is used to partition the elements on basis of condition mentioned in its arguments in such a way that the relative order of the elements is preserved..
  * partition_point(beg, end, condition) :<br>- This function returns an iterator pointing to the partition point of container i.e. the first element in the partitioned range [beg,end) for which condition is not true. The container should already be partitioned for this function to work.
<br>
<br>
  * partition_copy(beg, end, beg1, beg2, condition) :<br>- This function copies the partitioned elements in the differenet containers mentioned in its arguments. It takes 5 arguments. Beginning and ending position of container, beginning position of new container where elements have to be copied (elements returning true for condition), beginning position of new container where other elements have to be copied (elements returning false for condition) and the condition. Resizing new containers is necessary for this function.

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


<a name="#1b"></a>
### Numeric
<a name="#1b1"></a>
* valarray class

<a name="#1b1a"></a>
Public member functions in valarray class :
1. apply() :- This function applies the manipulation given in its arguments to all the valarray elements at once and returns a new valarray with manipulated values.
<a name="#1b1b"></a>
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


<a name="#1b1c"></a>
3. min() :- This function returns the smallest element of valarray.
<a name="#1b1d"></a>
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


<a name="#1b1e"></a>
5. shift() :- This function returns the new valarray after shifting elements by the number mentioned in its argument. If the number is positive, left-shift is applied, if number is negative, right-shift is applied.

<a name="#1b1f"></a>
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

<a name="#1b1g"></a>
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