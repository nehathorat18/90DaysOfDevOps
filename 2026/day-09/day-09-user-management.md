## Linux User & Group Management Challenge

### Users & Groups Created
- **Users:** tokyo, berlin, professor, nairobi  
- **Groups:** developers, admins, project-team  

### Group Assignments
- **developers:** tokyo, berlin  
- **admins:** professor  
- **project-team:** tokyo, nairobi  

### Directories Created
- **dev-project** → `drwxrwxr-x (775)`  
- **team-workspace** → `drwxrwxr-x (775)`
  
---

### Commands Used

- sudo useradd -m tokyo
- sudo useradd -m berlin
- sudo useradd -m professor
- cat /etc/passwd

<img width="1767" height="972" alt="1" src="https://github.com/user-attachments/assets/b075c310-b4d4-4067-90ce-f1c44940dbd3" />
<img width="687" height="173" alt="2" src="https://github.com/user-attachments/assets/1293ae55-87de-49a6-b1d7-9000c8818c77" />

- sudo groupadd developers
- sudo groupadd admins
- cat /etc/group

<img width="1492" height="417" alt="3" src="https://github.com/user-attachments/assets/7162095e-a691-4892-9625-7ef2568c87b4" />
<img width="1863" height="1027" alt="4" src="https://github.com/user-attachments/assets/37fe9f68-7ae4-41f0-8392-03aac7750700" />

- sudo usermod -aG developers tokyo
- sudo usermod -aG developers,admins berlin
- sudo usermod -aG admins professor
<img width="1102" height="112" alt="5" src="https://github.com/user-attachments/assets/f2f89435-0ec2-4e46-b0dc-ea7d2409afac" />

- groups tokyo
- groups berlin
- groups professor
<img width="847" height="341" alt="6" src="https://github.com/user-attachments/assets/b6335cdf-aab9-42d9-8d15-14fc3536da69" />

- sudo mkdir dev-project
- sudo chgrp developers dev-project/
- sudo chmod 775 dev-project/
<img width="1046" height="377" alt="7" src="https://github.com/user-attachments/assets/4ccf787b-cba4-4546-a8f7-524513133083" />

- sudo passwd tokyo
- sudo passwd berlin
<img width="1142" height="487" alt="8" src="https://github.com/user-attachments/assets/42a2175c-ec95-4362-acd8-a78210790aee" />

- sudo useradd -m nairobi
- sudo groupadd project-team
- sudo usermod -aG project-team tokyo
- sudo usermod -aG project-team nairobi
- cat /etc/group | grep project-team
<img width="928" height="153" alt="10" src="https://github.com/user-attachments/assets/82dc976a-644e-4693-a3de-e06d51eb3333" />

- sudo mkdir /opt/team-workspace
- cd /opt/team-workspace/
- sudo chmod 775 project-team
- groups nairobi
- sudo passwd nairobi
<img width="1448" height="801" alt="11" src="https://github.com/user-attachments/assets/8db9bc34-7496-4e57-a15b-dda437d71b94" />

- su nairobi
- touch /opt/team-workspace/nairobi.txt
- cd team-workspace
<img width="1321" height="396" alt="12" src="https://github.com/user-attachments/assets/2d74f5ed-fe6c-479f-9e1f-ed746bfe307c" />

---

### What I Learned
- Created and managed users and groups
- Set up directories with proper group access permissions
- Collaborated by creating files within shared directories as group members
