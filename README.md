package act1;
import java.util.*;	

public class GENESISANDTHETROOPS {
    public static final String RESET = "\033[0m";
    public static final String RED = "\033[31m";
    public static final String GREEN = "\033[32m";
    public static final String CYAN = "\033[36m";
    public static final String YELLOW = "\033[33m";
    public static final String BLUE = "\033[34m";
    public static final String WHITE = "\033[37m";
    public static Scanner sc = new Scanner(System.in);
    static int choice;

    public static void main(String[] args) throws InterruptedException {
        loadingScreen();
        mainMenu();
    }

 // --- Loading Screen ---
    public static void loadingScreen() throws InterruptedException {
        // Stage 1: Initial Boot Message
        System.out.println(BLUE + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                              SYSTEM BOOTING UP                               ║");
        System.out.println("\t║                                                                              ║");
        System.out.println("\t║   ┌─────────────────────────────────────────────────────────────────────┐    ║");
        System.out.println("\t║   │             Welcome to GENESISANDTHETROOPS Calculator!              │    ║");
        System.out.println("\t║   │                     Initializing core systems...                    │    ║");
        System.out.println("\t║   └─────────────────────────────────────────────────────────────────────┘    ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);
        Thread.sleep(1000);

        // New ASCII Art Display
        System.out.println(CYAN + "\n\tDisplaying Mascot..." + RESET);
        Thread.sleep(500);
        System.out.println(BLUE + "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@%%%%%%%%%@@@@@@@@@@@@@@%%%%%%%%%@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@*========*@@@@@%+++++++%@@@@@%++++++++*@*========+++++++++@#=====+@@@@@@@@@%*============+++#%@@@@@#+=====+++++++++*#%@%======+++++#@@@@@@@@@@******#####%@********##########@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@#========+@@@@@%+++++++#@@@@@%++++++++#@+=======++++++++++@#=====+@@@@@@@#===============++++++%@#=========+++++++++***%%+====+++++*@@@@@@@@@%******#####%@********##########@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@%========+@@@@@*+++++++*@@@@@#++++++++%@========++++++++++@#-====+@@@@@@*=================++++++#@*========++++++++++***%@*====+++++%@@@@@@@@#*******####%@********##########@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@=========@@@@@+++++++++@@@@@*+++++++*@%-========+++++++++@#-====+@@@@@*===========+++====+++++++%@+=======++++++++++****%@+===+++++*@@@@@@@@*********####@********##########@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@*========%@@@%+++++++++%@@@%++++++++*@#-=====+@@@@@@@@@@@@#-====+@@@@%==========*@@@@@*===+++++++%#=====#@@@@%+++++++****%%====+++++@@@@@@@%**********###@#******@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@#========#@@@%+++++++++#@@@%++++++++*@+======+@@@@@@@%------====+@@@@+=-========%@@@@@%+==+++++++%%====*@@@@@@#+++++++***#%====+++++%@@@@@@#***********##@#******@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@%+++++++++@@@#++++++++++@@@%++++++**#@=======+@@@@@@@%------====+@@@%=---======+@@@@@@%+=++++++++#@+===*@@@@@@%+++++++***#@+====++++*@@@@@%*************#@#+*****@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@%+++++++++@@@*++++++++++%@@#+++++**+%@=======+@@@@@@@%------====+@@@%=----=====+@@@@@@%+=++++++++#@+===#@@@@@@%++++++++***@*=====++++%@@@@#*************#@#+*****@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@+++++++++%@%+++++++++++%@@*+++++***@%-======+@@@@@@@%-----=====+@@@%=-----====+@@@@@@%+=++++++++#@+===#@@@@@@%+++++++++**@*=====++++%@@@@**************#@#+*****@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@#++++++++%@%+++++++++++#@@+++++****@#-======+@@@@@@@%**---=====+@@@%=------===+@@@@@@%##########%@+===#@@@@@@%++++++++++*@*==*===+++*@@@%+*************#@#++****@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@%++++++++#@#+++++++++++*@%++++****#@========+********%@=--=====+@@@%=------===+@@@@@@@@@@@@#+++++++===#@@@@@@%++++++++++*@*==#===++++%@@*++****#*******#@#++****########%@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@++++++++*@*+++++#++++++%%+++*****#%-======++++++++++%@=--=====+@@@%=-------==+@@@@@@@@@@@@*==========#@@@@@@%++++++++++*@*==#*===+++#@%++++***%*******#@#+++**********#%@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@*++++++++%++++++%++++++%#+++*****%%=======++++++++++%@=-======+@@@%--------==+@@@@@@@@@@@@*==========#@@@@@@%++++++++++*@*==%%===+++*@%++++**#%*******#@%++++*********#%@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@*++++++++%+++++*@*+++++##+*******@#=======++++++++++%@=-======+@@@%--------==+@@@@@@@@@@@@*==========#@@@@@@%++++++++++*@*==%%+===+++%*+++++*%%********@%++++*********#%@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@#++++++++*+++++*@%+++++**+******#@*=======++%%%%%%%%%@=-======+@@@%--------==+@@@@@@@@@@@@*==========*@@@@@@%++++++++++*@*==%@*===+++*++++++*%@********@%++++**%%%%%%%%%@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@%++++++++++++++#@@+++++++*******#@========++@@@@@@@%==--======+@@@%-------===+@@@@@@@@@@@@*==========*@@@@@@%==++++++++*@*==%@%====+++++++++*@@********@%+++++*@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@++++++++++++++%@@*++++++*******%%========++@@@@@@@%----======+@@@%-------===+@@@@@@@##########%@+===*@@@@@@%==++++++++*@*==%@@+===+++++++++%@@********@%+++++*@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@*++++++++++++*@@@#++++*********%#=======+++@@@@@@@%----======+@@@%-------===+@@@@@@%++++++++++#@+===*@@@@@@%==++++++++*@*==%@@*====++++++++%@@********%%+++++*@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@#++++++++++++#@@@%++++*********@#=======+++@@@@@@@%----======+@@@%-------===+@@@@@@%++++++++++#@+===*@@@@@@%===+++++++*@*=+@@@%=====++++++*@@@********%%++++++@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@%++++++++++++%@@@@*++*********#@*=======+++@@@@@@@%---=======+@@@%-------===+@@@@@@%++++++++++#@+===*@@@@@@%==++++++++*@*=+@@@@+====++++++%@@@#*******%%++++++@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@%++++++++++++%@@@@*+**********%@+======++++@@@@@@@%---=======+@@@@=-----=====@@@@@@%++++++++++%%====*@@@@@@#===+++++++#@+=+@@@@*=====+++++@@@@#+******%%++++++@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@++++++++++++@@@@@#++*********%@+======++++@@@@@@@%####*====++@@@@%#######*==#@@@@@#++++++++++%#=====%@@@@@+==++++++++%%==+@@@@%=====++++*@@@@#++*****%%++++++@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@#++++++++++#@@@@@%++*********@@+====++++++***********%%====++++*********@#===++**+++++++++++#@+======+**+====+++++++#@*==+@@@@@+=====+++#@@@@#++*****%%++++++********###@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@%++++++++++%@@@@@@++*********@@+==++++++++++++++*****%%====++++++++++++*@#=====++++++++++++*@*=-============+++++++*@#===+@@@@@#=====+++%@@@@%+++****%%+=+++++++********@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@%++++++++++%@@@@@@#+********#@@+++++++++++++++++*****%%===+++++++++++++*@#=====+++++++++++#@#----===========++++++#@*====+@@@@@%======+*@@@@@%++++***%%+=+++++++********@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@%++++++++++%@@@@@@#+********%@@++++++++++++++++******%%====+++++++++++**@#=====+++++++++#@@@@%+=-==========+++++#@%+=====*@@@@@%+=====+#@@@@@%+++++**%%+==++++++********@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@@%%%%%%%%%%@@@@@@@@%%%%%%%%%@@@%%%%%%%%%%%%%%%%%%%%%%@@%%%%%%%%%%%%%%%%%@@%#**+++*##%%@@@@@@@@@@%%##*++++*##%%@@@@%%%%%%%%@@@@@@%%%%%%%@@@@@@@%%%%%%%@@%%%%%%%%%%%%%%%%%@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n"
    			+ "@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@                                                                                                                                      \r\n");
        System.out.println(GREEN + "\t\t\t      🤖 Ready to Compute! 🤖" + RESET);
        Thread.sleep(5000);

        // Stage 2: Phased Loading Animation
        String[] phases = {"Loading App", "Initializing Modules", "Calibrating Systems", "Activating Interface"};
        String[] cursors = {"|", "/", "-", "\\"}; // Spinning cursor
        int totalSteps = 15; // Progress steps per phase

        for (int phase = 0; phase < phases.length; phase++) {
            System.out.println(CYAN + "\n\t" + phases[phase] + "..." + RESET);
            for (int i = 0; i < totalSteps; i++) {
                int percentage = (i + 1) * (100 / totalSteps); // Percentage per step
                String bar = "[" + "█".repeat(i) + "░".repeat(totalSteps - i - 1) + "] " + percentage + "% " + cursors[i % 4];
                System.out.print(GREEN + "\r\t\t" + bar + RESET);
                Thread.sleep(120); // Smooth, dynamic pace
            }
            System.out.println(BLUE + " ✔ Complete!" + RESET);
            Thread.sleep(400);
        }

        // Stage 3: Final Success and Transition
        System.out.println(GREEN + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                              SYSTEM READY!                                   ║");
        System.out.println("\t║                                                                              ║");
        System.out.println("\t║   ┌─────────────────────────────────────────────────────────────────────┐    ║");
        System.out.println("\t║   │        All systems operational. Proceeding to main menu...          │    ║");
        System.out.println("\t║   └─────────────────────────────────────────────────────────────────────┘    ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);
        Thread.sleep(1500);
        clearScreen();
    }


    // --- Clear Console ---
    public static void clearScreen() {
        System.out.print("\033[H\033[2J");
        System.out.flush();
    }

 // --- Main Menu ---
    public static void mainMenu() throws InterruptedException {
        while (true) {
            // Professional Design: Tech Console Dashboard
            System.out.println(BLUE + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
            System.out.println("\t║                         SYSTEM DASHBOARD                                     ║");
            System.out.println("\t║                                                                              ║");
            System.out.println("\t║   ┌─────────────────────────────────────────────────────────────────────┐    ║");
            System.out.println("\t║   │         Welcome to GENESISANDTHETROOPS Calculator System!           │    ║");
            System.out.println("\t║   │                  Select an option to proceed.                       │    ║");
            System.out.println("\t║   └─────────────────────────────────────────────────────────────────────┘    ║");
            System.out.println("\t║                                                                              ║");
            System.out.println("\t║   ┌─────────────────────────────────────────────────────────────────────┐    ║");
            System.out.println("\t║   │  [1]  Calculator     - Access advanced math tools                   │    ║");
            System.out.println("\t║   │  [2]  About          - View system information                      │    ║");
            System.out.println("\t║   │  [3]  Exit           - Shut down the system                         │    ║");
            System.out.println("\t║   └─────────────────────────────────────────────────────────────────────┘    ║");
            System.out.println("\t║                                                                              ║");
            System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);
            System.out.print("\n\t" + GREEN + "Enter choice: " + RESET);

            try {
                choice = sc.nextInt();
                clearScreen();
                switch (choice) {
                    case 1 -> calculatorMenu();
                    case 2 -> about();
                    case 3 -> outingScreen();
                    default -> {
                        System.out.println(RED + "\n\t╔══════════════════════════════════════╗");
                        System.out.println("\t║            INVALID CHOICE!           ║");
                        System.out.println("\t║       Please select 1, 2, or 3.      ║");
                        System.out.println("\t╚══════════════════════════════════════╝" + RESET);
                        System.out.print(YELLOW + "\n\tPress Enter to try again..." + RESET);
                        sc.nextLine(); // Clear buffer
                        sc.nextLine(); // Wait for user
                        clearScreen();
                    }
                }
            } catch (InputMismatchException e) {
                sc.nextLine();
                System.out.println(RED + "\n\t╔══════════════════════════════════════╗");
                System.out.println("\t║             INVALID INPUT!           ║");
                System.out.println("\t║      Please enter a valid number.    ║");
                System.out.println("\t╚══════════════════════════════════════╝" + RESET);
                System.out.print(YELLOW + "\n\tPress Enter to try again..." + RESET);
                sc.nextLine(); // Wait for user
                clearScreen();
            }
        }
    }

 // --- Calculator Menu ---
    public static void calculatorMenu() throws InterruptedException {
        while (true) {
            // Header Box
            System.out.println(CYAN + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
            System.out.println("\t║                            CALCULATOR DASHBOARD                            ║");
            System.out.println("\t║                                                                              ║");
            System.out.println("\t║   ┌─────────────────────────────────────────────────────────────────────┐    ║");
            System.out.println("\t║   │    Dive into advanced math tools and unleash your inner genius!     │    ║");
            System.out.println("\t║   └─────────────────────────────────────────────────────────────────────┘    ║");
            System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);

            // ASCII Art: Calculator Menu Theme
            System.out.println(BLUE + "\n\t\t\t   _____________________");
            System.out.println("\t\t\t  |  _________________  |");
            System.out.println("\t\t\t  | |    CALC MENU    | |");
            System.out.println("\t\t\t  | |_________________| |");
            System.out.println("\t\t\t  |  ___ ___ ___   ___  |");
            System.out.println("\t\t\t  | | 1 | 2 | 3 | | + | |");
            System.out.println("\t\t\t  | |___|___|___| |___| |");				
            System.out.println("\t\t\t  | | 4 | 5 | 6 | | - | |");
            System.out.println("\t\t\t  | |___|___|___| |___| |");
            System.out.println("\t\t\t  | | 7 | 8 | 9 | | * | |");
            System.out.println("\t\t\t  | |___|___|___| |___| |");
            System.out.println("\t\t\t  | | 0 | . | = | | / | |");
            System.out.println("\t\t\t  | |___|___|___| |___| |");
            System.out.println("\t\t\t  |_____________________|" + RESET);

            // Options List in a Box
            System.out.println(GREEN + "\n\t╔══════════════════════════════════════════════╗");
            System.out.println("\t║                SELECT AN OPTION              ║");
            System.out.println("\t╠══════════════════════════════════════════════╣");
            System.out.println("\t║  [1] Basic Calculator (+, -, *, /)           ║");
            System.out.println("\t║  [2] Conversion (mm, cm, m)                  ║");
            System.out.println("\t║  [3] Area & Circumference of Circle          ║");
            System.out.println("\t║  [4] Odd or Even Checker                     ║");
            System.out.println("\t║  [5] Back to Main Menu                       ║");
            System.out.println("\t╚══════════════════════════════════════════════╝" + RESET);

            // Input Prompt
            System.out.print("\n\t" + YELLOW + "Enter your choice: " + RESET);
            
            try {
                choice = sc.nextInt();
                clearScreen();
                switch (choice) {
                    case 1 -> basicCalculator();
                    case 2 -> conversion();
                    case 3 -> circle();
                    case 4 -> oddEven();
                    case 5 -> { clearScreen(); return; }
                    default -> {
                        System.out.println(RED + "\n\t╔══════════════════════════════════════╗");
                        System.out.println("\t║            INVALID CHOICE!           ║");
                        System.out.println("\t║  Please select 1-5.                  ║");
                        System.out.println("\t╚══════════════════════════════════════╝" + RESET);
                        System.out.print(YELLOW + "\n\tPress Enter to try again..." + RESET);
                        sc.nextLine(); // Clear buffer
                        sc.nextLine(); // Wait for user
                        clearScreen();
                    }
                }
            } catch (InputMismatchException e) {
                sc.nextLine();
                System.out.println(RED + "\n\t╔══════════════════════════════════════╗");
                System.out.println("\t║            INVALID INPUT!            ║");
                System.out.println("\t║        Please enter a number.        ║");
                System.out.println("\t╚══════════════════════════════════════╝" + RESET);
                System.out.print(YELLOW + "\n\tPress Enter to try again..." + RESET);
                sc.nextLine(); // Wait for user
                clearScreen();
            }
        }
    }

 // --- Basic Calculator ---
    public static void basicCalculator() {
        // Advanced Design: Calculator-themed ASCII art
        System.out.println(BLUE + "\n\t╔══════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                     BASIC CALCULATOR                         ║");
        System.out.println("\t║                                                              ║");
        System.out.println("\t║   ┌─────────────────────────────────────────────────────┐    ║");
        System.out.println("\t║   │             [ + ]  [ - ]  [ * ]  [ / ]              │    ║");
        System.out.println("\t║   │                                                     │    ║");
        System.out.println("\t║   │        Perform simple arithmetic operations!        │    ║");
        System.out.println("\t║   └─────────────────────────────────────────────────────┘    ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════╝" + RESET);

        System.out.print(CYAN + "\n\tEnter first number: " + RESET);
        double num1 = sc.nextDouble();
        System.out.print(CYAN + "\tEnter operator (+, -, *, /): " + RESET);
        char op = sc.next().charAt(0);
        System.out.print(CYAN + "\tEnter second number: " + RESET);
        double num2 = sc.nextDouble();

        double result;
        switch (op) {
            case '+' -> result = num1 + num2;
            case '-' -> result = num1 - num2;
            case '*' -> result = num1 * num2;
            case '/' -> {
                if (num2 == 0) {
                    System.out.println(RED + "\n\tError: Cannot divide by zero!" + RESET);
                    return;
                }
                result = num1 / num2;
            }
            default -> {
                System.out.println(RED + "\n\tInvalid operator!" + RESET);
                return;
            }
        }

        System.out.println(GREEN + "\n\t╔══════════════════════════════════════╗");
        System.out.println("\t║              RESULT                  ║");
        System.out.println("\t║  " + String.format("%.2f", num1) + " " + op + " " + String.format("%.2f", num2) + " = " + String.format("%.2f", result) + "  ║");
        System.out.println("\t╚══════════════════════════════════════╝" + RESET);

        // Continue prompt
        System.out.print(YELLOW + "\n\tPress Enter to return to Calculator Menu..." + RESET);
        sc.nextLine(); // Clear buffer
        sc.nextLine(); // Wait for user
    }

    // --- Conversion ---
    public static void conversion() {
        // Advanced Design: Ruler-themed ASCII art
        System.out.println(BLUE + "\n\t╔══════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                     CONVERSION TOOL                          ║");
        System.out.println("\t║                                                              ║");
        System.out.println("\t║   ┌─────────────────────────────────────────────────────┐    ║");
        System.out.println("\t║   │  mm ────► cm  |  cm ────► m  |  m ────► cm          │    ║");
        System.out.println("\t║   │                                                     │    ║");
        System.out.println("\t║   │  Choose your unit conversion!                       │    ║");
        System.out.println("\t║   └─────────────────────────────────────────────────────┘    ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════╝" + RESET);
        System.out.println("\t1. mm → cm");
        System.out.println("\t2. cm → m");
        System.out.println("\t3. m → cm");
        System.out.print(CYAN + "\n\tChoose conversion: " + RESET);
        int c = sc.nextInt();

        System.out.print(CYAN + "\tEnter value: " + RESET);
        double val = sc.nextDouble();
        double result = 0;
        String fromUnit = "", toUnit = "";

        switch (c) {
            case 1 -> { result = val / 10; fromUnit = "mm"; toUnit = "cm"; }
            case 2 -> { result = val / 100; fromUnit = "cm"; toUnit = "m"; }
            case 3 -> { result = val * 100; fromUnit = "m"; toUnit = "cm"; }
            default -> {
                System.out.println(RED + "\n\tInvalid conversion type!" + RESET);
                return;
            }
        }

        System.out.println(GREEN + "\n\t╔══════════════════════════════════════╗");
        System.out.println("\t║              RESULT                  ║");
        System.out.println("\t║  " + String.format("%.2f", val) + " " + fromUnit + " → " + String.format("%.2f", result) + " " + toUnit + "  ║");
        System.out.println("\t╚══════════════════════════════════════╝" + RESET);

        // Continue prompt
        System.out.print(YELLOW + "\n\tPress Enter to return to Calculator Menu..." + RESET);
        sc.nextLine(); // Clear buffer
        sc.nextLine(); // Wait for user
    }

    // --- Area & Circumference ---
    public static void circle() {
        // Advanced Design: Circle-themed ASCII art
        System.out.println(BLUE + "\n\t╔══════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                 AREA & CIRCUMFERENCE OF CIRCLE               ║");
        System.out.println("\t║                                                              ║");
        System.out.println("\t║                           _______                            ║");
        System.out.println("\t║                         /         \\                         ║");
        System.out.println("\t║                        |     □     |                         ║");
        System.out.println("\t║                         \\ _______ /                         ║");
        System.out.println("\t║                                                              ║");
        System.out.println("\t║              Area: πr²    |    Circumference: 2πr            ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════╝" + RESET);

        System.out.print(CYAN + "\n\tEnter radius: " + RESET);
        double r = sc.nextDouble();

        double area = Math.PI * r * r;
        double circumference = 2 * Math.PI * r;

        System.out.println(GREEN + "\n\t╔══════════════════════════════════════╗");
        System.out.println("\t║              RESULTS                 ║");
        System.out.println("\t║  Area: " + String.format("%.2f", area) + "                          ║");
        System.out.println("\t║  Circumference: " + String.format("%.2f", circumference) + "                  ║");
        System.out.println("\t╚══════════════════════════════════════╝" + RESET);

        // Continue prompt
        System.out.print(YELLOW + "\n\tPress Enter to return to Calculator Menu..." + RESET);
        sc.nextLine(); // Clear buffer
        sc.nextLine(); // Wait for user
    }

    // --- Odd or Even ---
    public static void oddEven() {
        // Advanced Design: Binary-themed ASCII art
        System.out.println(BLUE + "\n\t╔══════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                     ODD OR EVEN                              ║");
        System.out.println("\t║                                                              ║");
        System.out.println("\t║   ┌─────────────────────────────────────────────────────┐    ║");
        System.out.println("\t║   │  01010101  |  Even: Divisible by 2                  │    ║");
        System.out.println("\t║   │  10101010  |  Odd: Not divisible by 2               │    ║");
        System.out.println("\t║   │                                                     │    ║");
        System.out.println("\t║   │  Check if your number is even or odd!               │    ║");
        System.out.println("\t║   └─────────────────────────────────────────────────────┘    ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════╝" + RESET);

        System.out.print(CYAN + "\n\tEnter a number: " + RESET);
        int num = sc.nextInt();

        String result = (num % 2 == 0) ? "EVEN" : "ODD";
        String color = (num % 2 == 0) ? GREEN : YELLOW;

        System.out.println(color + "\n\t╔══════════════════════════════════════╗");
        System.out.println("\t║              RESULT                  ║");
        System.out.println("\t║  " + num + " is " + result + "                         1   ║");
        System.out.println("\t╚══════════════════════════════════════╝" + RESET);

        // Continue prompt
        System.out.print(YELLOW + "\n\tPress Enter to return to Calculator Menu..." + RESET);
        sc.nextLine(); // Clear buffer
        sc.nextLine(); // Wait for user
    }

 // --- About ---
    public static void about() throws InterruptedException {
        // Quick "loading" animation for flair
        System.out.println(CYAN + "\n\tLoading About Section..." + RESET);
        Thread.sleep(500);
        System.out.println(GREEN + "\t✔ Loaded!" + RESET);
        Thread.sleep(300);

        // Main Header Box
        System.out.println(BLUE + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                          ABOUT GENESISANDTHETROOPS                           ║");
        System.out.println("\t║                                                                              ║");
        System.out.println("\t║   ┌─────────────────────────────────────────────────────────────────────┐    ║");
        System.out.println("\t║   │  A sleek, console-based calculator built with passion and Java!     │    ║");
        System.out.println("\t║   │  Unleash the power of math in style.                                │    ║");
        System.out.println("\t║   └─────────────────────────────────────────────────────────────────────┘    ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);

        // ASCII Art: Calculator Theme
        System.out.println(YELLOW + "\n\t\t\t   _____________________");
        System.out.println("\t\t\t  |  _________________  |");
        System.out.println("\t\t\t  | | GENESIS&THE     | |");
        System.out.println("\t\t\t  | | TROOPS CALC     | |");
        System.out.println("\t\t\t  | |_________________| |");
        System.out.println("\t\t\t  |  ___ ___ ___   ___  |");
        System.out.println("\t\t\t  | | 7 | 8 | 9 | | + | |");
        System.out.println("\t\t\t  | |___|___|___| |___| |");
        System.out.println("\t\t\t  | | 4 | 5 | 6 | | - | |");
        System.out.println("\t\t\t  | |___|___|___| |___| |");
        System.out.println("\t\t\t  | | 1 | 2 | 3 | | * | |");
        System.out.println("\t\t\t  | |___|___|___| |___| |");
        System.out.println("\t\t\t  | | . | 0 | = | | / | |");
        System.out.println("\t\t\t  | |___|___|___| |___| |");
        System.out.println("\t\t\t  |_____________________|" + RESET);

        // Features Section
        System.out.println(CYAN + "\n\t╔══════════════════════════════════════════════╗");
        System.out.println("\t║                  FEATURES                    ║");
        System.out.println("\t╠══════════════════════════════════════════════╣");
        System.out.println("\t║  • Basic Arithmetic (+, -, *, /)             ║");
        System.out.println("\t║  • Unit Conversions (mm, cm, m)              ║");
        System.out.println("\t║  • Circle Area & Circumference               ║");
        System.out.println("\t║  • Odd or Even Checker                       ║");
        System.out.println("\t║  • Colorful, Animated UI                     ║");
        System.out.println("\t╚══════════════════════════════════════════════╝" + RESET);

        // Team Section
        System.out.println(GREEN + "\n\t╔══════════════════════════════════════════════╗");
        System.out.println("\t║                 DEVELOPED BY                 ║");
        System.out.println("\t╠══════════════════════════════════════════════╣");
        System.out.println("\t║  • Genesis Aguirre                           ║");
        System.out.println("\t║  • Mark Johnnel Lagahit                      ║");
        System.out.println("\t║  • Jerson Mamaril                            ║");
        System.out.println("\t║  • Gian Carlo Bulac                          ║");
        System.out.println("\t║  • Ianjie Las Marias                         ║");
        System.out.println("\t╚══════════════════════════════════════════════╝" + RESET);

        // Footer with Fun Note
        System.out.println(YELLOW + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                            THANK YOU FOR EXPLORING!                        ║");
        System.out.println("\t║                                                                              ║");
        System.out.println("\t║   ┌─────────────────────────────────────────────────────────────────────┐    ║");
        System.out.println("\t║   │          Feedback? We'd love to hear it! Keep calculating           │    ║");
        System.out.println("\t║   └─────────────────────────────────────────────────────────────────────┘    ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);

        // Prompt to return
        System.out.print("\n\t" + GREEN + "Press Enter to return to Main Menu..." + RESET);
        sc.nextLine(); // Clear buffer
        sc.nextLine(); // Wait for user
    }

 // --- Outing Screen (Exit Animation) ---
    public static void outingScreen() throws InterruptedException {
        // Stage 1: Initial Shutdown Warning
        System.out.println(RED + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                             SYSTEM SHUTDOWN INITIATED                        ║");
        System.out.println("\t║                                                                              ║");
        System.out.println("\t║  ┌─────────────────────────────────────────────────────────────────────┐     ║");
        System.out.println("\t║  │                  Preparing to shut down all processes...            │     ║");
        System.out.println("\t║  └─────────────────────────────────────────────────────────────────────┘     ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);
        Thread.sleep(1000);

        // Custom ASCII Art Display
        System.out.println(CYAN + "\n\tDisplaying Farewell Art..." + RESET);
        Thread.sleep(500);
        System.out.println(BLUE + "\n\t───────────────█───────────────█");
        System.out.println("\t────────────██─────────────██");
        System.out.println("\t─────────────███████████████");
        System.out.println("\t────────────█████████████████");
        System.out.println("\t───────────███████████████████");
        System.out.println("\t──────────████──█████████──████");
        System.out.println("\t─────────███████████████████████");
        System.out.println("\t────────█████████████████████████");
        System.out.println("\t────────█████████████████████████");
        System.out.println("\t───███──▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒──███");
        System.out.println("\t──█████─█████████████████████████─█████");
        System.out.println("\t──█████─████████████████──███████─█████");
        System.out.println("\t──█████─██████────────█──█────███─█████");
        System.out.println("\t──█████─█████─▓▓▓▓▓▓▓█──█▓▓─▓─███─█████");
        System.out.println("\t──█████─███─█─▓▓▓▓▓▓█──█▓▓─▓▓─███─█████");
        System.out.println("\t──█████─██──█─▓▓▓▓▓█──█▓▓─▓▓▓─███─█████");
        System.out.println("\t──█████─███─█─▓▓▓▓█──█▓▓─▓▓▓▓─███─█████");
        System.out.println("\t──█████─█████────█──█─────────███─█████");
        System.out.println("\t──█████─█████████──██████████████─█████");
        System.out.println("\t───███──████████──███████████████──███");
        System.out.println("\t────────█████████████████████████");
        System.out.println("\t─────────███████████████████████");
        System.out.println("\t──────────█████████████████████");
        System.out.println("\t─────────────██████───██████");
        System.out.println("\t─────────────██████───██████");
        System.out.println("\t─────────────██████───██████");
        System.out.println("\t─────────────██████───██████");
        System.out.println("\t──────────────████─────████" + RESET);
        System.out.println(GREEN + "\t\t\t      👋 See You Soon! 👋" + RESET);
        Thread.sleep(1000);

        // Stage 2: Progress Animation with Phases
        String[] phases = {"Initializing Shutdown", "Closing Processes", "Saving Data", "Finalizing Exit"};
        String[] cursors = {"|", "/", "-", "\\"}; // Spinning cursor
        int totalSteps = 20; // Total progress steps

        for (int phase = 0; phase < phases.length; phase++) {
            System.out.println(YELLOW + "\n\t" + phases[phase] + "..." + RESET);
            for (int i = 0; i < totalSteps; i++) {
                int percentage = (i + 1) * 5; // 5% per step
                String bar = "[" + "█".repeat(i) + "░".repeat(totalSteps - i - 1) + "] " + percentage + "% " + cursors[i % 4];
                System.out.print(RED + "\r\t\t" + bar + RESET);
                Thread.sleep(150); // Faster for dynamism
            }
            System.out.println(GREEN + " ✔ Complete!" + RESET);
            Thread.sleep(500);
        }

        // Stage 3: Final Countdown
        System.out.println(CYAN + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                              FINALIZING SHUTDOWN                             ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);
        for (int count = 3; count > 0; count--) {
            System.out.println(YELLOW + "\n\t\t\t\t\t\t" + count + "...");
            Thread.sleep(800);
        }

        // Stage 4: Farewell Message
        clearScreen();
        System.out.println(GREEN + "\n\t╔══════════════════════════════════════════════════════════════════════════════╗");
        System.out.println("\t║                              SYSTEM CLOSED SUCCESSFULLY                      ║");
        System.out.println("\t║                                                                              ║");
        System.out.println("\t║   ┌─────────────────────────────────────────────────────────────────────┐    ║");
        System.out.println("\t║   │  Thank you for using GENESISANDTHETROOPS Calculator!                │    ║");
        System.out.println("\t║   │  Developed by: Genesis Aguirre, Mark Johnnel Lagahit,               │    ║");
        System.out.println("\t║   │                 Jerson Mamaril, Gian Carlo Bulac,                   │    ║");
        System.out.println("\t║   │                 Ianjie Las Marias                                   │    ║");
        System.out.println("\t║   └─────────────────────────────────────────────────────────────────────┘    ║");
        System.out.println("\t║                                                                              ║");
        System.out.println("\t║                          Have a great day!                                   ║");
        System.out.println("\t╚══════════════════════════════════════════════════════════════════════════════╝" + RESET);
        Thread.sleep(2000);
        System.exit(0);
    }
}
