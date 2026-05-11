#### Task 1: Basic Functions
1. Create `functions.sh` with:
   - A function `greet` that takes a name as argument and prints `Hello, <name>!`
   - A function `add` that takes two numbers and prints their sum
   - Call both functions from the script
<img width="861" height="451" alt="1i" src="https://github.com/user-attachments/assets/c4d66636-e8ae-4ac7-afb4-a9dc0d294b70" />
<img width="702" height="167" alt="1o" src="https://github.com/user-attachments/assets/e25b8247-7e97-427d-bcd3-ff61d759198d" />

---

#### Task 2: Functions with Return Values
1. Create `disk_check.sh` with:
   - A function `check_disk` that checks disk usage of `/` using `df -h`
   - A function `check_memory` that checks free memory using `free -h`
   - A main section that calls both and prints the results
<img width="692" height="576" alt="2i" src="https://github.com/user-attachments/assets/a319d1f9-ba39-4a00-9fa4-6eac9b56a720" />
<img width="693" height="223" alt="2o" src="https://github.com/user-attachments/assets/107d6af3-9de5-4432-b1bb-56bc94b001a7" />

---

#### Task 3: Strict Mode — `set -euo pipefail`
1. Create `strict_demo.sh` with `set -euo pipefail` at the top
2. Try using an **undefined variable** — what happens with `set -u`?
3. Try a command that **fails** — what happens with `set -e`?
4. Try a **piped command** where one part fails — what happens with `set -o pipefail`?

**Document:** What does each flag do?
- `set -e` → Stops the script immediately if any command fails.
- `set -u` → Exits the script when an undefined/unbound variable is used.
- `set -o pipefail` → Makes the entire pipeline fail if any command in the pipeline fails.
<img width="571" height="426" alt="3i" src="https://github.com/user-attachments/assets/3fa1a2e4-8020-41dc-b800-a3a600ef9708" />
<img width="762" height="382" alt="3o" src="https://github.com/user-attachments/assets/ea60e295-b852-494d-824f-3ac57aa5bb39" />

---

#### Task 4: Local Variables
1. Create `local_demo.sh` with:
   - A function that uses `local` keyword for variables
   - Show that `local` variables don't leak outside the function
   - Compare with a function that uses regular variables
<img width="597" height="597" alt="4i" src="https://github.com/user-attachments/assets/5088a9e2-3608-4688-a076-ee5706432891" />
<img width="1021" height="452" alt="4o" src="https://github.com/user-attachments/assets/7935fa9c-fcca-459b-a594-33360754ee54" />

---

#### Task 5: Build a Script — System Info Reporter
Create `system_info.sh` that uses functions for everything:
1. A function to print **hostname and OS info**
2. A function to print **uptime**
3. A function to print **disk usage** (top 5 by size)
4. A function to print **memory usage**
5. A function to print **top 5 CPU-consuming processes**
6. A `main` function that calls all of the above with section headers
7. Use `set -euo pipefail` at the top

<img width="990" height="942" alt="5i" src="https://github.com/user-attachments/assets/ff456c07-1bb0-4b3b-a415-5340b659d4a5" />
<img width="897" height="841" alt="5o" src="https://github.com/user-attachments/assets/5ce1ded3-3966-4d79-98a3-3e302acc6ab2" />

#### What I Learned
- Practiced creating reusable and modular Bash scripts using functions.
- Learned how to build a System Info Reporter by combining multiple Linux commands.
- Improved script reliability using set -euo pipefail.
- Explored local and global functions/variables in shell scripting.


