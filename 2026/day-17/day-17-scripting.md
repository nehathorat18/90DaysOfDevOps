## Shell Scripting: Loops, Arguments & Error Handling

#### Task 1: For Loop
1. Create `for_loop.sh` that:
   - Loops through a list of 5 fruits and prints each one
<img width="707" height="222" alt="for_loop" src="https://github.com/user-attachments/assets/6d95b390-9d65-4d2c-8edb-bc8af59d7785" />
<img width="695" height="253" alt="forloop" src="https://github.com/user-attachments/assets/628d9ec8-3a28-4b4b-b8c3-2af00537319d" />

2. Create `count.sh` that:
   - Prints numbers 1 to 10 using a for loop
<img width="511" height="216" alt="count1" src="https://github.com/user-attachments/assets/1ba6e3b1-67c6-48af-ac71-bd4c7d4b905b" />
<img width="692" height="361" alt="count" src="https://github.com/user-attachments/assets/2987625b-c78c-43bd-b9e7-9dea5b70e7b1" />

---

#### Task 2: While Loop
1. Create `countdown.sh` that:
   - Takes a number from the user
   - Counts down to 0 using a while loop
   - Prints "Done!" at the end
<img width="526" height="255" alt="count-down" src="https://github.com/user-attachments/assets/64bd9cfe-d268-4d8d-a5c0-d497cd4c2fd0" />
<img width="776" height="541" alt="countdown" src="https://github.com/user-attachments/assets/3b42ac40-f7ce-4256-b1bb-af94553eb3b8" />

---

#### Task 3: Command-Line Arguments
1. Create `greet.sh` that:
   - Accepts a name as `$1`
   - Prints `Hello, <name>!`
   - If no argument is passed, prints "Usage: ./greet.sh <name>"
     
<img width="507" height="318" alt="greet" src="https://github.com/user-attachments/assets/9231ca7b-42f5-425f-8b32-ca6925cea9c3" />
<img width="680" height="197" alt="greett" src="https://github.com/user-attachments/assets/f5ed7ff6-3359-4a22-967a-db2e026ef080" />

2. Create `args_demo.sh` that:
   - Prints total number of arguments (`$#`)
   - Prints all arguments (`$@`)
   - Prints the script name (`$0`)
<img width="488" height="200" alt="argsdemo" src="https://github.com/user-attachments/assets/ba29e6d1-958c-4e1f-9d00-1ea1294164ad" />
<img width="896" height="201" alt="args_demo" src="https://github.com/user-attachments/assets/5c89cb73-212f-42f6-890a-2b8277819282" />

---

#### Task 4: Install Packages via Script
1. Create `install_packages.sh` that:
   - Defines a list of packages: `nginx`, `curl`, `wget`
   - Loops through the list
   - Checks if each package is installed (use `dpkg -s` or `rpm -q`)
   - Installs it if missing, skips if already present
   - Prints status for each package

> Run as root: `sudo -i` or `sudo su`
<img width="710" height="430" alt="installed_pkgg" src="https://github.com/user-attachments/assets/212e5508-a3fe-4ca8-92fc-0a36ab6de841" />
<img width="873" height="351" alt="installed_pkg" src="https://github.com/user-attachments/assets/4086387b-9840-4826-8875-6bee1467cabd" />

---

#### Task 5: Error Handling
1. Create `safe_script.sh` that:
   - Uses `set -e` at the top (exit on error)
   - Tries to create a directory `/tmp/devops-test`
   - Tries to navigate into it
   - Creates a file inside
   - Uses `||` operator to print an error if any step fails

Example:
```bash
mkdir /tmp/devops-test || echo "Directory already exists"
```
<img width="948" height="305" alt="safe_script" src="https://github.com/user-attachments/assets/7736306e-a7ae-46e8-8c29-bbaf7f44d283" />
<img width="1192" height="415" alt="safescript" src="https://github.com/user-attachments/assets/35919e86-5d45-460e-9500-2a3689f71dee" />

2. Modify your `install_packages.sh` to check if the script is being run as root — exit with a message if not.
<img width="830" height="530" alt="modified1" src="https://github.com/user-attachments/assets/2250dc92-eb12-40f8-a7d6-d7651f42eefd" />
<img width="785" height="137" alt="modified" src="https://github.com/user-attachments/assets/20d7575f-212c-41d3-83fc-2ce085298641" />

---

#### What you learned
- Loops (for, while) help automate repetitive tasks
- Command-line arguments ($1, $@, $#) 
- Error handling set -e, || is helps us for writing safe and reliable scripts

---
