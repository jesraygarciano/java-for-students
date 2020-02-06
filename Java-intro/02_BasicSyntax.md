# BasicSyntax

## Agenda
  1. [Slide 「What is Java ?」](https://docs.google.com/presentation/d/1d8TF1DyIyE2U7JWaO2YCrFvYgFtr6xHDZ2PsUaZDZuk/edit?usp=sharing)
  2. Basic Syntax

## 2. Basic Syntax

```
public class Main {

	public static void main(String[] args) {
		
		// 1. Variables
		int num = 1;
		boolean flg = true;
		String name = "SeedKun";
		
		// Error Example
//		num = "1";
//		name = 1;
		
		// 2. Operators
		System.out.println(1 + 1);
		System.out.println(2 - 1);
		System.out.println(2 * 2);
		System.out.println(4 / 2);
		System.out.println(4 / 3);
		
		// 3. If statements
		int time = 22;
		if (time < 10) {
			System.out.println("Good mirning.");
		} else if (time < 20) {
			System.out.println("Good day.");
		} else {
			System.out.println("Good evening.");
		}
		
		// 4. Switch statements
		int gender = 1;
		switch (gender) {
		case 1:
			System.out.println("Male");
			break;
			
		case 2:
			System.out.println("Female");
			break;
			
		default:
			System.out.println("Unknown");
			break;
		}
		
		// 5. Arrays
		String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
		int[] scores = {60, 40, 70, 90};
		System.out.println(cars[0]);
		System.out.println(scores[2]);
		
		// 6. While
		int i = 0;
		while (i < 5) {
			System.out.println(i);
			i++;
		}
		
		// 7. For
		for (int j = 0; j < 10; j++) {
			System.out.println(j);
		}
		
		// 8. ArrayList
		ArrayList<String> carList = new ArrayList<>();
		carList.add("Volvo");
		carList.add("BMW");
		carList.add("Ford");
		carList.add("Mazda");
		
		System.out.println(carList);
		
		carList.remove(0);
		carList.remove("Mazda");
		
		System.out.println(carList);
		
		// 9. Method
		sample();
		sample("NexSeed");
	}
	
	private static void sample() {
		
		System.out.println("This is example");

	}
	
	private static void sample(String name) {
		
		System.out.println("My name is + " + name);

	}
}

```