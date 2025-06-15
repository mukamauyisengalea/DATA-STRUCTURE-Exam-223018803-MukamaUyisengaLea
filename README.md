
 **FINAL EXAM OF OOP**
 
 **QUIZ-ENGINE PROJECT**

This C++ program is a simple console quiz program developed based on the principles of object-oriented programming (OOP). It supports two types of users—GuestUser and PremiumUser—with different permissions when responding to the quiz. The program also illustrates the usage of dynamic memory allocation, pointer handling, inheritance, and abstraction.

**1.	Including Required Libraries**

#include <iostream>
#include <cstring>
The program starts by including two header files. iostream is used for input and output operations such as cin and cout. cstring provides functions for string manipulation (e.g., strncpy) for copying character arrays.
using namespace std;
This line tells the compiler to use the standard namespace, so we don’t have to prefix std:: every time we use cout, cin, or other standard objects.

**2.	Defining the Question Structure**

struct Question {
    char prompt[100];
    char choices[4][40];
    int correctIdx;
};
Here, a structure Question is declared to represent a quiz question. It contains:
•	prompt: a string to hold the question text.
•	choices: a 2D array to store four possible answer options.
•	correctIdx: an integer that stores the index of the correct answer (from 0 to 3).

**3.	Declaring the Abstract Base Class: QuizUser**

class QuizUser {
public:
    virtual int attemptQuiz(Question* questions, int count) = 0;
    virtual ~QuizUser() {}
};
This is an abstract base class called QuizUser containing:
•	A pure virtual function attemptQuiz, which must be overridden by any derived class. It takes a pointer to an array of questions and a count of how many there are.
•	A virtual destructor, ensuring proper cleanup of resources if a derived class object is deleted via a base class pointer.

**4.GuestUser Class Definition**

class GuestUser : public QuizUser {

This class publicly inherits from QuizUser, meaning it must implement attemptQuiz
         
    int attemptQuiz(Question* questions, int count) override {
The attemptQuiz method allows a Guest user to answer up to 3 questions
int limit = (count < 3) ? count : 3;.
If there are fewer than 3 questions, the limit is adjusted accordingly.
for (int i = 0; i < limit; i++) {
    ...
    if (answer - 1 == q->correctIdx) score++;
}
The loop displays each question, allows the user to input an answer, and compares it to the correct index. The score is increased if the answer is correct.

**5.	PremiumUser Class Definition**

class PremiumUser : public QuizUser {
A Premium user can attempt all available questions. The attemptQuiz method here is similar to GuestUser but uses the full count rather than a limit of 3.

**6.	Adding Questions Dynamically**

void addQuestion(Question*& questions, int& size, Question newQ)
This function adds a new Question to a dynamically allocated array:
•	It creates a new array one element larger.
•	Copies all old questions into the new array.
•	Adds the new question at the end.
•	Deletes the old array and updates the pointer and size.

**7.	Removing a Question**

void removeQuestion(Question*& questions, int& size, int index)
This function removes a question at a specified index. It:
Validates the index.
Creates a new array one element smaller.
Copies all questions except the one to remove.
Deletes the old array and updates the size.

**8.	Creating Questions Manually**

Question createQuestion(...)
This helper function simplifies question creation. It:
•	Copies the prompt and choices using strncpy for safety.
•	Sets the correct answer index.
Returns a Question object.

**9. Main Function: Execution Starts Here**

int main()
The main function orchestrates the entire flow:
•	Initializes a dynamic questions array with 0 size.
•	Adds four sample questions using addQuestion and createQuestion.
QuizUser** users = new QuizUser*[userCount];
An array of QuizUser pointers is created. The first is a GuestUser, and the second a PremiumUser
for (int i = 0; i < userCount; i++) {
    users[i]->attemptQuiz(questions, qSize);
}.
Each user takes the quiz according to their type. The virtual function ensures the correct version of attemptQuiz is called, thanks to polymorphism.

**10. Cleaning Up Memory.**

for (int i = 0; i < userCount; i++) {
    delete users[i];
}
delete[] users;
delete[] questions;
Memory allocated using new must be manually freed using delete. This prevents memory leaks, which is especially important in larger programs.

**Conclusion**

This quiz program is a good example of proper usage of object-oriented programming principles, especially abstraction, inheritance, and polymorphism. The program also deals with dynamic memory using explicit allocation and deallocation. The Guest/Premium user type difference introduces real-world constraints and shows how the behavior of objects may vary with respect to class hierarchy. Overall, it's a well-structured and neat C++ implementation of a minimalist but flexible quiz system.






**WORK2 ESSAY OF C++**

**1.INTRODUCTION**

C++ is a general-purpose programming language that is widely used for system and application software development. It was designed to provide high-level programming capabilities while still allowing low-level programming.
When you write a C++ program, it typically consists of several key components:
1.	Header Files: These files contain declarations of functions, classes, and other resources. They are included at the beginning of the program using preprocessor directives such as #include. For example, #include <iostream> includes the standard input-output stream library.
2.	Namespaces: These are used to organize code into logical groups and to prevent name collisions. The standard library uses the namespace std. You can include this in your program using using namespace std;.
3.	Main Function: The main function is the entry point of the program. Every C++ program must have a main function, which is where the execution starts.
4.	Statements and Expressions: Inside the main function (or other functions), you write the actual code that performs the tasks you want your program to accomplish. This includes variables, control structures (like loops and conditionals), and function calls.

**2.COMPONENT OF C++ PROGRAM**

#include<iostream>
#include<iostream>: This line is a preprocessor directive that includes the standard input-output stream library. It is necessary to use the standard input and output functions like cout and cin.
using namespace std;
using namespace std;: This line tells the compiler to use the standard namespace. The standard namespace contains all the definitions of the standard library. Without this line, you would need to prefix standard library objects with std::, like std::cout.
main(){
main(){: This is the main function of the program. Every C++ program must have a main function, which is the starting point of execution.
    return 0;
}
return 0;: This statement is used to return a value from the main function. In this case, 0 typically indicates that the program has executed successfully. The closing curly brace } marks the end of the main function.

**3.IMPORTANCE **

#include <iostream> :is a header file library that lets us work with input and output objects, such as cout . Header files add functionality to C++ programs.

using namespace std: means that we can use names for objects and variables from the standard library.
int main():This is called a function. Any code inside its curly brackets {} will be executed.
cout : is an object used together with the insertion operator (<<) to output/print text or content of variable.
return 0: ends the main function.

**4.CONCLUSION**

Each of these components plays an important role in ensuring that your program is correctly set up to perform input and output operations, adhere to standard library conventions, and define the starting point and successful completion of the program.

OTHER EXAPLAINATION https://github.com/mukamauyisengalea/223018803-MUKAMAUYISENGALEA-OBJECT-ORIENTED-PROGRAM.git




**WORK1(EXAM OF DBMS)**

**TOPIC: Project 48: Library Book Reservation and Borrowing System**

Topic 1: Define data structures and discuss their importance in library book reservation and borrowing system.

Topic 2: Implement Binary Search Tree (BST) and Heap to manage data in the library book reservation and borrowing system.

Topic 3: Implement Circular Queue for library book reservation and borrowing system processing.

Topic 4: Create Queue to manage a fixed number of orders in the library book reservation and borrowing system.

Topic 5: Use Queue to track data dynamically in library book reservation and borrowing system.

Topic 6: Implement a tree to represent hierarchical data in the library book reservation and borrowing system.

Topic 7: Use Heap Sort to sort the library book reservation and borrowing system data based on priority.


**1. Introduction**

In today’s rapidly evolving digital landscape, libraries face numerous challenges in efficiently managing book reservations and borrowing systems. A common problem is the lack of streamlined processes to handle large volumes of data, leading to delays and inefficiencies in serving patrons. These inefficiencies can hinder the overall library experience, leaving users dissatisfied and reducing the utility of library resources. To address these issues, leveraging advanced data structures and algorithms becomes essential.

Data structures are fundamental tools in computer science that organize and store data effectively. They provide a systematic way to manage, retrieve, and process information, ensuring that systems remain responsive and scalable. By integrating these structures into library management systems, libraries can enhance their operational efficiency, prioritize tasks, and improve user experiences. This essay explores various data structures and their applications in creating a robust library book reservation and borrowing system.

**2. Features**
   
**Define Data Structures**: Data structures provide the backbone for efficient data organization. They enable libraries to manage data systematically, ensuring quick access and seamless updates. For library systems, structures like trees, queues, and heaps facilitate quick access, modification, and management of information. Properly defining these structures ensures scalability and reliability, catering to the dynamic needs of modern libraries.

**Implement Binary Search Tree (BST)**: A Binary Search Tree is an efficient way to store and retrieve book data based on unique identifiers such as ISBN numbers. BSTs allow for fast searches, insertions, and deletions, making them ideal for large-scale library databases. For instance, a BST can enable users to find specific books quickly by performing logarithmic time searches.

**Implement Circular Queue**: Circular queues optimize space by reusing memory. This feature is crucial for managing book reservations, ensuring that the system operates continuously without requiring frequent resets. Circular queues also enhance performance by minimizing wasted storage, which is particularly useful in high-traffic library environments.

**Create a Queue for Fixed Orders**: A queue with a fixed size is useful for managing a set number of book requests or processing limited-time offers. This approach ensures orderly management of reservations within predefined constraints. For example, fixed queues can handle special event bookings or pre-order lists efficiently.
Use Queue to Track Reservations Dynamically: Dynamic queues provide flexibility in handling variable demand. They can dynamically expand or contract based on the number of reservations, preventing system overload and ensuring seamless service. Dynamic tracking allows libraries to accommodate unexpected spikes in demand, such as during peak academic seasons.

**Implement Tree for Hierarchical Data**: Hierarchical data, such as categorizing books by genres, authors, or publication years, is best represented using tree structures. This organization simplifies browsing and enhances the user’s ability to find specific resources. For example, a hierarchical tree can allow users to navigate from general genres to specific titles efficiently.

**Heap Sort for Priority**: Heap sort is an efficient algorithm for sorting data based on priority. For example, the system can prioritize reservations based on user type (e.g., faculty over students) or due dates, ensuring that high-priority requests are addressed promptly. This ensures equitable resource allocation and improves user satisfaction by reducing wait times for critical requests.

**Additional Features**

**	Hash Tables for Quick Access**: Hash tables can be implemented to store and retrieve book information in constant time. They are particularly useful for managing large datasets.

**	Linked Lists for Reservation History**: Linked lists can maintain user reservation histories, allowing easy traversal and updates.

**	Graph Structures for Networked Libraries**: For systems managing multiple libraries, graphs can represent connections and dependencies, enabling seamless inter-library resource sharing.

**3. Importance**

**Library Management Systems (LMS)**

An LMS powered by advanced data structures transforms the way libraries operate. It reduces manual effort, minimizes errors, and speeds up operations such as book searches, reservations, and borrowing processes. Moreover, a well-designed LMS improves user satisfaction by providing timely and accurate information. Key benefits include:

**	Improved Efficiency**: Faster data retrieval and processing.

**	Enhanced User Experience**: Easier access to resources and reduced wait times.

**	Scalability**: Ability to handle growing user demands without compromising performance.

**	Data Insights**: Advanced structures can provide analytical insights, helping libraries optimize resource allocation and planning.

**4. Conclusion**
   
Incorporating data structures into library book reservation and borrowing systems is not just a technical necessity but a strategic advantage. From efficient data handling to prioritization and dynamic management, these features ensure that libraries can meet the demands of modern users. By embracing such innovations, libraries can continue to serve as pillars of knowledge and learning in the digital age. Additionally, the use of advanced algorithms and data organization techniques ensures that library systems remain resilient, adaptable, and user-focused. With these enhancements, libraries can achieve their mission of providing seamless access to information and fostering a culture of learning.

