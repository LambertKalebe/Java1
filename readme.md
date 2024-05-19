/**
 * This is the main method of the Calculator class. It reads two numbers and an operator from the user,
 * performs the corresponding operation and prints the result.
 *
 * @param args Command line arguments (not used in this program).
 */
public static void main(String[] args) {
    /**
     * Reads a number from the user.
     *
     * @return The number entered by the user.
     */
    public static float readNumber() {
        Scanner readInput = new Scanner(System.in);
        System.out.print("Enter a number: ");
        return readInput.nextFloat();
    }

    /**
     * Reads an operator from the user.
     *
     * @return The operator entered by the user.
     */
    public static String readOperator() {
        Scanner readInput = new Scanner(System.in);
        System.out.print("Enter an operator (+, -, *, /): ");
        return readInput.next();
    }

    /**
     * Performs the specified operation on two numbers and returns the result.
     *
     * @param a The first number.
     * @param b The second number.
     * @param operator The operator to be applied.
     * @return The result of the operation.
     */
    public static float performOperation(float a, float b, String operator) {
        switch (operator) {
            case "+":
                return a + b;
            case "-":
                return a - b;
            case "*":
                return a * b;
            case "/":
                if (b != 0) {
                    return a / b;
                } else {
                    throw new IllegalArgumentException("Division by zero is not allowed.");
                }
            default:
                throw new IllegalArgumentException("Invalid operator. Please enter one of the following: +, -, *, /.");
        }
    }

    float a = readNumber();
    String operator = readOperator();
    float b = readNumber();

    try {
        float result = performOperation(a, b, operator);
        System.out.println("The result is: " + result);
    } catch (IllegalArgumentException e) {
        System.out.println(e.getMessage());
    }
}