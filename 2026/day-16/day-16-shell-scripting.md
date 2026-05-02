## Shell Scripting Basics 

### Task 1: Your First Script
1. Create a file `hello.sh`
2. Add the shebang line `#!/bin/bash` at the top
3. Print `Hello, DevOps!` using `echo`
4. Make it executable and run it

```bash
chmod +x hello.sh
./hello.sh
```
<img width="708" height="177" alt="11" src="https://github.com/user-attachments/assets/2aa72de9-ae0a-4025-9fc8-2f024a0b16e9" />
<img width="805" height="280" alt="1" src="https://github.com/user-attachments/assets/4efc5928-be8e-4569-a528-961f9091b2c3" />

**Document:** What happens if you remove the shebang line?
--> Even when we remove the shebang line, the script still executes. It is not mandatory, but it tells the system that the script is intended to run using Bash.

---

### Task 2: Variables
1. Create `variables.sh` with:
   - A variable for your `NAME`
   - A variable for your `ROLE` (e.g., "DevOps Engineer")
   - Print: `Hello, I am <NAME> and I am a <ROLE>`
<img width="562" height="387" alt="21" src="https://github.com/user-attachments/assets/f2b82310-9d25-403f-aefd-6fc2eb42e132" />
<img width="685" height="203" alt="2" src="https://github.com/user-attachments/assets/42150adf-9556-46dc-b779-d065f0037cd1" />

2. Try using single quotes vs double quotes — what's the difference?

- If you use single quotes, it will not fetch the variable value.  
- If you use double quotes, it will fetch the variable and print its value where it is called.

---

### Task 3: User Input with read

1. Create `greet.sh` that:
   - Asks the user for their name using `read`
   - Asks for their favourite tool
   - Prints: `Hello <name>, your favourite tool is <tool>`
<img width="978" height="298" alt="31" src="https://github.com/user-attachments/assets/5cab589e-7d69-40e6-9c0a-de8ddd52d60e" />
<img width="695" height="202" alt="3" src="https://github.com/user-attachments/assets/20e55ba0-0d9f-4ccf-bfd6-6b8db987ffd2" />

---

### Task 4: If-Else Conditions

1. Create `check_number.sh` that:
   - Takes a number using `read`
   - Prints whether it is **positive**, **negative**, or **zero**
<img width="690" height="296" alt="41" src="https://github.com/user-attachments/assets/9a03031e-74e7-4050-9a65-6c8c05d68694" />
<img width="857" height="410" alt="4" src="https://github.com/user-attachments/assets/52a138f8-0123-4d1e-82e0-631ba59cf3cd" />

2. Create `file_check.sh` that:
   - Asks for a filename
   - Checks if the file **exists** using `-f`
   - Prints appropriate message
<img width="897" height="337" alt="51" src="https://github.com/user-attachments/assets/dac2a3da-99d0-4512-85f0-e51165969a4f" />
<img width="908" height="347" alt="5" src="https://github.com/user-attachments/assets/fa11f130-0202-4cfc-8968-c08f022b74e5" />

---

### Task 5: Combine It All

Create `server_check.sh` that:
1. Stores a service name in a variable (e.g., `nginx`, `sshd`)
2. Asks the user: "Do you want to check the status? (y/n)"
3. If `y` — runs `systemctl status <service>` and prints whether it's **active** or **not**
4. If `n` — prints "Skipped."
<img width="856" height="417" alt="61" src="https://github.com/user-attachments/assets/314a21ae-47ca-47e4-a804-53bc805c38be" />
<img width="781" height="298" alt="6" src="https://github.com/user-attachments/assets/50acbad6-0864-49e2-b14f-3ddd0a4605a5" />

---

### What You Learned

- How to write a basic shell script using if-else conditions to control program flow  
- `/dev/null` acts like a black hole — it discards any output redirected to it  
- How to take user input using `read` and store it in variables  
- How to use variables inside conditions with `$` to access their values  
- How to check a service status using `systemctl is-active`  

---
