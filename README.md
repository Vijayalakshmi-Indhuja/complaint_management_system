# Complaint Management System

The Complaint Management System is a Python-based project that efficiently manages and resolves complaints within an organization, based on the hierarchy of employment. This system provides a structured approach to complaint handling, ensuring that each complaint is addressed by the appropriate personnel.

## Features

- Register complaints with essential details such as name, roll number or ID, and description.
- Assign complaints automatically to the relevant personnel or department based on their role and position.
- Seamless communication and collaboration among students, CRs, and principals.
- Efficient complaint resolution and forwarding options.
- User-friendly interface and customization options.
- Integration with existing databases and systems.

## How it Works

1. Students can register complaints by providing the necessary information.
2. Complaints are recorded in a centralized database for easy tracking.
3. CRs and principals can access the system to solve, forward, and resolve complaints.
4. Communication and collaboration among stakeholders are facilitated through remarks and solutions.
5. The system ensures timely resolution of complaints and maintains transparency.

## Installation

To run the Complaint Management System locally, follow these steps:

1. Clone the repository.
2. Install the required dependencies.
3. Set up the necessary configuration files.
4. Run the application.

## Overall Structure and Functionality of the code

Let's go through the code and explain its functionality:

1. The code begins by importing the `os` module, which provides a way to interact with the operating system.

2. Two variables `filename` and `filename2` are initialized with the values `'file1'` and `'file2'`, respectively. These variables represent the names of the files used to store the complaints and forwarded queries.

3. The code defines three functions:
   - The `read` function takes a `filename` as an argument and opens the file in read mode. It then prints a heading for the complaints register and reads and prints the contents of the file. Finally, it closes the file.
   - The `append` function takes `data2`, `stu`, and `roll` as arguments. It opens the file in append mode, writes the complaint details to the file, and closes it. It also prints a success message.
   - The `solve` function takes `role` as an argument. It prompts the user to enter a roll number of a complaint they want to resolve and a remark or solution for the query. Depending on the role (2 for CR or 3 for principal), it adds a specific string indicating who resolved the complaint. It finds the line number of the complaint using the `find_query` function, modifies the line in the file with the resolution information, and breaks out of the loop.

4. The `find_query` function takes `find_roll` and `filename` as arguments. It reads the file line by line and checks if a line contains the specified roll number. If a match is found, it returns the line number. Otherwise, it returns `None`.

5. The `forward_query` function takes `forward_roll` and `remark` as arguments. It first checks if the file specified by `filename` exists. If it does, it reads its contents and stores them in `data_search`. It then iterates over the lines, identifies the lines to be forwarded (based on the `forward_roll`), and adds a remark by CR. Finally, it opens `filename2` in append mode, writes the relevant lines to it, and closes the file.

6. The code enters an infinite loop using `while True:`.

7. Inside the loop, it checks if the file specified by `filename` exists. If it does, it proceeds with the following operations:

8. It prompts the user to select a user type (1 for student, 2 for CR, 3 for principal).

9. If the user type is 1 (student), it prompts the user to enter their name, ID number, and complaint. It then calls the `append` function to add the complaint to the file.

10. If the user type is 2 (CR), it calls the `read` function to display the complaints registered so far. It then prompts the CR to choose between solving a complaint, forwarding a complaint, or exiting. Depending on the chosen option, it calls the `solve` or `forward_query` function accordingly.

11. If the user type is 3 (principal), it prompts the principal to choose between checking all queries or checking forwarded queries. Based on the selected option, it calls the `read` function to display the corresponding file's contents. If the principal wants to solve a query, it calls the `solve` function with the user type set to 3. If the principal wants to resolve a forwarded query, it uses similar logic as the `solve` function, but it modifies the `filename2` file instead.

12. After executing the respective actions based on the user type, the code prompts the user to either end or restart the program.

## Contributing

Contributions to the Complaint Management System are welcome! If you find any issues or have ideas for improvement, feel free to open an issue or submit a pull request.

## License

The Complaint Management System is open-source software licensed under the [MIT License](LICENSE).
