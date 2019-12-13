
## Array Data Structure
* [reference1](https://www.geeksforgeeks.org/array-data-structure/) 
* [reference2](https://www.geeksforgeeks.org/arrays-in-java/)
* [reference3](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/arrays.html)


1) Array is collections of item store in contiguous memory locations.
2) Array can contains **primitives data types** as well as **objects of a class** depending on the definition of array.
3) In case of primitives data types, the actual values are stored in contiguous memory locations.
4) In case of objects of a class, the actual objects are stored in heap segment.
```java
Example : 
int intArray[];    //declaring array
intArray = new int[20];  // allocating memory to array
 int[] intArray = new int[]{ 1,2,3,4,5,6,7,8,9,10 }; 
 // Declaring array literal (if size of array is already known)
``` 
5) The direct **superclass** of an array type is **Object**.
6) Every array type implements the interfaces Cloneable and java.io.Serializable.
7) Multidimensional(Jagged) arrays - arrays of arrays with each element of the array holding the reference of other array. 
```Java
Example
int arr[][] = { {2,7,9},{3,6,1},{7,4,2} }; 
```
9) When you clone a single dimensional array, such as Object[], a “deep copy” is performed
10) A clone of a multidimensional array (like Object[][]) is a “shallow copy” however, which is to say that it creates only a single new array with each element array a reference to an original element array but subarrays are shared.
11) Array is static in size i.e of fixed length.
12) [Array questions](https://javahungry.blogspot.com/2019/03/array-interview-questions-and-answers-in-java.html?_sm_au_=iHV7HfSQq0PqmZMPBJ3vvK7RJCBJt)
13) Memory usage
  Every 1-dimensional array has a header of size 8 bytes and another 4 bytes for storing the size of the array. 
  Then, it has the storage for the elements which can be calculated by multiplying the size of the array by the data type. 
  If the final value is not a multiple of 8 bytes, padding is added to make it a multiple of 8.

For the example above where we have array numbers of type int and size 10, that means we have:

12 bytes for the header object

10 elements times 4 bytes (int size)

4 bytes padding

So the size of the array is 12 + 10*4 + 4 = 56 bytes.

Since a two-dimensional array is an array of arrays, we can first calculate the array and then its arrays. So for the table example above, we have an array of 10 elements which is 56 bytes. Each element is also an array of 10 elements so we have 10 times 56. So in total we have 56 + (10 * 56) = 616 bytes

14)If we want to remove a value or insert a value in the middle, it can be costly. For example, if we have an array of size 10 and we have values for elements index 0 through 8 and we want to insert a value after index 5, we have to move elements at index 6 through 8 one over to make the space for the new value. So we would first copy element at index 8 to index 9, then copy index 7 to 8, then index 6 to index 7 and then finally we could assign the new value to index 6. 
In the same way, if we want to delete a value but not leave an element without a value, we need to move all the values over. The longer the array and the more number of elements that have to be copied over, the longer it will take and thus impact the performance of the program. In addition, since the size of the array is fixed, if we need to add more elements than the size of the array, we need to create a new bigger array and copy the elements over. The more elements that have to be copied, the longer it will take. 
