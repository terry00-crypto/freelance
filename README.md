Project #1

@RestController
public class ProgressController {

    @Autowired
    private ProgressRepository progressRepository;

    @GetMapping("/progress")
    public Progress getProgress(@RequestParam("userId") Long userId) {
        return progressRepository.findByUserId(userId);
    }
}


#
CREATE TABLE user_progress (
    id BIGINT AUTO_INCREMENT PRIMARY KEY,
    user_id BIGINT NOT NULL,
    question_id BIGINT NOT NULL,
    completed BOOLEAN NOT NULL DEFAULT FALSE,
    created_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP NOT NULL DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    CONSTRAINT fk_user FOREIGN KEY (user_id) REFERENCES users(id),
    CONSTRAINT fk_question FOREIGN KEY (question_id) REFERENCES questions(id)
);



Project #

# import java.util.Scanner;

public class Palindrome {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String str = scanner.nextLine();

        if (isPalindrome(str)) {
            System.out.println(str + " is a palindrome.");
        } else {
            System.out.println(str + " is not a palindrome.");
        }
    }

    public static boolean isPalindrome(String str) {
        int length = str.length();
        for (int i = 0; i < length / 2; i++) {
            if (str.charAt(i) != str.charAt(length - i - 1)) {
                return false;
            }
        }
        return true;
    }
}


Project #3 - Write a function that takes in an array of numbers and prints the
combinations that add up to 10.

public static void printCombinationsThatAddUpToTen(int[] arr) {
    int n = arr.length;
    for (int i = 0; i < n; i++) {
        for (int j = i + 1; j < n; j++) {
            if (arr[i] + arr[j] == 10) {
                System.out.println(arr[i] + " + " + arr[j] + " = 10");
            }
        }
    }
}

int[] arr = { 1, 2, 3, 4, 5, 6, 7, 8, 9 };
printCombinationsThatAddUpToTen(arr);


Project #4 – Write a fully functioning java application that takes an integer as a command line argument
n, and outputs the nth hexagonal number for the input?


public class HexagonalNumber {
    public static void main(String[] args) {
        if (args.length == 0) {
            System.out.println("Please provide an integer as an argument.");
            return;
        }
        
        int n = 0;
        try {
            n = Integer.parseInt(args[0]);
        } catch (NumberFormatException e) {
            System.out.println("The argument must be an integer.");
            return;
        }
        
        if (n < 1) {
            System.out.println("The argument must be a positive integer.");
            return;
        }
        
        int hexagonalNumber = getHexagonalNumber(n);
        System.out.println("The " + n + "th hexagonal number is " + hexagonalNumber + ".");
    }
    
    public static int getHexagonalNumber(int n) {
        return n * (2 * n - 1);
    }
}





