# DS_JAVA_MODULE-08 — Combined File

This document combines all exercise files in the repository into a single PDF-friendly report.

---

# Ex11 Convert HashSet to ArrayList in Java
## AIM:
To convert a collection of distinct integers stored in a HashSet into an ArrayList and display its contents.

## Algorithm
1. Start the program.
2. Create a HashSet to store a collection of distinct integers.
3. Add a few integers to the HashSet.
4. Create an ArrayList and initialize it with the elements of the HashSet.
5. Display the elements of both HashSet and ArrayList.
6. End the program.

## Program:
```java
/*
Program to To convert a collection of distinct integers stored in a HashSet into an ArrayList and display its contents.
Developed by: Abinaya A
RegisterNumber: 212224230004
*/

import java.util.*;

public class HashSetToArrayList {

    public static ArrayList<Integer> convertToArrayList(HashSet<Integer> set) {
        ArrayList<Integer> list = new ArrayList<>(set);
        return list;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        HashSet<Integer> set = new HashSet<>();
        for (int i = 0; i < n; i++) {
            int num = sc.nextInt();
            set.add(num);
        }

        ArrayList<Integer> list = convertToArrayList(set);
        System.out.println("ArrayList contents:");
        for (int num : list) {
            System.out.print(num + " ");
        }
        sc.close();
    }
}
```

## Output:
<img width="524" height="550" alt="image" src="https://github.com/user-attachments/assets/0a328278-4dfa-401b-b137-abc9458d737d" />

## Result:
The program successfully converts a collection of distinct integers stored in a HashSet into an ArrayList.

---

# Ex12 Add Elements from an Array into a TreeSet
## AIM:
To write a Java program that adds elements from an array into a TreeSet and displays the elements in sorted order.

## Algorithm
1. Create an array containing a few integer elements.
2. Create a TreeSet to store elements in sorted order.
3. Use a loop to add each element of the array into the TreeSet.
4. Display the elements of the TreeSet.
5. Stop the program.

## Program:
```java
/*
Program that adds elements from an array into a TreeSet and displays the elements in sorted order.
Developed by: Abinaya A
RegisterNumber: 212224230004
*/

import java.util.*;

public class ArrayToTreeSet {

    public static TreeSet<Integer> convertArrayToTreeSet(int[] arr) {
        List<Integer> list = new ArrayList<>();
        for(int x : arr){
            list.add(x);
        }

        TreeSet<Integer> treeSet = new TreeSet<>(list);
        return treeSet;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        TreeSet<Integer> treeSet = convertArrayToTreeSet(arr);
        System.out.println("Elements in TreeSet:");
        for (int num : treeSet) {
            System.out.println(num);
        }

        sc.close();
    }
}
```

## Output:
<img width="624" height="436" alt="image" src="https://github.com/user-attachments/assets/869f72c0-2cfe-4e38-a11e-669968f0a796" />

## Result:
The program successfully adds elements from an array into a TreeSet.

---

# Ex13 Fill the First 10 Elements of an Array with a Constant using Arrays.fill()
## AIM:
To write a Java program that fills the first 10 elements of an array with a constant value using the Arrays.fill() method.

## Algorithm
1. Start the program.
2. Create an integer array of a specified size (for example, 15 elements).
3. Use the Arrays.fill() method to fill the first 10 elements of the array with a constant value.
4. Display the elements of the array after filling.
5. Stop the program.

## Program:
```java
/*
Program to FILL the first 10 elements of an array with a constant value using the Arrays.fill() method.
Developed by: Abinaya A
RegisterNumber: 212224230004
*/

import java.util.*;

public class FillArrayUsingArraysFill {

    public static int[] fillArray(int size, int value) {
        int[] arr = new int[size];
        Arrays.fill(arr, value);
        return arr;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int value = sc.nextInt();
        int[] arr = fillArray(10, value);
        System.out.println("Array elements:");
        for (int num : arr) {
            System.out.print(num + " ");
        }
        sc.close();
    }
}
```

## Output:
<img width="706" height="176" alt="image" src="https://github.com/user-attachments/assets/3b0bedfe-2c88-4b2f-840e-e2733f1f817d" />

## Result:
The program successfully fills the first 10 elements of the array with the constant value 5 using the Arrays.fill() method.

---

# Ex14 Tracking the First Unique Number in a Stream using LinkedHashMap
## AIM:
To implement a program that tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.

## Algorithm
1. Start the program.
2. Create a LinkedHashMap to store integers as keys and their frequency (count) as values.
3. Read or define a stream of integers (array of numbers).
4. For each integer in the stream:
   - If the number is not already in the map, insert it with count = 1.
   - If it exists, increment its count by 1.
5. After processing each element, find the first number in the LinkedHashMap with count = 1.
6. Display the current stream and the first unique number.

## Program:
```java
/*
Program to tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.
Developed by: Abinaya A
RegisterNumber: 212224230004
*/

import java.util.*;

public class FirstUniqueNumberStream {

    public static void processStream(int n, Scanner sc) {
        LinkedHashMap<Integer, Integer> freqMap = new LinkedHashMap<>();
        for(int i=0; i<n; i++){
            int current = sc.nextInt();

            freqMap.put(current, freqMap.getOrDefault(current, 0)+1);

            int fUniq = -1;

            for(Map.Entry<Integer, Integer> entry : freqMap.entrySet()){
                if(entry.getValue() == 1){
                    fUniq = entry.getKey();
                    break;
                }
            }

            if(fUniq != -1){
                System.out.println("First unique number: "+fUniq);
            }else{
                System.out.println("No unique number");
            }
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        processStream(n, sc);
        sc.close();
    }
}
```

## Output:
<img width="686" height="507" alt="image" src="https://github.com/user-attachments/assets/c8c28d2e-327d-4303-b3c5-80c1eeec6735" />

## Result:
The program successfully tracks and returns the first unique number at any point in the integer stream using a LinkedHashMap.

---

# Ex15 Value Existence Check in a TreeMap
## AIM:
To write a Java program that checks whether a given value exists in a TreeMap.

## Algorithm
1. Create a TreeMap to store key–value pairs.
2. Insert some sample key–value pairs into the TreeMap.
3. Display the contents of the TreeMap.
4. Use the containsValue() method to check whether a specific value exists in the map.
5. Display the result based on the check.

## Program:
```java
/*
Program to checks whether a given value exists in a TreeMap.
Developed by: Abinaya A
RegisterNumber: 212224230004
*/

import java.util.*;

public class TreeMapValueExistenceCheck {

    public static void checkValue(TreeMap<Integer, String> map, String searchValue) {
        if(map.containsValue(searchValue)){
            System.out.println("Value \""+searchValue+"\" exists in the TreeMap.");
        }else{
            System.out.println("Value \""+searchValue+"\" does not exist in the TreeMap.");
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        TreeMap<Integer, String> map = new TreeMap<>();

        int n = sc.nextInt();

        for (int i = 0; i < n; i++) {
            int key = sc.nextInt();
            sc.nextLine();
            String value = sc.nextLine();
            map.put(key, value);
        }
        String searchValue = sc.nextLine();

        checkValue(map, searchValue);
        sc.close();
    }
}
```

## Output:
<img width="972" height="668" alt="image" src="https://github.com/user-attachments/assets/4f28964f-e8ad-4737-ac84-18a702035340" />

## Result:
Thus, the program successfully checks whether a specified value exists in a TreeMap using the containsValue() method.

---

# Conclusion
This repository contains exercises on HashSet conversion, TreeSet sorting, array filling, unique stream tracking, and TreeMap value checking. The combined report is ready for PDF conversion.
