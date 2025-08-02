
public class Factorial {
	public class RecursiveTrace {

	    static int depth = 0;

	    	    public static int factorial(int n) {
	        printIndent("factorial(" + n + ") called");
	        depth++;

	        int result;
	        if (n == 0 || n == 1) {
	            result = 1;
	        } else {
	            result = n * factorial(n - 1);
	        }

	        depth--;
	        printIndent("factorial(" + n + ") returns " + result);
	        return result;
	    }

	    
	    public static int fibonacci(int n) {
	        printIndent("fibonacci(" + n + " ) called");
	        depth++;

	        int result;
	        if (n == 0) {
	            result = 0;
	        } else if (n == 1) {
	            result = 1;
	        } else {
	            result = fibonacci(n - 1) + fibonacci(n - 2);
	        }

	        depth--;
	        printIndent("fibonacci(" + n + ") returns " + result);
	        return result;
	    }

	    public static void printIndent(String message) {
	        for (int i = 0; i < depth; i++) {
	            System.out.print("  ");
	        }
	        System.out.println(message);
	    }

	    public static void main(String[] args) {
	        System.out.println("\n--- Factorial Trace ---");
	        int factResult = factorial(4);
	        System.out.println("Factorial(4) = " + factResult);

	        System.out.println("\n--- Fibonacci Trace ---");
	        int fibResult = fibonacci(5);
	        System.out.println("Fibonacci(5) = " + fibResult);
	    }
	}

}
