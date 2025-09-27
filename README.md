public class ReverseInteger {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter an integer: ");
        int x = sc.nextInt();
        int sign = (x < 0) ? -1 : 1;
        x = Math.abs(x);
        long rev = 0;  // use long to catch overflow while building
        while (x != 0) {
            int digit = x % 10;
            rev = rev * 10 + digit;
            x = x / 10;
        }
        rev = rev * sign;
        // check 32-bit range
        if (rev < Integer.MIN_VALUE || rev > Integer.MAX_VALUE) {
            System.out.println(0);
        } else {
            System.out.println((int)rev);
        }
    }
}
