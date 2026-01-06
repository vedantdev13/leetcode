

 
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











HARD____
