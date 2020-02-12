import java.util.Scanner;

public class Mentormate {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);

        int n = Integer.parseInt(scan.nextLine());

        String stars = "*";
        String minus = "-";
        getFirstLine(n, stars, minus);
        getFirsCenterLines(n, stars, minus);
        getSecondsCenterLines(n, stars, minus);
        getLastLine(n, stars, minus);


    }

    private static void getSecondsCenterLines(int n, String stars, String minus) {

        //last rows (without the last row)
        int lines = (n - 1) / 2;

        int value = n / 2;
        int firstAndLastMinus = (int) Math.ceil(value);

        int minusForMakingM = 1;

        int aLotOfStars = n+((n-1));


        for (int i = 1; i <= lines; i++) {

            for (int j = 1; j <= 2; j++) {
                for (int k = 1; k <= firstAndLastMinus; k++) {
                    System.out.print(minus);
                }
                for (int k = 1; k <= n; k++) {
                    System.out.print(stars);
                }
                for (int k = 1; k <=minusForMakingM; k++) {
                    System.out.print(minus);
                }
                for (int k = 1; k <=aLotOfStars; k++) {// 
                    System.out.print(stars);
                }
                for (int k = 1; k <=minusForMakingM ; k++) {
                    System.out.print(minus);
                }
                for (int k = 1; k <= n; k++) {
                    System.out.print(stars);
                }
                for (int k = 1; k <= firstAndLastMinus; k++) {
                    System.out.print(minus);
                }

            }
            firstAndLastMinus -=1;
            minusForMakingM +=2;
            aLotOfStars -=2;
            System.out.println();
        }

    }

    private static void getFirsCenterLines(int n, String stars, String minus) {
        int lines = ((n-1)/2);

        int startEndLines = n;
        int firstStar = n;
        int midMinus=n;


        for (int i = 1; i <=lines ; i++) {
            startEndLines -=1;
            firstStar +=2;
            midMinus -=2;
            for (int colum = 1; colum <=2; colum++) {

                for (int j = 1; j <= startEndLines; j++) { //first
                    System.out.print(minus);
                }
                for (int j = 1; j <=firstStar; j++) {
                    System.out.print(stars);
                }
                for (int j = 1; j <=midMinus; j++) {
                    System.out.print(minus);
                }
                for (int j = 1; j <=firstStar ; j++) {
                    System.out.print(stars);
                }
                for (int j = 1; j <=startEndLines ; j++) {
                    System.out.print(minus);
                }

            }
            System.out.println();

        }


    }




    private static void getLastLine(int n, String stars, String minus) {
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= n; j++) {
                System.out.print(stars);
            }
            if (i == 3) {//
                continue;
            }
            for (int j = 1; j <= n; j++) {
                System.out.print(minus);
            }
            if (i == 5) {
                for (int j = 1; j <= n; j++) {
                    System.out.print(stars);
                }
            }
        }
    }

    private static void getFirstLine(int n, String stars, String minus) {

        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= n; j++) {
                System.out.print(minus);
            }
            if (i == 3) {//
                continue;
            }
            for (int j = 1; j <= n; j++) {
                System.out.print(stars);
            }
            if (i == 5) {
                for (int j = 1; j <= n; j++) {
                    System.out.print(minus);
                }
            }

        }
        System.out.println();

    }
}


