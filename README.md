

 
lets finish 

EASY _____







MEDIUM____

1. Q8
class Solution {
    public int myAtoi(String s) {

        // agar string null hai ya empty hai to 0 return
        if (s == null || s.length() == 0) return 0;

        // int ki max aur min limit
        final int INT_MAX = Integer.MAX_VALUE;   // 2147483647
        final int INT_MIN = Integer.MIN_VALUE;   // -2147483648

        int i = 0;                 // string index
        int n = s.length();        // string ki length

        // starting ke spaces skip karo
        while (i < n && s.charAt(i) == ' ') {
            i++;
        }

        // agar sirf spaces hi the
        if (i == n) return 0;

        int sign = 1;              // number positive maan ke chalo

        // + ya - check karo
        if (s.charAt(i) == '+') {
            i++;
        } else if (s.charAt(i) == '-') {
            sign = -1;             // negative number
            i++;
        }

        long res = 0;              // number store karne ke liye

        // jab tak digit mil rahi hai
        while (i < n && s.charAt(i) >= '0' && s.charAt(i) <= '9') {

            int digit = s.charAt(i) - '0';   // char ko number me badla

            res = res * 10 + digit;          // number banaya

            // agar limit cross ho gayi
            if (sign * res <= INT_MIN) return INT_MIN;
            if (sign * res >= INT_MAX) return INT_MAX;

            i++;                              // next character
        }

        // final answer
        return (int)(res * sign);
    }
}



2.
// ni samjhaaaa
class Solution {

    // Mod value (question me diya hota hai)
    static final long MOD = 1000000007;

    public int countGoodNumbers(long n) {

        // even index positions count
        // example n=5 → indexes: 0 1 2 3 4 → even = 3
        long evenCount = (n + 1) / 2;

        // odd index positions count
        long oddCount = n / 2;

        // total ways:
        // even index → 5 choices
        // odd index → 4 choices
        long evenWays = power(5, evenCount);
        long oddWays = power(4, oddCount);

        // final answer
        long ans = (evenWays * oddWays) % MOD;

        return (int) ans;
    }

    // fast power function (important part)
    private long power(long base, long exp) {

        long result = 1;

        while (exp > 0) {

            // if exp is odd
            if (exp % 2 == 1) {
                result = (result * base) % MOD;
            }

            // base square
            base = (base * base) % MOD;

            // exp half
            exp = exp / 2;
        }

        return result;
    }
}









HARD____
