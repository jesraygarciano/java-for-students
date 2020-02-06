# ConsoleApp 〜Hit And Blow〜

## Rule
- This is a game to guess 3-digit numbers made by a personal computer.
- You enter three numbers
- If the numbers and location match, HIT will be counted.
- If the numbers are correct but in the wrong place, BLOW will be counted.
- (Example) If computer is 「014」and you enter 「412」,
- HIT is 1 because 「1」 matches the number and the location.
- 「4」 have the same number, but the location is different, so BLOW is 2.

## Let's create
1. Create New Project and New Class
2. Add main method
3. Create a unique 3 digit random number
4. User input 3 digit number
5. Judge computer numbers and user input
6. Display result
7. Add turn logic
8. remove Unnecessary code
9. make function automaticaly (This is option)

### 3. Create a unique 3 digit random number
- Generate a 3-digit random number from 0 to 9.
- The three digits are unique.

1. create new function

    ```Java
    private static List<Integer> generateNumbers() {

    }
    ```

2. create ArrayList for computer numbers

    ```Java
    private static List<Integer> generateNumbers() {
      List<Integer> numbers = new ArrayList<>();

      return numbers;
    }
    ```

3. Let's call the method

    ```Java
    public static void main(String[] args) {

      List<Integer> numbers = generateNumbers();

      System.out.println(numbers);
    }
    ```

4. Add Random Numbers to ArrayList

    ```Java
    private static List<Integer> generateNumbers() {
      List<Integer> numbers = new ArrayList<>();

      Random rand = new Random();
      int randomNumber = rand.nextInt(10);
      numbers.add(randomNumber);
      randomNumber = rand.nextInt(10);
      numbers.add(randomNumber);
      randomNumber = rand.nextInt(10);
      numbers.add(randomNumber);

      return numbers;
    }
    ```

5. add while loop

    1. Add const for digit

      ```Java
      public class Main {

        private static final int DIGIT_NUMBER = 3;
      ```

    2. add logic

      ```Java
      private static List<Integer> generateNumbers() {
        List<Integer> numbers = new ArrayList<>();

        Random rand = new Random();

        while (numbers.size() < DIGIT_NUMBER) {
          int randomNumber = rand.nextInt(10);
          numbers.add(randomNumber);

        }
        return numbers;
      }
      ```

5. Add logic for unique number

    ```Java
    private static List<Integer> generateNumbers() {
      List<Integer> numbers = new ArrayList<>();

      Random rand = new Random();

      while (numbers.size() < DIGIT_NUMBER) {
        int randomNumber = rand.nextInt(10);
        if (!numbers.contains(randomNumber)) {
          numbers.add(randomNumber);
        }
      }
      return numbers;
    }
    ```

### 4. User input 3 digit number

1. create new function

    ```Java
    private static List<Integer> inputNumbers() {
      List<Integer> userNumbers = new ArrayList<>();

      return userNumbers;
    }
    ```

2. Add user input logic

    ```Java
    private static List<Integer> inputNumbers() {
      List<Integer> userNumbers = new ArrayList<>();

      Scanner scanner = new Scanner(System.in);

      System.out.print("Please enter the First digit：");

      int num = scanner.nextInt();

      userNumbers.add(num);

      return userNumbers;
    }
    ```

3. Let's call the method

    ```Java
    public static void main(String[] args) {

      List<Integer> numbers = generateNumbers();

      System.out.println(numbers);

      List<Integer> userNumbers = inputNumbers();

      System.out.println(userNumbers);
    }
    ```

4. Add loop for input 3 numbers

    ```Java
    private static List<Integer> inputNumbers() {

      List<Integer> userNumbers = new ArrayList<>();

      Scanner scanner = new Scanner(System.in);

      for (int i = 1; i <= DIGIT_NUMBER; i++) {
        System.out.print("Please enter the First digit：");

        int num = scanner.nextInt();

        userNumbers.add(num);
      }

      return userNumbers;
    }
    ```

5. Create function for switching Ordinal text

    > Current code, every time print `Please enter the First digit：`


    1. make new function

        ```Java
        private static void convertIntToOrdinal(int number) {

        }
        ```

    2. add return

        ```Java
        private static String convertIntToOrdinal(int number) {
          String ordinal = "";

          return ordinal;
        }
        ```

    3. Add switch

        ```Java
        private static String convertIntToOrdinal(int number) {
          String ordinal = "";

          switch (number) {
          case 1:
            ordinal = "First";
            break;

          case 2:
            ordinal = "Second";
            break;

          case 3:
            ordinal = "Third";
            break;

          default:
            break;
          }

          return ordinal;
        }
        ```

    4. Call the function

        ```Java
        private static List<Integer> inputNumbers() {
          List<Integer> userNumbers = new ArrayList<>();

          Scanner scanner = new Scanner(System.in);

          for (int i = 1; i <= DIGIT_NUMBER; i++) {
            String ordinal = convertIntToOrdinal(i);
            System.out.print("Please enter the " + ordinal + " digit：");

            int num = scanner.nextInt();

            userNumbers.add(num);
          }

          return userNumbers;
        }
        ```

### 5. Judge computer numbers and user input

1. make new function

    ```Java
    private static void judge(List<Integer> array1, List<Integer> array2) {

    }
    ```

2. return result

    ```Java
    private static boolean judge(List<Integer> array1, List<Integer> array2) {
      return array1.equals(array2);
    }
    ```

3. Let's call the method

    ```Java
    public static void main(String[] args) {

      List<Integer> numbers = generateNumbers();

      System.out.println(numbers);

      List<Integer> userNumbers = inputNumbers();

      System.out.println(userNumbers);

      if (judge(numbers, userNumbers)) {
        System.out.println("Correct");
      } else {
        System.out.println("Incorrect");
      }
    }
    ```

### 6. Display result

1. make new function

    ```Java
    private static void displayResult() {

    }
    ```

2. Add print logic

    ```Java
    private static void displayResult() {
      int hit = 0;
      int blow = 0;

      System.out.println("===Result===");
      System.out.println(hit + "HIT, " + blow + "BLOW");
      System.out.println("============");
    }
    ```

3. Call method

    ```Java
    public static void main(String[] args) {

      List<Integer> numbers = generateNumbers();

      System.out.println(numbers);

      List<Integer> userNumbers = inputNumbers();

      System.out.println(userNumbers);

      if (judge(numbers, userNumbers)) {
        System.out.println("Correct");
      } else {
        displayResult();
      }
    }
    ```

4. make new function for count Hit

    ```Java
    private static int countHit(List<Integer> numbers, List<Integer> userNumbers) {
      int count = 0;

      return count;
    }
    ```

    > HIT is that matches the number and the location.


    ```Java
    private static int countHit(List<Integer> numbers, List<Integer> userNumbers) {
      int count = 0;

      for (int i = 0; i < DIGIT_NUMBER; i++) {
        if (numbers.get(i) == userNumbers.get(i)) {
          count++;
        }
      }

      return count;
    }
    ```

5. make new function for count Blow

    ```Java
    private static int countBlow(List<Integer> numbers, List<Integer> userNumbers) {
      int count = 0;

      return count;
    }
    ```

    > BLOW is that have the same number, but the location is different.

    ```Java
    private static int countBlow(List<Integer> numbers, List<Integer> userNumbers) {
      int count = 0;

      for (int i = 0; i < DIGIT_NUMBER; i++) {
        if (numbers.get(i) != userNumbers.get(i) && userNumbers.contains(numbers.get(i))) {
          count++;
        }
      }

      return count;
    }
    ```

6. Let's use hit and blow function

    ```Java
    private static void displayResult(List<Integer> numbers, List<Integer> userNumbers) {
      int hit = countHit(numbers, userNumbers);
      int blow = countBlow(numbers, userNumbers);

      System.out.println("===Result===");
      System.out.println(hit + "HIT, " + blow + "BLOW");
      System.out.println("============");
    }
    ```

    ```Java
    public static void main(String[] args) {

      List<Integer> numbers = generateNumbers();

      System.out.println(numbers);

      List<Integer> userNumbers = inputNumbers();

      System.out.println(userNumbers);

      if (judge(numbers, userNumbers)) {
        System.out.println("Correct");
      } else {
        displayResult(numbers, userNumbers);
      }
    }
    ```

### 7. Add turn logic

1. Add while loop until user clear game

    ```Java
    public static void main(String[] args) {

      List<Integer> numbers = generateNumbers();

      System.out.println(numbers);

      while (true) {
        List<Integer> userNumbers = inputNumbers();

        System.out.println(userNumbers);

        if (judge(numbers, userNumbers)) {
          System.out.println("Correct");
          break;
        } else {
          displayResult(numbers, userNumbers);
        }
      }
    }
    ```

2. Add variables for counting turn

    ```Java
    public static void main(String[] args) {

      List<Integer> numbers = generateNumbers();

      System.out.println(numbers);

      int turnNum = 0;

      while (true) {

        turnNum++;

        List<Integer> userNumbers = inputNumbers();

        System.out.println(userNumbers);

        if (judge(numbers, userNumbers)) {
          System.out.println("Correct");
          break;
        } else {
          displayResult(numbers, userNumbers);
        }
      }
    }
    ```

3. Print result with turn count

    ```Java
    public static void main(String[] args) {

      List<Integer> numbers = generateNumbers();

      System.out.println(numbers);

      int turnNum = 0;

      while (true) {

        turnNum++;

        List<Integer> userNumbers = inputNumbers();

        System.out.println(userNumbers);

        if (judge(numbers, userNumbers)) {
          System.out.println("！！！！！Game Clear！！！！！");
				  System.out.println("Completed in " + turnNum + " turns");
          break;
        } else {
          displayResult(numbers, userNumbers);
        }
      }
    }
    ```

### 8. remove Unnecessary code

  ```Java
  public static void main(String[] args) {

    List<Integer> numbers = generateNumbers();

    // no need
    // System.out.println(numbers);

    int turnNum = 0;

    while (true) {

      turnNum++;

      List<Integer> userNumbers = inputNumbers();

      // no need
      // System.out.println(userNumbers);

      if (judge(numbers, userNumbers)) {
        System.out.println("！！！！！Game Clear！！！！！");
        System.out.println("Completed in " + turnNum + " turns");
        break;
      } else {
        displayResult(numbers, userNumbers);
      }
    }
  }
  ```

### 9. make function automaticaly (This is option)

1. Select these lines.

    ```Java
    System.out.println("！！！！！Game Clear！！！！！");
    System.out.println("Completed in " + turnNum + " turns");
    ```

2. Right click ➞ 「Refactor」 ➞ 「Extract Method...」

    <img src="./images/09.png">

3. Input method name
    > method name is 「displayResult」

    <img src="./images/10.png">