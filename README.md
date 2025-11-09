# 🐚 Custom Linux Shell Implementation (C++)

### Capstone Project – Linux Operating System  
**Submitted by:** Kunal Kumar  
**Registration No.:** 2241011140  
**Wipro Batch:** 10  
**Date:** 09/11/2025  

---

## 📘 Overview

This project implements a **Custom Shell** in **C++** — a lightweight command-line interpreter that mimics the behavior of standard Unix/Linux shells.  
It supports **command execution, I/O redirection, piping, background processing**, and a simple **command history** mechanism.

---

## 🎯 Objective

To design and implement a simple shell that:
- Executes Linux commands entered by the user.
- Handles process creation and management.
- Supports redirection and piping.
- Implements command history and basic job control.

---

## 🧩 Features

✅ **Command Parsing:**  
Splits input into tokens while handling background execution (`&`).

✅ **Built-in Commands:**  
- `cd <directory>` – Change the current working directory.  
- `mkfifo <filename>` – Create a named pipe.  
- `history` – Display last 10 commands.  
- `!!` – Execute the most recent command.  
- `!N` – Execute the Nth command from history.

✅ **Redirection:**  
- Input (`<`), Output (`>`), and Error (`2>`) redirection supported.

✅ **Piping (`|`):**  
Supports multiple pipes between commands (e.g., `ls -l | grep cpp | wc -l`).

✅ **Background Execution (`&`):**  
Run commands in the background without waiting for completion.

✅ **Job Control (Basic):**  
Reports PID for background processes.

---

## ⚙️ Implementation Details

- Language: **C++17**  
- System Calls Used: `fork()`, `execvp()`, `pipe()`, `dup2()`, `waitpid()`  
- Headers:  
  ```cpp
  #include <iostream>
  #include <string>
  #include <vector>
  #include <unistd.h>
  #include <sys/wait.h>
  #include <fcntl.h>
  #include <sys/stat.h>
