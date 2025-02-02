# Hello
Beginning of coding

# Hello World Makefile

This project contains a simple "Hello, World!" program written in C, and this **Makefile** helps automate the compilation, cleaning, and execution of the program.

---

## **How to Use the Makefile**

### **1. Build the Program**
To compile the program, simply run:
```sh
make
```
This will generate an executable file named `Hello`.

### **2. Run the Program**
After building, you can run the program using:
```sh
make run
```
This will execute `./Hello`.

### **3. Clean the Project**
To remove the compiled files and dependencies, run:
```sh
make clean
```
This deletes `Hello` and all `.o` and `.d` files.

---

## **Explanation of Makefile**

### **Variables Used**
- `BASE_DIR` → The root directory of the project.
- `CC` → The compiler (`gcc`).
- `INCLUDE` → Tells the compiler where to find header files (`inc/` directory).
- `SOURCE` → Points to the source code directory (`src/`).
- `EXEC` → Name of the compiled output (`Hello`).
- `CFLAGS` → Compiler flags for debugging (`-g`), dependency tracking (`-MMD -MP`), and including headers.
- `SRCS` → All `.c` files in `src/`.
- `OBJECTS` → All `.o` files (compiled `.c` files).
- `DEPS` → Dependency files (`.d`) generated automatically.

### **Makefile Rules**
- `all`: Builds the `Hello` executable from the `.o` files.
- `$(EXEC)`: Links all object files to create the final executable.
- `$(SOURCE)/%.o: $(SOURCE)/%.c`: Compiles each `.c` file into an `.o` file.
- `clean`: Deletes compiled files (`Hello`, `.o`, and `.d`).
- `run`: Compiles and runs the program.

### **Dependency Handling**
The line:
```makefile
-include $(DEPS)
```
Ensures that `make` tracks changes in header files and only recompiles necessary files, improving efficiency.

---

## **Folder Structure**
```
project-root/
│── inc/           # Header files (.h)
│── src/           # Source files (.c)
│── Makefile       # Build script
│── README.md      # This file
```

---

## **Why Use This Makefile?**
✅ Automates compilation and execution.
✅ Tracks dependencies for efficient rebuilding.
✅ Makes it easy to clean up compiled files.
✅ Works on Linux/macOS.

---

Happy coding! 🚀


