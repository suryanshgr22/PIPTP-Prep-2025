# Week1 - Day 4

## Problems
---
- Problem 1
    ### Code
    ```java
    public static int f(int n){
        if(n==0) return 0;
        return n + f(n-1);
    }
    System.out.println(f(5));
    ```
    ### Solution : 
    *15*
    ### Explaination :
    *f(5) -> 5+f[4) -> 4+f(3) -> 3+f(2) -> 2+f(1) -> 1+f(0) -> 0.
    Answer = 5+4+3+2+1+0 = 15*
---
---
- Problem 2
    ### Code
    ```java
    public static int foo(int n) {
        if (n == 1) return 1;
        if (n % 2 == 0) return 2 * foo(n / 2);
        return 2 * foo((n - 1) / 2) + 1;
    }
    System.out.println(foo(5));
    ```
    ### Solution : 
    *5*
    ### Explaination :
    *f(5) -> 2*f(2)+1, 
     f(2) -> 2*f(1)
     f(1) -> 1
     Answer => (1*2)*2+1 = 5*
---
---
- Problem 3
    ### Code
    ```java
    public static int calc(int n) {
        if (n < 2) return n;
        return f(n-1) * f(n-2);
    }
    System.out.println(calc(5));
    ```
    ### Solution : 
    *0*
    ### Explaination :
    *f(0) -> 0,
     f(1) -> 1,
     f(2) -> f(1) * f(0) -> 1 * 0 = 0
     f(3) -> f(2) * f(1) -> 0 * 1 = 0
     f(4) -> f(3) * f(2) -> 0 * 0 = 0
     f(5) -> f(4) * f(3) -> 0 * 0 = 0*
---
---

- Problem 4
    ### Code
    ```java
    public static int solve(int a, int b) {
        if (b == 0) return a;
        return solve(b, a % b);
    }
    System.out.println(solve(48, 18));
    ```
    ### Solution : 
    *6*
    ### Explaination :
    *GCD : f(48, 18) -> f(18, 12) -> f(12, 6) -> f(6, 0) -> return 6*
---

- Problem 5
    ### Code
    ```java
    public static int solve(int n) {
        if (n == 0) return 1;
        if(n<10) return 0;
        if(n%10 == 0) return 1+solve(n/10);
        return solve(n/10);
    }
    System.out.println(solve(102030));
    ```
    ### Solution : 
    *3*
    ### Explaination :
    *Count number of zeros: f(102030) -> 1+f(10203) -> f(1020) -> 1+f(102) -> f(10) -> 1+f(1) -> return 0.
    Answer : 0 + 1 + 1 + 1 = 3*
---

- Problem 6
    ### Code
    ```java
    public static int solve(String X, String Y, int m, int n) {
        if (m == 0 || n == 0) return 0;
        if (X.charAt(m - 1) == Y.charAt(n - 1))
            return 1 + solve(X, Y, m - 1, n - 1);
        else
            return Math.max(solve(X, Y, m - 1, n), solve(X, Y, m, n - 1));
    }

    // Example usage:
    System.out.println(solve("AGGTAB", "GXTXAYB", 6, 7));

    ```
    ### Solution : 
    *4*
    ### Explaination :
    *Longest Common Subsequence ->
    A G T A B -> 4*
---

- Problem 7
    ### Code
    ```java
    public static int solve(int[] masses, int[] merits, int limit, int itemCount) {
        if (itemCount == 0 || limit == 0) return 0;
        if (masses[itemCount - 1] > limit)
            return solve(masses, merits, limit, itemCount - 1);
        return Math.max(
            merits[itemCount - 1] + solve(masses, merits, limit - masses[itemCount - 1], itemCount - 1),
            solve(masses, merits, limit, itemCount - 1)
        );
    }

    // Example usage:
    int[] masses = {1, 3, 4, 5};
    int[] merits = {1, 4, 5, 7};
    int limit = 7;
    System.out.println(solve(masses, merits, limit, masses.length));


    ```
    ### Solution : 
    *9*
    ### Explaination :
    *0 -1 KnapSack problem -> max merits = 9 with masses = 7 <= 7*
---


---

- Problem 8
    ### Code
    ```java
    public static int f(int a, int b) {
    if (b == 0) return 0;
        return a + f(a, b - 1);
    }
    System.out.println(f(3, 2));
    ```
    ### Solution : 
    *6*
    ### Explaination :
    *Multiplication of a * b -> 3 * 2 -> 6*
---

- Problem 9
    ### Code
    ```java
    void recur(int n) {
        if (n <= 0) return;
        recur(n - 1);
        System.out.print(n);
        recur(n - 2);
    }
    recur(3);
    ```
    ### Solution : 
    *1 2 3 1*
    ### Explaination :
    *f(3) -> f(2) -> f(1) -> f(0) -> return 0
    print(1), f(-1) -> return 0,
    print(2), f(0) -> return 0
    print(3), f(1) -> f(0) -> return 0
    print(1)*
---

- Problem 10
    ### Code
    ```java
    public static int countPaths(int m, int n) {
        if (m == 1 || n == 1) return 1;
        return countPaths(m - 1, n) + countPaths(m, n - 1);
    }
    System.out.println(countPaths(3, 3));
    ```
    ### Solution : 
    *6*
    ### Explaination :
    *Count no of ways to reach top left cell from bottom right cell if the grid of size 3x3*
---




