public class Palindrome
 { 
   public static void main (string[]args)
    { 
      int number;
      Scanner scanner = new scanner (system.in);
      system.out.println("enter a number");
      number = sc.nextint;
      int reversedNumber = 0, temp = number;
      while(temp >0)
      {
        int remainder = temp % 10;
        reversed number = reversedNUmber * 10 + remainder;
        temp = temp/10;
      } 
        if( number == reversedNumber)
         system.out.println("number is palindrome");
        else
         system.out.println("number is not palindrome");
      }
    }  
