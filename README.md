# Lab-7_202001123

## ID - 202001123

## Name - Het Patel

## Section-A

Equivalence Partitioning Test Cases:

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


## Program 1

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

**Junit testing 1**
**Junit testing 2**
**Junit testing 3**
**Junit testing 4**

