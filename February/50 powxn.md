## math
```java
class Solution {
    public double myPow(double x, int n) {
        long N = n;
        if (N < 0) {
            x = 1 / x;
            N = -N;
        }
        
        double result = 1;
        
        while (N > 0) {
            if ((N & 1) == 1) {
                result *= x;
            }
            x *= x;
            N >>= 1;
        }
        
        return result;
    }
}
```
![Submission screenshots](screenshots/pow(x,n)/math.png)  
## reecusrion
```java
class Solution {
    public double myPow(double x, int n) {
        long N = n;
        if (N < 0) {
            x = 1 / x;
            N = -N;
        }
        return fastPow(x, N);
    }
    
    private double fastPow(double x, long n) {
        if (n == 0) return 1;
        
        double half = fastPow(x, n / 2);
        
        if (n % 2 == 0) return half * half;
        
        return half * half * x;
    }
}

```
![Submission screenshots](screenshots/pow(x,n)/recursion.png)  