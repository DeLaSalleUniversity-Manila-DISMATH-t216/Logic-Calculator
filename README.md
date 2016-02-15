# Logic-Calculator

![jcinsanity](Screenshot 001.PNG)

~~~
package ph.edu.dlsu;
import java.io.*;

public class Main {

    public static void main(String[] args)  {

        String j = getInput("Input X (true or false): ");
        String c = getInput("Input Y (true or false): ");

        if (j.equals("0"))
            c = "false";

        if (j.equals("1"))
            c = "true";

        if (j.equals("1"))
            c = "true";

        if (j.equals("0"))
            c = "false";

        boolean X = Boolean.parseBoolean(j);
        boolean Y = Boolean.parseBoolean(c);

        System.out.println("Choose: 1. AND, 2. OR, 3. XOR, 4. NAND, 5. NOR, 6. XNOR 7.IMPLICATION, 8. EXIT ");
        String strOption = getInput("Choose from 1-8 =  ");

        int intOption = Integer.parseInt(strOption);

        switch(intOption){
            case 1:
                andTable(X, Y);
                break;
            case 2:
                orTable(X, Y);
                break;
            case 3:
                xorTable(X, Y);
                break;
            case 4:
                nandTable(X, Y);
                break;
            case 5:
                norTable(X, Y);
                break;
            case 6:
                xnorTable(X, Y);
                break;
            case 7:
                impliTable(X, Y);
                break;
            default:
                System.out.println("I'm sorry");
                break;

        }
    }

    private static void andTable(boolean x, boolean y) {
        System.out.println("|\t" +x+ "\t|\t" +y+ "\t|\t" +(x && y)+ "\t|");
    }

    private static void orTable(boolean x, boolean y) {

        System.out.println("|\t" +x+ "\t|\t" +y + "\t|\t" +(x || y)+ "\t|");
    }

    private static void xorTable(boolean x, boolean y) {
        System.out.println("|\t" +x+ "\t|\t" +y+ "\t|\t" +(x ^ y)+ "\t|");
    }

    private static void nandTable(boolean x, boolean y) {
        System.out.println("|\t" +x+ "\t|\t" +y+ "\t|\t" +!(x && y)+ "\t|");
    }

    private static void norTable(boolean x, boolean y) {
        System.out.println("|\t" +x+ "\t|\t" +y+ "\t|\t" +!(x || y)+ "\t|");
    }

    private static void xnorTable(boolean x, boolean y) {
        System.out.println("|\t" +x+ "\t|\t" +y+ "\t|\t" +!(x ^ y)+ "\t|");

    }

    private static void impliTable(boolean x, boolean y) {
        System.out.println("|\t" + x + "\t|\t" + y + "\t|\t" + (!x || y) + "\t|");
    }


    private static String getInput(String prompt) {
        BufferedReader stdin = new BufferedReader(
                new InputStreamReader(System.in));

        System.out.print(prompt);
        System.out.flush();

        try {
            return stdin.readLine();
        } catch (Exception e) {
            return "Error: " + e.getMessage();
        }
    }

}
~~~
