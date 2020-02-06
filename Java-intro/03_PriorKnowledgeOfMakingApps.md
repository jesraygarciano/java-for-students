# PriorKnowledgeOfMakingApps

- Before creating an app, I want to study the technology used in the app to be created.

## Const
> One of the "boxes for storing values" in programming languages.  
> The value entered first cannot be changed later.

### (ex）
> final double PI = 3.14;

## Scanner Class
> This class for handling text input.

- When you want to input text

```
Scanner scanner = new Scanner(System.in);
System.out.print("Please input text：");
String text = scanner.nextLine();
System.out.println(text);
```

- When you want to input number

```
System.out.print("Please input number：");
int number = scanner.nextInt();
System.out.println(number);
```

## Random Number

```
Random rand = new Random();
// 0 〜 2
int randomNumber = rand.nextInt(3);

// 0 〜 4
randomNumber = rand.nextInt(5);
```