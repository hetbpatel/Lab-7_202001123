# Lab-7_202001123

## ID - 202001123

## Name - Het Patel

## Section-A

### Equivalence Partitioning Test Cases:

| ID | Day | Month | Year| Expected Output |
|----|-----|-------|-----|-----------------|
|  1 | 5   |  9    |2002 | 04-09-2002      |
|  2 | 7   |  5    |2005 | 06-05-2005      |
|  3 | 32  |  4   |2004 | An error message |
|  4| 1 | 3 | 2001 | 28-2-2001|
|  5| 1 | 3 | 2000 | 29-2-2001|
|6| 1 | 1 | 1900 | Invalid Date |
| 7| 1| 1| 2000| 31-12-1999|
| 8| 13| 4|2023| Invalid Date |
|9| 5|12|2013| 4-12-2013|
|10| 32|11|2002| An error message|


### Equivalence Class

Day: <br />

| Partition ID | Range | Status |
| --- | --- | --- |
| E1 | Between 1 and 28 | Valid |
| E2 | Less than 1 | Invalid |
| E3 | Greater than 31 | Invalid |
| E4 | Equals 30 | Valid |
| E5 | Equals 29 | Valid for leap year |
| E6 | Equals 31 | Valid |

Month: <br />

| Partition ID | Range | Status |
| --- | --- | --- |
| E7 | Between 1 and 12 | Valid |
| E8 | Less than 1 | Invalid |
| E9 | Greater than 12 | Invalid |

Year: <br />

| Partition ID | Range | Status |
| --- | --- | --- |
| E10 | Between 1900 and 2015 | Valid |
| E11 | Less than 1 | Invalid |
| E12 | Greater than 2015 | Invalid |


## Program 1:

```
THE MAIN FILE

package tests

public class unittesting {

    // public int square(int n)

    // {

        // return n*n

        // }

    public static int linearSearch(int v, int[] a) {

        int i = 0

        while (i < a.length) {

            if (a[i] == v) {

                return i
            }

            i++
        }

        return -1
    }

    public static int countItem(int v, int[] a) {

        int count = 0

        for (int i=0
             i < a.length
             i++) {

            if (a[i] == v) {

                count++
            }

        }

        return count
    }

    public static int binarySearch(int v, int[] a) {

        int lo = 0

        int hi = a.length - 1

        while (lo <= hi) {

            int mid = (lo + hi) / 2

            if (v == a[mid]) {

                return mid
            } else if (v < a[mid]) {

                hi = mid - 1
            } else {

                lo = mid + 1
            }

        }

        return -1
    }

    public static final int ** *EQUILATERAL*** = 0

    public static final int ** *ISOSCELES*** = 1

    public static final int ** *SCALENE*** = 2

    public static final int ** *INVALID*** = 3

    public static int triangle(int a, int b, int c) {

        if (a >= b + c | | b >= a + c | | c >= a + b) {

            return ***INVALID***
        }

        if (a == b & & b == c) {

            return ***EQUILATERAL***
        }

        if (a == b | | a == c | | b == c) {

            return ***ISOSCELES***
        }

        return ***SCALENE***
    }

    public static boolean prefix(String s1, String s2) {

        if (s1.length() > s2.length()) {

            return false
        }

        for (int i=0
             i < s1.length()
             i++) {

            if (s1.charAt(i) != s2.charAt(i)) {

                return false
            }

        }

        return true
    }

    // public static int triangleP6(float a, float b, float c) {

        // if (a >= b + c | | b >= a + c | | c >= a + b) {

            // System.out.println("INVALID")

            // }

        // if (a == b & & b == c) {

            // System.out.println("EQUILATERAL")

            // return EQUILATERAL

            // }

        // if (a == b | | a == c | | b == c) {

            // System.out.println("ISOSCELES")

            // return ISOSCELES

            // }

        // System.out.println("SCALENE")

        // }

}
```

**Equivalence partition for linear search**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| [2, 4, 6, 8, 10],v = 2 | 0 |
| [1, 3, 5, 7, 9],v = 2 | -1 |
| [2, 4, 6, 8, 10],v = 11 | -1 |
| [-100, 100] | 0 |
| [1,2,3,4,5,6],v = 6 | 5 |
| [],v = 10 | -1 |
| NULL,v = 111 | -1 |

**Boundary value analysis**
| Tester Action and Input Data | Expected Outcome |
|------------------------------|------------------|
| NULL | -1 |
| [],v = 5 | -1 |
| [5],v = 5 | 0 |
| [5],v = 60 | -1 |
| [3,5],v = 3 | 0 |
| [3,5],v = 5 | 1 |
| [3,5],v = 14 | -1 |
| [1,3,5],v = 1 | 0 |
| [1,3,5],v = 5 | 2 |
| [1,3,5],v = 10 | -1 |
|[1,2,3,4,5,6,7,8,9,1,0,11,111],v = 1| 0 |
|[1,2,3,4,5,6,7,8,9,1,0,11,111],v = 111| 12 |
|[1,2,3,4,5,6,7,8,9,1,0,11,111],v = 1111| -1 |

**Junit testing-1:**

![alt](https://github.com/hetbpatel/Lab-7_202001123/blob/b4a4a731dbc18ed2726961d868ab0e7c5326ab64/p1.jpeg)

```

package tests;

import org.junit.Test;

import org.junit.FixMethodOrder;

import org.junit.runners.MethodSorters;

import static org.junit.Assert.*;

//import org.junit.Test;

*

@FixMethodOrder
*(*MethodSorters*.***NAME_ASCENDING***)

public class linearsearchtest {

    *@Test*

public void test1() {

unittesting obj1= new unittesting();

int[] n={12,24,2,89,34,45};

int output_f = obj1.*linearSearch*(12, n);

*assertEquals*(0, output_f);

}

    *@Test*

public void test2() {

unittesting obj1= new unittesting();

int[] n={12,24,2,89,34,45};

int output_f = obj1.*linearSearch*(24, n);

*assertEquals*(1, output_f);

}

    *@Test*

public void test3() {

unittesting obj1= new unittesting();

int[] n={12,24,2,89,34,45};

int output_f = obj1.*linearSearch*(45, n);

*assertEquals*(10, output_f);

}

}
```

**Junit testing-2:**

![alt](https://github.com/hetbpatel/Lab-7_202001123/blob/b4a4a731dbc18ed2726961d868ab0e7c5326ab64/p2.jpeg)

```
package tests;

import org.junit.Test;

import org.junit.FixMethodOrder;

import org.junit.runners.MethodSorters;

import static org.junit.Assert.*;

import org.junit.Test;

*

@FixMethodOrder
*(*MethodSorters*.***NAME_ASCENDING***)

public class countitemtest {

    *@Test*

public void test1() {

unittesting obj1= new unittesting();

int[] n={12,24,2,89,34,45};

int output_f = obj1.*countItem*(12, n);

*assertEquals*(1, output_f);

}

    *@Test*

public void test2() {

unittesting obj1= new unittesting();

int[] n={12,24,2,89,34,45};

int output_f = obj1.*countItem*(24, n);

*assertEquals*(0, output_f);

}

    *@Test*

public void test3() {

unittesting obj1= new unittesting();

int[] n={12,24,2,89,89,45};

int output_f = obj1.*countItem*(89, n);

*assertEquals*(2, output_f);

}

}

```

**Junit testing-3:**

![alt](https://github.com/hetbpatel/Lab-7_202001123/blob/b4a4a731dbc18ed2726961d868ab0e7c5326ab64/p3.jpeg)

```
package tests;

import static org.junit.Assert.*;

import org.junit.Test;

public class binarySearchtest {

    @Test

    public void test1() {

        unittesting obj1 = new unittesting();

        int[] n = { 1, 2, 3, 4, 5, 6, 7, 8 };

        int output_f = obj1.binarySearch(12, n);

        assertEquals(0, output_f);

    }

    @Test

    public void test2() {

        unittesting obj1 = new unittesting();

        int[] n = { 11, 12, 13, 14, 15, 16, 17 };

        int output_f = obj1.binarySearch(14, n);

        assertEquals(3, output_f);

    }

    @Test

    public void test3() {

        unittesting obj1 = new unittesting();

        int[] n = { 11, 12, 13, 14, 15, 16, 17 };

        int output_f = obj1.binarySearch(11, n);

        assertEquals(4, output_f);

    }

}

```

**Junit testing-4:**

![alt](https://github.com/hetbpatel/Lab-7_202001123/blob/b4a4a731dbc18ed2726961d868ab0e7c5326ab64/p4.jpeg)

```
package tests;

import static org.junit.Assert.*;

import org.junit.Test;

public class triangletest {

    @Test

    public void test1() {

        unittesting obj1 = new unittesting();

        // int[] n={12,24,2,89,34,45};

        int output_f = obj1.triangle(1, 1, 1);

        assertEquals(0, output_f);

    }

    @Test

    public void test2() {

        unittesting obj1 = new unittesting();

        // int[] n={12,24,2,89,34,45};

        int output_f = obj1.triangle(4, 4, 2);

        assertEquals(1, output_f);

    }

    @Test

    public void test3() {

        unittesting obj1 = new unittesting();

        // int[] n={12,24,2,89,34,45};

        int output_f = obj1.triangle(1, 2, 3);

        assertEquals(0, output_f);

    }

    @Test

    public void test4() {

        unittesting obj1 = new unittesting();

        // int[] n={12,24,2,89,34,45};

        int output_f = obj1.triangle(12, 5, 13);

        assertEquals(1, output_f);

    }

}

```

**Junit testing-5:**
![alt](https://github.com/hetbpatel/Lab-7_202001123/blob/b4a4a731dbc18ed2726961d868ab0e7c5326ab64/p5.jpeg)

```
package tests;

import static org.junit.Assert.*;

import org.junit.Test;

public class prefixtest {

    @Test

    public void test1() {

        unittesting obj1 = new unittesting();

        // int[] n={1,2,3,4,5,6,7,8};

        boolean output_f = obj1.prefix("maharth", "maharththakar");

        assertEquals(true, output_f);

    }

    @Test

    public void test2() {

        unittesting obj1 = new unittesting();

        // int[] n={11,12,13,14,15,16,17};

        boolean output_f = obj1.prefix("hihello", "hi");

        assertEquals(true, output_f);

    }

    @Test

    public void test3() {

        unittesting obj1 = new unittesting();

        // int[] n={11,12,13,14,15,16,17};

        boolean output_f = obj1.prefix("hello", "helluhow");

        assertEquals(true, output_f);

    }

}

```

<br>

## Program 2:

The function countItem returns the number of times a value v appears in an array of integers a.

<br>

```
int countItem(int v, int a[]){
  int count = 0;
  for (int i = 0; i < a.length; i++){
    if (a[i] == v)
    count++;
  }
  return (count);
}
```
**Equivalence Partitioning:**

| Tester Action and Input Data     | Expected Outcome      |
| ------------- | :---: |
| v is present in a        | Number of times v appears in a         |
| v is not present in a         | 0         |

**Boundary Value Analysis:**

| Tester Action and Input Data     | Expected Outcome      |
| ------------- | :---: |
| Empty array a        | 0         |
| v is present once in a         | 1         |
| v is present multiple times in a        | Number of times v appears in a         |
| v is present at the first index of a         | 1         |
| v is present at the last index of a        | 1        |
| v is not present in a         | 0        |



<br>

## Program 3:
The function binarySearch searches for a value v in an ordered array of integers a. 
<br>
If v appears in the array a, then the function returns an index i, such that a[i] == v; otherwise, -1 is returned.<br>
Assumption: the elements in the array a are sorted in non-decreasing order.
<br>

```
int binarySearch(int v, int a[]){
  int lo,mid,hi;
  lo = 0;
  hi = a.length-1;
  while (lo <= hi){
    mid = (lo+hi)/2;
    if (v == a[mid])
      return (mid);
    else if (v < a[mid])
      hi = mid-1;
    else
      lo = mid+1;
  }
  return(-1);
}
```

**Equivalence Partitioning:**

| Tester Action and Input Data     | Expected Outcome      |
| ------------- | :---: |
| v is present in a        | Index of v         |
| v is not present in a         | -1         |

**Boundary Value Analysis:**

| Tester Action and Input Data     | Expected Outcome      |
| ------------- | :---: |
| Empty array a        | -1         |
| v is present at the first index of a         | 0         |
| v is present at the last index of a length of a        | -1         |
| v is not present in a         | -1         |

<br>

## Program 4:
P4. The following problem has been adapted from The Art of Software Testing, by G. Myers (1979). <br>
The function triangle takes three integer parameters that are interpreted as the lengths of the sides of a triangle. <br>
It returns whether the triangle is equilateral (three lengths equal), isosceles (two lengths equal), scalene (no lengths equal), or invalid (impossible lengths).<br>
```
final int EQUILATERAL = 0;
final int ISOSCELES = 1;
final int SCALENE = 2;
final int INVALID = 3;
int triangle(int a, int b, int c){
  if (a >= b+c || b >= a+c || c >= a+b)
    return(INVALID);
  if (a == b && b == c)
    return(EQUILATERAL);
  if (a == b || a == c || b == c)
    return(ISOSCELES);
  return(SCALENE);
}
```

**Equivalence Partitioning:**

| Tester Action and Input Data     | Expected Outcome      |
| ------------- | :---: |
| Invalid triangle (a+b<=c)        | INVALID         |
| Valid equilateral triangle (a=b=c)         | EQUILATERAL         |
| Valid isosceles triangle (a=b<c)        | ISOSCELES         |
| Valid scalene triangle (a<b<c)         | SCALENE         |

**Boundary Value Analysis:**

| Tester Action and Input Data     | Expected Outcome      |
| ------------- | :---: |
| Invalid triangle (a+b<=c)        | INVALID         |
| Invalid triangle (a+c<b)         | INVALID         |
| Invalid triangle (b+c<a)        | INVALID         |
| Valid equilateral triangle (a=b=c)         | EQUILATERAL         |
| Valid isosceles triangle (a=b<c)        | ISOSCELES         |
| Valid isosceles triangle (a=c<b)        | ISOSCELES         |
| Valid isosceles triangle (b=c<a)        | ISOSCELES         |
| Valid scalene triangle (a<b<c)         | SCALENE         |

<br>

## Program 5:
The function prefix (String s1, String s2) returns whether or not the string s1 is a prefix of string s2 (you may assume that neither s1 nor s2 is null).
<br>

```
public static boolean prefix(String s1, String s2){
  if (s1.length() > s2.length()){
    return false;
  }
  for (int i = 0; i < s1.length(); i++){
    if (s1.charAt(i) != s2.charAt(i)){
      return false;
    }
  }
  return true;
}
```

**Equivalence Partitioning:**

| Tester Action and Input Data     | Expected Outcome      |
| ------------- | :---: |
| Empty string s1 and s2        | True         |
| Empty string s1 and non-empty s2         | True         |
| Non-empty s1 is a prefix of non-empty s2        | True         |
| Non-empty s1 is not a prefix of s2         | False         |
| Non-empty s1 is longer than s2         | False         |

**Boundary Value Analysis:**

| Tester Action and Input Data     | Expected Outcome      |
| ------------- | :---: |
| Empty string s1 and s2        | True         |
| Empty string s1 and non-empty s2         | True         |
| Non-empty s1 is not a prefix of s2         | False         |
| Non-empty s1 is longer than s2         | False         |
<br>

## Program 6:
Consider again the triangle classification program (P4) with a slightly different specification: <br>
The program reads floating values from the standard input. The three values A, B, and C are interpreted as representing the lengths of the sides of a triangle. <br>
The program then prints a message to the standard output that states whether the triangle, if it can be formed, is scalene, isosceles, equilateral, or right angled.<br>
Determine the following for the above program:<br>
<br>

**a) Identify the equivalence classes for the system<br>**

Equivalence Classes:<br>
EC1: All sides are positive, real numbers.<br>
EC2: One or more sides are negative or zero.<br>
EC3: The sum of the lengths of any two sides is less than or equal to the length of the remaining side (impossible lengths).<br>
EC4: The sum of the lengths of any two sides is greater than the length of the remaining side (possible lengths).<br>

<br>


**b) Identify test cases to cover the identified equivalence classes. Also, explicitly mention which test case would cover which equivalence class.<br>**
(Hint: you must need to be ensure that the identified set of test cases cover all identified equivalence classes)<br>

Test cases:<br>
TC1 (EC1): A=3, B=4, C=5 (right-angled triangle)<br>
TC2 (EC1): A=5, B=5, C=5 (equilateral triangle)<br>
TC3 (EC1): A=5, B=6, C=7 (scalene triangle)<br>
TC4 (EC1): A=5, B=5, C=7 (isosceles triangle)<br>
TC5 (EC2): A=-2, B=4, C=5 (invalid input)<br>
TC6 (EC2): A=0, B=4, C=5 (invalid input)<br>

<br>


**c) For the boundary condition A + B > C case (scalene triangle), identify test cases to verify the boundary.<br>**

Test cases for the boundary condition A + B > C:<br>
TC7 (EC4): A=2, B=3, C=6 (sum of A and B is equal to C)<br>

<br>


**d) For the boundary condition A = C case (isosceles triangle), identify test cases to verify the boundary.<br>**

Test cases for the boundary condition A = C:<br>
TC8 (EC4): A=5, B=6, C=5 (A equals to C)<br>

<br>

**e) For the boundary condition A = B = C case (equilateral triangle), identify test cases to verify the boundary.<br>**

Test cases for the boundary condition A = B = C:<br>
TC9 (EC4): A=1, B=1, C=1 (all sides are equal)<br>

<br>

**f) For the boundary condition A2 + B2 = C2 case (right-angle triangle), identify test cases to verify the boundary.<br>**

Test cases for the boundary condition A^2 + B^2 = C^2:<br>
TC10 (EC4): A=3, B=4, C=5 (right-angled triangle)<br>

<br>

**g) For the non-triangle case, identify test cases to explore the boundary.<br>**

Test cases for the non-triangle case:<br>
TC11 (EC3): A=2, B=2, C=4 (sum of A and B is less than C)<br>

<br>

**h) For non-positive input, identify test points.<br>**

Test points for non-positive input:<br>
TP1 (EC2): A=0, B=4, C=5 (invalid input)<br>
TP2 (EC2): A=-2, B=4, C=5 (invalid input)<br>
Note: Test cases TC1 to TC10 covers all identified equivalence classes.<br>

<br>

**Test Cases Code**
```
package lab_7;
import static org.junit.Assert.*;
import org.junit.Test;
public class LinaerSearch {
	@Test
	public void test() {
		unittesting obj = new unittesting();
       int[] arr1 = {2, 4, 6, 8, 10};
       int[] arr2 = {-3, 0, 3, 7, 11};
       int[] arr3 = {1, 3, 5, 7, 9};
      
       //assertEquals(2, obj.linearSearch(6, arr1));
       assertEquals(8, obj.linearSearch(3, arr2));
       assertEquals(4, obj.linearSearch(9, arr3));
	}
	
	@Test
	public void test2() {
		unittesting counter = new unittesting();
		int[] arr1 = {1, 2, 4, 4, 5};
		int[] arr2 = {1, 2, 3, 4, 5, 6, 7, 8, 9};
		int[] arr3 = {1, 2, 3, 4, 4, 4, 5, 6, 7, 8, 9};
		int v1 = 4;
		int v2 = 10;
		assertEquals(2, counter.countItem(v1, arr1));
		assertEquals(0, counter.countItem(v2, arr1));
		
	}
	
	@Test
	public void test3() {
		unittesting bs = new unittesting();
		
		int[] arr1 = {1, 3, 5, 7, 9};
		assertEquals(0, bs.binarySearch(1, arr1)); // search for 1 in {1, 3, 5, 7, 9}
		assertEquals(2, bs.binarySearch(5, arr1)); // search for 5 in {1, 3, 5, 7, 9}
		
		int[] arr2 = {2, 4, 6, 8, 10, 12};
		assertEquals(-1, bs.binarySearch(1, arr2)); // search for 1 in {2, 4, 6, 8, 10, 12}
		assertEquals(2, bs.binarySearch(6, arr2)); // search for 6 in {2, 4, 6, 8, 10, 12}
		
	}
	
	 @Test
	  public void testEquilateral() {
	    assertEquals("Equal", unittesting.triangle(3, 3, 3));
	  }
	  @Test
	  public void testIsosceles() {
	    assertEquals("Isosceles", unittesting.triangle(5, 5, 6));
	   
	  }
	  @Test
	  public void testScalene() {
	    assertEquals("Scalene", unittesting.triangle(3, 4, 5));
	  }
	  @Test
	  public void testIncorrectInput() {
	    assertEquals("Incorrect input", unittesting.triangle(1, 2, 3));
	   
	  }
	 
	  @Test
	    public void testPrefix() {
	        String s1 = "hello";
	        String s2 = "hello world";
	        assertTrue(unittesting.prefix(s1, s2));
	       
	        s1 = "abc";
	        s2 = "abcd";
	        assertTrue(unittesting.prefix(s1, s2));
	       
	        s1 = "";
	        s2 = "hello";
	        assertTrue(unittesting.prefix(s1, s2));
	       
	        s1 = "hello";
	        s2 = "hi";
	        assertFalse(unittesting.prefix(s1, s2));
	       
	        s1 = "abc";
	        s2 = "def";
	        assertFalse(unittesting.prefix(s1, s2));
	    }
	 
}
```

# **Section B**
1. Convert the Java code comprising the beginning of the doGraham method into a control flow graph (CFG).
<br>

![alt](https://github.com/hetbpatel/Lab-7_202001123/blob/8bfbae24d27da49c41c95e31cf73fd4da93d0097/p6.png)

2. Construct test sets for your flow graph that are adequate for the following criteria:

a. Statement Coverage.
To achieve statement coverage, we need to make sure that every statement in the code is executed at least once.


        Test 1: p = empty vector
        Test 2: p = vector with one point
        Test 3: p = vector with two points with the same y component
        Test 4: p = vector with two points with different y components
        Test 5: p = vector with three or more points with different y components
        Test 6: p = vector with three or more points with the same y component

<br>

b. Branch Coverage.
To achieve branch coverage, we need to make sure that every possible branch in the code is taken at least once

<br>

        Test 1: p = empty vector
        Test 2: p = vector with one point
        Test 3: p = vector with two points with the same y component
        Test 4: p = vector with two points with different y components
        Test 5: p = vector with three or more points with different y components, and none of them have the same x component
        Test 6: p = vector with three or more points with the same y component, and some of them have the same x component
        Test 7: p = vector with three or more points with the same y component, and all of them have the same x component

c. Basic Condition Coverage.
To achieve basic condition coverage, we need to make sure that every basic condition in the code (i.e., every Boolean subexpression) is evaluated as both true and false at least once

<br>

        Test 1: p = empty vector
        Test 2: p = vector with one point
        Test 3: p = vector with two points with the same y component
        Test 4: p = vector with two points with different y components
        Test 5: p = vector with three or more points with different y components, and none of them have the same x component
        Test 6: p = vector with three or more points with the same y component, and some of them have the same x component
        Test 7: p = vector with three or more points with the same y component, and all of them have the same x component
        Test 8: p = vector with three or more points with the same y component, and some of them have the same x component, and the first point has a smaller x component
<br>
