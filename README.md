# Simple SQL Database in C 

This project is a lightweight, from-scratch implementation of a relational database similar to SQLite, written entirely in **C**. It features a command-line interface (REPL) for executing SQL queries, persists data to a file, and uses a **B-Tree** data structure for efficient data organization and retrieval.

This project is inspired by the excellent "Let's Build a Simple Database" tutorial by Connor Stack.

---

## Features

- **SQL Command-Line Interface**: An interactive REPL (`db >`) to execute commands.
- **Persistent Storage**: All data is saved to a binary file and loaded automatically on startup.
- **Efficient B-Tree Data Structure**: Uses a B-Tree to store data, allowing for fast lookups and keeping data sorted by the primary key.
- **Basic SQL Support**: Implements `INSERT` and `SELECT` statements for a single, predefined table.
- **Meta-Commands**: Includes special commands like `.exit` to safely close the database and save data.

---

## Tech Stack

- **Language**: C
- **Compiler**: GCC (or any standard C compiler like Clang)
- **Build System**: Make



---

## Getting Started

Follow these steps to clone, build, and run the project on your local machine.

### **Prerequisites**

You'll need `git`, `make`, and a C compiler like `gcc` installed.

### **Installation & Build**

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/shivjeet1/sql-C-db.git
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd sql-C-db
    ```
3.  **Compile the source code:**
    ```bash
    gcc db.c -o db 
    ```
    This will create an executable file named `db` in the project root.

---

## Usage

You must provide a database filename when running the program. The database will be created if it doesn't exist.

1.  **Run the application:**
    ```bash
    ./db test.db
    ```

2.  **You are now in the SQL REPL.** You can start inserting data. The table schema is fixed as `(id INTEGER, username VARCHAR(32), email VARCHAR(255))`.
    ```sql
    db > insert 1 userone person1@example.com
    Executed.
    db > insert 2 usertwo person2@example.com
    Executed.
    ```

3.  **Retrieve all data** from the table using the `select` command:
    ```sql
    db > select
    (1, userone, person1@example.com)
    (2, usertwo, person2@example.com)
    Executed.
    ```

4.  **Data is persistent.** You can exit the database and your data will be saved.
    ```sql
    db > .exit
    ```
    If you run `./db test.db` again and type `select`, your data will still be there.

---

## Credits

- This project is a personal implementation based on the fantastic tutorial **[Let's Build a Simple Database](https://cstack.github.io/db_tutorial/)** by **Connor Stack**.
- The code in this repository was written, implemented and tested by **[shivjeet1](https://github.com/shivjeet1)**.

---

## License

- This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Resources

- [Let's Build a Simple Database](https://cstack.github.io/db_tutorial)


