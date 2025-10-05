# Java
Teacher import java.util.Scanner;

class Main
{
    public static void main(String[] args)
    {
        Scanner in = new Scanner(System.in);

        System.out.print("Enter number: ");
        int number = in.nextInt();

        System.out.println("\nChoose an option:");
        System.out.println("1. Sum (1+2+...+n)");
        System.out.println("2. Factorial");
        System.out.println("3. Perfect Number Check");
        System.out.println("4. Strong Number Check");

        System.out.print("Enter choice: ");
        int choice = in.nextInt();

        if(choice == 1) {
            int sum = All.add(number);
            System.out.println("Sum = " + sum);
        }
        else if(choice == 2) {
            int fact = All.fact(number);
            System.out.println("Factorial = " + fact);
        }
        else if(choice == 3) {
            All.perfect(number);
        }
        else if(choice == 4) {
            All.strong(number);
        }
        else {
            System.out.println("Invalid Choice!");
        }
    }
}

class All
{
    public static int add(int n)
    {
        if(n == 0) return 0;
        return n + add(n - 1);
    }

    public static int fact(int n)
    {
        if(n == 0 || n == 1) return 1;
        return n * fact(n - 1);
    }

    public static void perfect(int n)
    {
        int sum = 0;
        for(int i = 1; i < n; i++)
        {
            if(n % i == 0) sum += i;
        }
        if(n == sum)
            System.out.println(n + " is a Perfect Number");
        else
            System.out.println(n + " is NOT a Perfect Number");
    }

    public static void strong(int n)
    {
        int sum = 0, g = n;
        while(n != 0)
        {
            int n1 = n % 10;
            int c = 1;
            while(n1 != 0)
            {
                c *= n1;
                n1--;
            }
            sum += c;
            n /= 10;
        }
        if(g == sum)
            System.out.println(g + " is a Strong Number");
        else
            System.out.println(g + " is NOT a Strong Number");
    }
}
