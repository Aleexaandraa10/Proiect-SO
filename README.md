# **AAShell - Custom Shell in C**  

## 📖 **Description**  
AAShell is an **interactive mini-shell** developed in **C**, providing a customized Linux command execution experience. This shell mimics the functionalities of a standard shell, supporting **system command execution, background process management, pipes (`|`), logical operators (`&&`, `||`), input/output redirection (`<`, `>`), and a command history feature**.  

### 🔹 **Main Components**  
#### **Structures and Global Variables**  
- `BackgroundProcess`: Structure for storing background processes.  
- `background_processes` & `background_count`: Lists background processes and their count.  
- `history` & `history_count`: Stores user command history.  
- `current_pid` & `suspended_pid`: Tracks the current and suspended process IDs.  

#### **Interactive Interface and Messages**  
- `print_prompt`: Displays a custom shell prompt.  
- `welcome_message`: Prints a welcome message for users.  

---

### 🚀 **Key Features**  
#### 📌 **Command History**  
- `add_to_history`: Adds commands to history for future reference.  
- `print_history`: Displays the user’s command history.  

#### 📌 **Command Execution**  
- `execute_command`: Executes simple user commands.  
- `execute_pipe`: Enables execution of **two commands using pipes** (`|`).  
- `execute_redirection`: Handles **input/output redirection** (`<`, `>`).  
- `execute_with_status`: Runs commands and interprets **execution status codes**.  
- `execute_logical_commands`: Executes commands with **logical operators (`&&`, `||`)**.  

#### 📌 **Background Process Management**  
- `print_jobs`: Lists running background processes.  
- `bring_to_foreground`: Brings a background process to the foreground.  
- `kill_background_process`: Terminates a background process.  

#### 📌 **Process Suspension & Resumption**  
- `signal_handler`: Handles `SIGTSTP` (`Ctrl+Z`) to suspend an active process.  
- `handle_fg_command`: Resumes suspended processes and brings them to the foreground.  

---

### ⚙️ **Signal Handling & Execution Control**  
- **Process Suspension (`SIGTSTP`)**: When the user presses `Ctrl+Z`, the current process is suspended and can be resumed later.  
- **Process Resumption (`SIGCONT`)**: The suspended process can be resumed using `fg`.  

---

## 🔧 **Compilation & Execution**  
1. **Compile the project:**  
   ```sh
   gcc shell_so.c -o aashell
   ```  
2. **Run the custom shell:**  
   ```sh
   ./aashell
   ```  
3. **To exit:**  
   ```sh
   exit
   ```
