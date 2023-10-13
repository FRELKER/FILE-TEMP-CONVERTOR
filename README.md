# FILE-TEMP-CONVERTOR
This is the Internship project where I write a code for Temperature Convertor and Quiz  using Java and Python  Language respectively

    import java.util.Scanner;

     public class TemperatureConverterApp {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        while (true) {
            System.out.println("Temperature Converter App");
            System.out.println("1. Celsius to Fahrenheit");
            System.out.println("2. Fahrenheit to Celsius");
            System.out.println("3. Celsius to Kelvin");
            System.out.println("4. Kelvin to Celsius");
            System.out.println("5. Fahrenheit to Kelvin");
            System.out.println("6. Kelvin to Fahrenheit");
            System.out.println("7. Quit");
            System.out.print("Select an option: ");

            int choice = input.nextInt();
            
            if (choice == 7) {
                System.out.println("Goodbye! Kindly visit again.");
                break;
            }
            
            double temperature;
            
            switch (choice) {
                case 1:
                    System.out.print("Enter temperature in Celsius: ");
                    temperature = input.nextDouble();
                    System.out.println("Temperature in Fahrenheit: " + celsiusToFahrenheit(temperature));
                    break;
                case 2:
                    System.out.print("Enter temperature in Fahrenheit: ");
                    temperature = input.nextDouble();
                    System.out.println("Temperature in Celsius: " + fahrenheitToCelsius(temperature));
                    break;
                case 3:
                    System.out.print("Enter temperature in Celsius: ");
                    temperature = input.nextDouble();
                    System.out.println("Temperature in Kelvin: " + celsiusToKelvin(temperature));
                    break;
                case 4:
                    System.out.print("Enter temperature in Kelvin: ");
                    temperature = input.nextDouble();
                    System.out.println("Temperature in Celsius: " + kelvinToCelsius(temperature));
                    break;
                case 5:
                    System.out.print("Enter temperature in Fahrenheit: ");
                    temperature = input.nextDouble();
                    System.out.println("Temperature in Kelvin: " + fahrenheitToKelvin(temperature));
                    break;
                case 6:
                    System.out.print("Enter temperature in Kelvin: ");
                    temperature = input.nextDouble();
                    System.out.println("Temperature in Fahrenheit: " + kelvinToFahrenheit(temperature));
                    break;
                default:
                    System.out.println("Invalid option. Please select a valid option.");
                    break;
            }
        }
        
        input.close();
    }
    
    // Conversion methods
    public static double celsiusToFahrenheit(double celsius) {
        return (celsius * 9/5) + 32;
    }
    
    public static double fahrenheitToCelsius(double fahrenheit) {
        return (fahrenheit - 32) * 5/9;
    }
    
    public static double celsiusToKelvin(double celsius) {
        return celsius + 273.15;
    }
    
    public static double kelvinToCelsius(double kelvin) {
        return kelvin - 273.15;
    }
    
    public static double fahrenheitToKelvin(double fahrenheit) {
        return (fahrenheit + 459.67) * 5/9;
    }
    
    public static double kelvinToFahrenheit(double kelvin) {
        return (kelvin * 9/5) - 459.67;
    }
    }



CODE QUIZ

     import random

    class Quiz:
    def __init__(self, questions):
        self.questions = questions
        self.score = 0

    def display_question(self, question):
        print(question["question"])
        for i, option in enumerate(question["options"], start=1):
            print(f"{i}. {option}")
        user_choice = input("Enter the number of your answer: ")
        return int(user_choice)

    def run(self):
        random.shuffle(self.questions)
        for question in self.questions:
            user_choice = self.display_question(question)
            if user_choice == question["answer"]:
                print("Correct!\n")
                self.score += 1
            else:
                print(f"Wrong! The correct answer was {question['options'][question['answer']-1]}\n")
        print(f"You got {self.score}/{len(self.questions)} questions correct.")

    if __name__ == "__main__":
    questions = [
        {
            "question": "What is the capital of France?",
            "options": ["Berlin", "Madrid", "Paris", "Rome"],
            "answer": 3,
        },
        {
            "question": "Which planet is known as the Red Planet?",
            "options": ["Mars", "Venus", "Jupiter", "Saturn"],
            "answer": 1,
        },
        {
            "question": "What is the largest mammal in the world?",
            "options": ["Elephant", "Blue Whale", "Giraffe", "Hippopotamus"],
            "answer": 2,
        },
    ]

    quiz = Quiz(questions)
    quiz.run()

