# codealpha_tasks_artificial_Intelligence_chatbot

# AI Chatbot using Java 🤖

A simple Artificial Intelligence Chatbot developed using Java.  
This chatbot interacts with users, answers questions, performs calculations, tells jokes, shows date & time, saves chat history, and more.

---

# 📌 Features

✅ Greeting Responses  
✅ NLP Basic Processing  
✅ Rule-Based AI Chatbot  
✅ User Name Recognition  
✅ Date & Time Feature  
✅ Calculator Operations  
✅ Random Jokes  
✅ Motivational Quotes  
✅ Chat History Saving  
✅ FAQ Responses  
✅ Exit Command  

---

# 🛠 Technologies Used

- Java
- OOP Concepts
- File Handling
- Scanner Class
- Random Class
- LocalDate & LocalTime

---

# 📂 Project Structure

```text
AI-Chatbot
│
├── Main.java
├── chat.txt
└── README.md
```

---

# ▶ How to Run

## Step 1
Open OnlineGDB / Replit / Any Java Compiler

## Step 2
Copy and paste the code into:

```text
Main.java
```

## Step 3
Run the program

---

# 💻 Complete Java Code

```java
import java.util.Scanner;
import java.util.Random;
import java.time.LocalDate;
import java.time.LocalTime;
import java.io.FileWriter;
import java.io.IOException;

class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        Random random = new Random();

        String userName = "";

        System.out.println("=================================");
        System.out.println("        AI CHATBOT");
        System.out.println("=================================");
        System.out.println("Type 'bye' to exit");
        System.out.println();

        while (true) {

            System.out.print("You: ");
            String input = sc.nextLine();

            String originalInput = input;

            input = input.toLowerCase();

            String response = "";

            // Greetings
            if (input.contains("hi") || input.contains("hello")) {

                String[] replies = {
                    "Hello!",
                    "Hi there!",
                    "Welcome!",
                    "Nice to meet you!"
                };

                response = replies[random.nextInt(replies.length)];
            }

            // Name Feature
            else if (input.startsWith("my name is")) {

                userName = originalInput.substring(11).trim();

                response = "Nice to meet you, " + userName + "!";
            }

            // How are you
            else if (input.contains("how are you")) {

                response = "I am fine and ready to help you!";
            }

            // Java Question
            else if (input.contains("java")) {

                response = "Java is a powerful object-oriented programming language.";
            }

            // Time Feature
            else if (input.contains("time")) {

                response = "Current Time: " + LocalTime.now().withNano(0);
            }

            // Date Feature
            else if (input.contains("date")) {

                response = "Today's Date: " + LocalDate.now();
            }

            // Calculator Add
            else if (input.startsWith("add")) {

                try {

                    String[] parts = input.split(" ");

                    int a = Integer.parseInt(parts[1]);
                    int b = Integer.parseInt(parts[2]);

                    response = "Sum = " + (a + b);

                } catch (Exception e) {

                    response = "Usage: add number1 number2";
                }
            }

            // Calculator Subtract
            else if (input.startsWith("sub")) {

                try {

                    String[] parts = input.split(" ");

                    int a = Integer.parseInt(parts[1]);
                    int b = Integer.parseInt(parts[2]);

                    response = "Difference = " + (a - b);

                } catch (Exception e) {

                    response = "Usage: sub number1 number2";
                }
            }

            // Calculator Multiply
            else if (input.startsWith("mul")) {

                try {

                    String[] parts = input.split(" ");

                    int a = Integer.parseInt(parts[1]);
                    int b = Integer.parseInt(parts[2]);

                    response = "Product = " + (a * b);

                } catch (Exception e) {

                    response = "Usage: mul number1 number2";
                }
            }

            // Calculator Divide
            else if (input.startsWith("div")) {

                try {

                    String[] parts = input.split(" ");

                    int a = Integer.parseInt(parts[1]);
                    int b = Integer.parseInt(parts[2]);

                    response = "Division = " + (a / b);

                } catch (Exception e) {

                    response = "Usage: div number1 number2";
                }
            }

            // Joke Feature
            else if (input.contains("joke")) {

                String[] jokes = {

                    "Why do programmers love Java? Because it has classes!",
                    "Why was the computer cold? Because it left Windows open!",
                    "Why do Java developers wear glasses? Because they don't C#!"
                };

                response = jokes[random.nextInt(jokes.length)];
            }

            // Motivation Feature
            else if (input.contains("motivate")) {

                String[] quotes = {

                    "Never give up. Great things take time.",
                    "Success starts with self-confidence.",
                    "Dream big and work hard.",
                    "Believe in yourself!"
                };

                response = quotes[random.nextInt(quotes.length)];
            }

            // User Name Recall
            else if (input.contains("what is my name")) {

                if (!userName.equals("")) {

                    response = "Your name is " + userName;

                } else {

                    response = "I don't know your name yet.";
                }
            }

            // Exit
            else if (input.contains("bye")) {

                response = "Goodbye! Have a nice day!";
                System.out.println("Bot: " + response);

                saveChat(originalInput, response);

                break;
            }

            // Unknown Message
            else {

                response = "Sorry, I don't understand.";
            }

            // Print Bot Response
            System.out.println("Bot: " + response);

            // Save Chat
            saveChat(originalInput, response);
        }

        sc.close();
    }

    // Method to Save Chat History
    public static void saveChat(String userInput, String botResponse) {

        try {

            FileWriter fw = new FileWriter("chat.txt", true);

            fw.write("You: " + userInput + "\n");
            fw.write("Bot: " + botResponse + "\n");
            fw.write("----------------------------------\n");

            fw.close();

        } catch (IOException e) {

            System.out.println("Error saving chat.");
        }
    }
}
```

---

# 📸 Sample Output

```text
=================================
        AI CHATBOT
=================================
Type 'bye' to exit

You: hi
Bot: Hello!

You: my name is Amrutha
Bot: Nice to meet you, Amrutha!

You: what is my name
Bot: Your name is Amrutha

You: time
Bot: Current Time: 10:45:30

You: date
Bot: Today's Date: 2026-06-09

You: add 5 3
Bot: Sum = 8

You: sub 10 4
Bot: Difference = 6

You: mul 2 5
Bot: Product = 10

You: div 20 4
Bot: Division = 5

You: joke
Bot: Why do Java developers wear glasses? Because they don't C#!

You: motivate
Bot: Believe in yourself!

You: bye
Bot: Goodbye! Have a nice day!
```

---

# 🎯 Concepts Used

- Conditional Statements
- Loops
- Methods
- Arrays
- File Handling
- Exception Handling
- String Operations

---

# 🚀 Future Improvements

- GUI Interface using Swing
- Voice Assistant
- Database Integration
- Web Chatbot
- AI API Integration

---

# 📚 Internship Task

This project was developed as part of a Java Programming Internship Task.

---

# 👩‍💻 Author

## SHEK AHMADRAZA

---

# ⭐ GitHub

If you like this project, give it a ⭐ on GitHub.
