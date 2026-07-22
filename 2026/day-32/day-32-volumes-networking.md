# Day 32 – Docker Volumes & Networking
---


### Task 1: The Problem
1. Run a Postgres or MySQL container
<img width="1497" height="987" alt="1 1" src="https://github.com/user-attachments/assets/b44cd7c4-a260-4716-b21a-ffffc728d40f" />
<img width="1265" height="202" alt="1 2" src="https://github.com/user-attachments/assets/e3d276fb-1b3f-4e46-8f4d-3a4e140b0dc6" />

2. Create some data inside it (a table, a few rows — anything)
<img width="1567" height="992" alt="1 3" src="https://github.com/user-attachments/assets/92aa48b1-7c4a-4e39-a4a9-2647a762a642" />


3. Stop and remove the container
4. Run a new one — is your data still there?
<img width="1627" height="532" alt="1 4" src="https://github.com/user-attachments/assets/0d0d9448-7f2c-4371-8440-c796dc56e6b5" />

Write what happened and why.
- Containers are ephemeral by design, meaning any data stored inside the container is lost when the container is stopped and removed unless persistent storage is used.
---

### Task 2: Named Volumes
1. Create a named volume
<img width="1435" height="550" alt="2 1" src="https://github.com/user-attachments/assets/820c29ab-85f5-4ee5-98a6-b03d15ac73f9" />


2. Run the same database container, but this time **attach the volume** to it
<img width="1816" height="795" alt="2 2" src="https://github.com/user-attachments/assets/98a98ccc-2764-4e20-a5c3-2b9c58d78548" />

3. Add some data, stop and remove the container
<img width="1887" height="965" alt="2 3" src="https://github.com/user-attachments/assets/20488eb0-b64f-4905-a762-9e895577637f" />

4. Run a brand new container with the **same volume**
5. Is the data still there?
<img width="1816" height="887" alt="2 4" src="https://github.com/user-attachments/assets/3b56ee85-0195-49c8-9945-9ae33d9434dc" />

**Verify:** `docker volume ls`, `docker volume inspect`

<img width="997" height="552" alt="2 11" src="https://github.com/user-attachments/assets/8d7c5f70-5fa1-493b-b140-1a5566b6dfc1" />

---

### Task 3: Bind Mounts
1. Create a folder on your host machine with an `index.html` file
2. Run an Nginx container and **bind mount** your folder to the Nginx web directory
3. Access the page in your browser
4. Edit the `index.html` on your host — refresh the browser
<img width="1377" height="917" alt="3" src="https://github.com/user-attachments/assets/9ab78b62-68ad-462e-bf69-eb87bc8f2094" />
<img width="732" height="412" alt="3 1" src="https://github.com/user-attachments/assets/c7ad8ab7-7f7d-42af-b275-84533225558c" />

Write in your notes: What is the difference between a named volume and a bind mount?
| Named Volume | Bind Mount |
|--------------|------------|
| Docker manages the storage. | Uses a folder from your computer. |
| Best for saving application data. | Best for sharing project files. |
| **Example:** Database data (`postgres_data`). | **Example:** Project folder (`./app:/app`). |

---

### Task 4: Docker Networking Basics
1. List all Docker networks on your machine
2. Inspect the default `bridge` network
3. Run two containers on the default bridge — can they ping each other by **name**?
4. Run two containers on the default bridge — can they ping each other by **IP**?

---

### Task 5: Custom Networks
1. Create a custom bridge network called `my-app-net`
2. Run two containers on `my-app-net`
3. Can they ping each other by **name** now?
4. Write in your notes: Why does custom networking allow name-based communication but the default bridge doesn't?

---

### Task 6: Put It Together
1. Create a custom network
2. Run a **database container** (MySQL/Postgres) on that network with a volume for data
3. Run an **app container** (use any image) on the same network
4. Verify the app container can reach the database by container name

---
