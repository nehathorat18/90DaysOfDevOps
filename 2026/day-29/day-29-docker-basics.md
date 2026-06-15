## Introduction to Docker

### Task 1: What is Docker?
Research and write short notes on:
- What is a container and why do we need them?
  A container is a package that contains everything needed to run an application, including the code, libraries, dependencies and configuration.
  Containers help solve the **"It works on my machine"** problem by providing the same environment everywhere, ensuring the application runs consistently across development, testing and production systems.
    
- Containers vs Virtual Machines — what's the real difference?
  
| Containers | Virtual Machines |
|------------|------------------|
| Lightweight | Heavyweight |
| Share host OS kernel | Run a full guest OS |
| Faster startup | Slower startup |
| Lower resource usage | Higher resource usage |
| Less storage required | More storage required |
| Example: Utho Playground | Example: VirtualBox,EC2 |

- What is the Docker architecture? (daemon, client, images, containers, registry)
- **Daemon (dockerd)** – A background process that manages Docker objects such as containers, images, networks and volumes. It works with containerd to run containers.

- **Client** – The command-line interface (CLI) where you type Docker commands and interact with the Docker daemon.

- **Images** – Read-only templates (blueprints) used to create containers. Images are typically built from a Dockerfile.

- **Registry** – A storage location for Docker images. Registries can be **public** (e.g., Docker Hub) or **private**.

---

### Task 2: Install Docker
1. Install Docker on your machine (or use a cloud instance)
2. Verify the installation
3. Run the `hello-world` container
4. Read the output carefully — it explains what just happened
<img width="1912" height="1021" alt="1" src="https://github.com/user-attachments/assets/df7a2cfa-8eae-4d4c-9ee4-0955e7c774db" />
<img width="982" height="457" alt="1 2" src="https://github.com/user-attachments/assets/3efe513f-f928-42cd-a290-64f9a97951d9" />
<img width="1232" height="252" alt="1 3" src="https://github.com/user-attachments/assets/da3c91b3-1cd2-4a45-adc5-cc27a03b0585" />
<img width="1232" height="752" alt="1 1" src="https://github.com/user-attachments/assets/445f4674-4f33-44e8-9fbf-04b50c7ff582" />

---

### Task 3: Run Real Containers
1. Run an **Nginx** container and access it in your browser
<img width="1842" height="485" alt="3 1" src="https://github.com/user-attachments/assets/25c55f19-944c-47d0-aca6-be4add435895" />

2. Run an **Ubuntu** container in interactive mode — explore it like a mini Linux machine
<img width="1631" height="367" alt="3 2" src="https://github.com/user-attachments/assets/1b531012-111d-48d2-ad54-fd15206a86ae" />

3. List all running containers
4. List all containers (including stopped ones)
5. Stop and remove a container
<img width="1882" height="926" alt="3 3" src="https://github.com/user-attachments/assets/5d5139f3-372d-4df2-b7c9-0ad5b0ccda18" />

---

### Task 4: Explore
1. Run a container in **detached mode** — what's different?
2. Give a container a custom **name**
3. Map a **port** from the container to your host
4. Check **logs** of a running container
5. Run a command **inside** a running container
<img width="1821" height="927" alt="4" src="https://github.com/user-attachments/assets/9464f0c9-1656-43d8-ae28-7aaecf09e31c" />
   
---
