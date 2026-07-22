# Day 33 – Docker Compose: Multi-Container Basics
---


### Task 1: Install & Verify
1. Check if Docker Compose is available on your machine
2. Verify the version
<img width="1398" height="750" alt="1" src="https://github.com/user-attachments/assets/1b788381-c839-4097-a26f-c5db790ddabf" />

---

### Task 2: Your First Compose File
1. Create a folder `compose-basics`
2. Write a `docker-compose.yml` that runs a single **Nginx** container with port mapping
3. Start it with `docker compose up`
4. Access it in your browser
5. Stop it with `docker compose down`
<img width="1877" height="418" alt="2 1" src="https://github.com/user-attachments/assets/978828d3-959e-42cc-a18d-be7f5b886b5c" />
<img width="1555" height="742" alt="2" src="https://github.com/user-attachments/assets/1c4cb96f-bc13-4e41-91b7-8a8c0f2ccc7c" />
<img width="1858" height="532" alt="2 2" src="https://github.com/user-attachments/assets/ce73938d-8820-4a0c-81df-d9160c53d793" />
<img width="1671" height="317" alt="2 3" src="https://github.com/user-attachments/assets/815c9348-0df5-43b2-814b-89f9051305e9" />

---

### Task 3: Two-Container Setup
Write a `docker-compose.yml` that runs:
- A **WordPress** container
- A **MySQL** container

They should:
- Be on the same network (Compose does this automatically)
- MySQL should have a named volume for data persistence
- WordPress should connect to MySQL using the service name

Start it, access WordPress in your browser, and set it up.
<img width="1901" height="377" alt="3 1" src="https://github.com/user-attachments/assets/923fa558-28e8-4669-91ef-44facef925ae" />
<img width="1901" height="590" alt="3 2" src="https://github.com/user-attachments/assets/f9d3fafb-7676-4811-85ce-1bc2f7209c33" />
<img width="1907" height="325" alt="3 3" src="https://github.com/user-attachments/assets/e5aec00e-120c-4eaa-b86f-0397445464f0" />
<img width="1878" height="970" alt="3 4" src="https://github.com/user-attachments/assets/3a1d63b8-078e-460f-a7ea-ef2402dc5a3e" />
<img width="1896" height="766" alt="3 5" src="https://github.com/user-attachments/assets/d17f3ad8-6d58-467c-9038-8b82e7d938f4" />
<img width="1873" height="756" alt="3 6" src="https://github.com/user-attachments/assets/3a86fc52-cb9a-42e4-b4ea-42698af9654c" />
<img width="1915" height="898" alt="3 7" src="https://github.com/user-attachments/assets/7ffc0272-a433-40e8-a9fe-382697f9067f" />



**Verify:** Stop and restart with `docker compose down` and `docker compose up` — is your WordPress data still there?
<img width="1906" height="258" alt="3 8" src="https://github.com/user-attachments/assets/a20c6659-32e3-47f1-8837-7e9892899ded" />
<img width="1895" height="538" alt="3 9" src="https://github.com/user-attachments/assets/ef2adacc-515d-43df-98a7-c394473cbdc1" />


---

### Task 4: Compose Commands

1. **Start services in detached mode**
   ```bash
   docker compose up -d
   ```
   Starts all services in the background.

2. **View running services**
   ```bash
   docker compose ps
   ```
   Shows all running containers in the Compose project.

3. **View logs of all services**
   ```bash
   docker compose logs
   ```
   Displays logs from all services.

4. **View logs of a specific service**
   ```bash
   docker compose logs <service-name>
   ```
   Example:
   ```bash
   docker compose logs web
   ```
   Displays logs for only the specified service.

5. **Stop services without removing**
   ```bash
   docker compose stop
   ```
   Stops all running containers but keeps them available to start again.

6. **Remove everything (containers, networks)**
   ```bash
   docker compose down
   ```
   Stops and removes containers and the network created by Docker Compose.

7. **Rebuild images if you make a change**
   ```bash
   docker compose up --build
   ```
   Rebuilds the images and starts the services with the latest changes.
---

### Task 5: Environment Variables
1. Add environment variables directly in your `docker-compose.yml`
2. Create a `.env` file and reference variables from it in your compose file
3. Verify the variables are being picked up
---
