### File Permissions & File Operations Challenge

## Task 1: Create Files

- Create empty file devops.txt using touch
- Create notes.txt with some content using cat or echo
- Create script.sh using vim with content: echo "Hello DevOps"
- Verify: ls -l to see permissions

<img width="1201" height="485" alt="t1" src="https://github.com/user-attachments/assets/55f8e7f1-6cde-43cd-892b-4db427f3e06b" />

---

## Task 2: Read Files

- Read notes.txt using cat
- View script.sh in vim read-only mode
- Display first 5 lines of /etc/passwd using head
- Display last 5 lines of /etc/passwd using tail

<img width="728" height="140" alt="T21" src="https://github.com/user-attachments/assets/e870dfbc-a500-476d-aa7b-b9457375bb33" />

<img width="1108" height="1012" alt="T22" src="https://github.com/user-attachments/assets/15323b4c-06b0-499c-9f4f-6c7e975bd135" />

<img width="882" height="362" alt="t23" src="https://github.com/user-attachments/assets/6cca7877-c9f5-4c92-b8b6-ed3d741fc5e0" />

---

## Task 3: Understand Permissions

Format: rwxrwxrwx (owner-group-others)  
r = read (4)  
w = write (2)  
x = execute (1)  

What are current permissions? → 664  
Who can read/write/execute?  
- user: read, write  
- group: read, write  
- others: read  

<img width="986" height="131" alt="t3" src="https://github.com/user-attachments/assets/afc3e97e-a5c1-4544-96f7-1d67e2924d84" />

---

## Task 4: Modify Permissions

- Make script.sh executable → run it with ./script.sh
- Set devops.txt to read-only (remove write for all)
- Set notes.txt to 640 (owner: rw, group: r, others: none)
- Create directory project/ with permissions 755
- Verify: ls -l after each change

<img width="1162" height="832" alt="t4" src="https://github.com/user-attachments/assets/f2ecabab-4d6e-4e09-90c8-c0ac72a9ddc6" />

---

## Task 5: Test Permissions

- Try writing to a read-only file - what happens?
- Try executing a file without execute permission
- Document the error messages

<img width="1065" height="153" alt="t5" src="https://github.com/user-attachments/assets/1a2df31f-ee49-4754-aaa0-b6fedd7dc6ec" />
---

## Files Created

- devops.txt  
- notes.txt  
- script.sh  
- project/  

---

## Permission Changes

- script.sh: 664 → 774  
- devops.txt: 664 → 444  
- notes.txt: 664 → 640  

---

## Commands Used

touch devops.txt  
echo "You are under notes.txt" > notes.txt  
vim script.sh  
ls -l  
cat notes.txt  
vim script.sh  
cat /etc/passwd | head -n 5  
cat /etc/passwd | tail -n 5  
ls -l devops.txt notes.txt script.sh  
sudo chmod 774 script.sh  
./script.sh  
sudo chmod 444 devops.txt  
ls -l  
sudo chmod 640 notes.txt  
sudo chmod 640 notes.txt | ls -l  
mkdir project  
sudo chmod 755 project | ls -l  
echo "Write" >> devops.txt  
./notes.txt  

---

## What I Learned

- How to use touch, cat and echo in different situations  
- How to read specific lines from files using head and tail  
- How to modify permissions (read, write, execute) for files  
- Realized that without proper permissions, you cannot access or execute files  
- Learned how Linux enforces security through permissions  
