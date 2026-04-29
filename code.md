Here’s a clean way to solve **“find the k-th largest prime number in an array” in Java**.

---

## 🧠 Approach

1. Loop through the array
2. Check which numbers are **prime**
3. Store primes in a list
4. Sort in **descending order**
5. Return the **k-th element**

---

## ✅ Java Code

```java
import java.util.*;

public class KthLargestPrime {

    // Function to check if a number is prime
    public static boolean isPrime(int n) {
        if (n <= 1) return false;
        if (n == 2) return true;
        if (n % 2 == 0) return false;

        for (int i = 3; i * i <= n; i += 2) {
            if (n % i == 0) return false;
        }
        return true;
    }

    // Function to find kth largest prime
    public static int kthLargestPrime(int[] arr, int k) {
        List<Integer> primes = new ArrayList<>();

        for (int num : arr) {
            if (isPrime(num)) {
                primes.add(num);
            }
        }

        // Sort in descending order
        Collections.sort(primes, Collections.reverseOrder());

        if (k <= primes.size()) {
            return primes.get(k - 1);
        } else {
            return -1; // Not enough prime numbers
        }
    }

    public static void main(String[] args) {
        int[] arr = {10, 7, 5, 3, 20, 11};
        int k = 2;

        int result = kthLargestPrime(arr, k);
        System.out.println("Kth largest prime: " + result);
    }
}
```

---

## 📌 Example

Input:

```
arr = [10, 7, 5, 3, 20, 11]
k = 2
```

Prime numbers → `[7, 5, 3, 11]`
Sorted (desc) → `[11, 7, 5, 3]`

👉 2nd largest = **7**

---

## ⚡ Better Approach (More Efficient)

Instead of sorting, you can use a **min heap (PriorityQueue)** of size `k` to improve performance for large arrays.

If you want, I can show that optimized version too 👍
