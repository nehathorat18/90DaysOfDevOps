# Linux Fundamentals: Read and Write Text Files

## Command History
1. touch notes.txt  
2. ls  
3. echo "Line 1" > notes.txt  
4. cat notes.txt  
5. echo "Line 2" >> notes.txt  
6. cat notes.txt  
7. echo "Line 3" | tee -a notes.txt  
8. cat notes.txt  
9. echo "Line 4" >> notes.txt  
10. echo "Line 5" >> notes.txt  
11. cat notes.txt  
12. head -n 2 notes.txt  
13. tail -n 2 notes.txt  
14. history  

---

## Summary

- `>` → Overwrites file  
- `>>` → Appends to file  
- `tee -a` → Appends while also printing output  
- `cat` → Displays file content  
- `head` → Shows first few lines  
- `tail` → Shows last few lines  

<img width="1806" height="801" alt="Picture1" src="https://github.com/user-attachments/assets/052d8531-a33a-4001-a9d2-da32c3a8d991" />
