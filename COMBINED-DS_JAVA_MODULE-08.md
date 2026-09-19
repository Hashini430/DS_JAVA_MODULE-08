# DS_JAVA_MODULE-08 — Combined PDF Report

This document combines all five exercise files in the repository into one PDF-ready Markdown file.

---

# Ex11 — Convert HashSet to ArrayList in Java

## Aim
To convert a collection of distinct integers stored in a `HashSet` into an `ArrayList` and display its contents.

## Algorithm
1. Start the program.
2. Create a `HashSet` to store distinct integers.
3. Add integers to the `HashSet`.
4. Create an `ArrayList` initialized with the elements of the `HashSet`.
5. Display the `ArrayList` contents.

## Program
```java
import java.util.*;

public class HashSetToArrayList {
    public static ArrayList<Integer> convertToArrayList(HashSet<Integer> set) {
        return new ArrayList<>(set);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        HashSet<Integer> set = new HashSet<>();

        for (int i = 0; i < n; i++) {
            set.add(sc.nextInt());
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

## Output
<img width="524" height="550" alt="image" src="https://github.com/user-attachments/assets/0a328278-4dfa-401b-b137-abc9458d737d" />

## Result
The program successfully converts a collection of distinct integers stored in a `HashSet` into an `ArrayList`.

---

# Ex12 — Add Elements from an Array into a TreeSet

## Aim
To write a Java program that adds elements from an array into a `TreeSet` and displays the elements in sorted order.

## Algorithm
1. Create an integer array.
2. Create a `TreeSet` to store elements in sorted order.
3. Add each array element to the `TreeSet`.
4. Display the sorted elements.

## Program
```java
import java.util.*;

public class ArrayToTreeSet {
    public static TreeSet<Integer> convertArrayToTreeSet(int[] arr) {
        List<Integer> list = new ArrayList<>();
        for (int x : arr) {
            list.add(x);
        }
        return new TreeSet<>(list);
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

## Output
<img width="624" height="436" alt="image" src="https://github.com/user-attachments/assets/869f72c0-2cfe-4e38-a11e-669968f0a796" />

## Result
The program successfully adds elements from an array into a `TreeSet`.

---

# Ex13 — Fill the First 10 Elements of an Array with a Constant

## Aim
To write a Java program that fills an array with a constant value using the `Arrays.fill()` method.

## Algorithm
1. Start the program.
2. Read a constant value.
3. Create an array of size 10.
4. Fill the array using `Arrays.fill()`.
5. Display the array elements.

## Program
```java
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

## Output
<img width="706" height="176" alt="image" src="https://github.com/user-attachments/assets/3b0bedfe-2c88-4b2f-840e-e2733f1f817d" />

## Result
The program successfully fills the first 10 elements of the array with a constant value.

---

# Ex14 — Track the First Unique Number in a Stream

## Aim
To track the first unique, non-repeating number in a stream of integers using a `LinkedHashMap`.

## Algorithm
1. Create a `LinkedHashMap` to store integers and their frequencies.
2. Read the stream of integers.
3. Update the frequency of each number.
4. Search the map in insertion order for the first number with frequency 1.
5. Display the first unique number or report that none exists.

## Program
```java
import java.util.*;

public class FirstUniqueNumberStream {
    public static void processStream(int n, Scanner sc) {
        LinkedHashMap<Integer, Integer> freqMap = new LinkedHashMap<>();

        for (int i = 0; i < n; i++) {
            int current = sc.nextInt();
            freqMap.put(current, freqMap.getOrDefault(current, 0) + 1);

            int firstUnique = -1;
            for (Map.Entry<Integer, Integer> entry : freqMap.entrySet()) {
                if (entry.getValue() == 1) {
                    firstUnique = entry.getKey();
                    break;
                }
            }

            if (firstUnique != -1) {
                System.out.println("First unique number: " + firstUnique);
            } else {
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

## Output
<img width="686" height="507" alt="image" src="https://github.com/user-attachments/assets/c8c28d2e-327d-4303-b3c5-80c1eeec6735" />

## Result
The program successfully tracks and returns the first unique number at each point in the integer stream.

---

# Ex15 — Value Existence Check in a TreeMap

## Aim
To write a Java program that checks whether a given value exists in a `TreeMap`.

## Algorithm
1. Create a `TreeMap` to store key-value pairs.
2. Read and insert the entries.
3. Read the value to search for.
4. Use `containsValue()` to check whether the value exists.
5. Display the result.

## Program
```java
import java.util.*;

public class TreeMapValueExistenceCheck {
    public static void checkValue(TreeMap<Integer, String> map, String searchValue) {
        if (map.containsValue(searchValue)) {
            System.out.println("Value \"" + searchValue + "\" exists in the TreeMap.");
        } else {
            System.out.println("Value \"" + searchValue + "\" does not exist in the TreeMap.");
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

## Output
<img width="972" height="668" alt="image" src="https://github.com/user-attachments/assets/4f28964f-e8ad-4737-ac84-18a702035340" />

## Result
The program successfully checks whether a specified value exists in a `TreeMap` using `containsValue()`.

---

# Conclusion

This combined document covers Java collection operations using `HashSet`, `ArrayList`, `TreeSet`, `Arrays.fill()`, `LinkedHashMap`, and `TreeMap`. It is ready to open in a Markdown viewer and export as a PDF.
