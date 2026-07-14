# Day 30 – Docker Images & Container Lifecycle


### Task 1: Docker Images
1. Pull the `nginx`, `ubuntu`, and `alpine` images from Docker Hub
2. List all images on your machine — note the sizes
3. Compare `ubuntu` vs `alpine` — why is one much smaller?
- Alpine is much smaller because it is a minimal Linux distribution.  It includes only essential packages and is designed for lightweight containers, while Ubuntu includes many additional tools and libraries.
4. Inspect an image — what information can you see?
- Image ID
- Repository and tag
- Created date
- OS and architecture
- Environment variables
- Entrypoint/Command
- Image layers
- Size
5. Remove an image you no longer need
<img width="1326" height="812" alt="1" src="https://github.com/user-attachments/assets/3bd3d1bb-071a-47cf-92c8-cc134955c3d2" />
<img width="1917" height="191" alt="1 4" src="https://github.com/user-attachments/assets/90eb3571-0ed2-4d97-9e39-9e2431b6cae1" />

---

### Task 2: Image Layers
1. Run `docker image history nginx` — what do you see?
- It shows the image's build history, including all layers, the commands used to create them, and the size of each layer.
<img width="1765" height="525" alt="2" src="https://github.com/user-attachments/assets/3a4223c2-93d0-489d-bfbd-4aa50f689092" />

2. Each line is a **layer**. Note how some layers show sizes and some show 0B
- Layers with sizes contain actual file changes.
- `0B` layers are metadata changes (e.g., `CMD`, `ENV`, `EXPOSE`) and don't add files.
3. Write in your notes: What are layers and why does Docker use them?
**Layers** are read-only building blocks of a Docker image. Docker uses them to save storage space, speed up image builds, and reuse unchanged layers.
---

### Task 3: Container Lifecycle
Practice the full lifecycle on one container:
1. **Create** a container (without starting it)
2. **Start** the container
3. **Pause** it and check status
4. **Unpause** it
5. **Stop** it
6. **Restart** it
7. **Kill** it
8. **Remove** it

Check `docker ps -a` after each step — observe the state changes.
<img width="1212" height="922" alt="3" src="https://github.com/user-attachments/assets/744ec4d4-5a0e-417b-97e1-9de21f56f98e" />
<img width="1407" height="590" alt="3 1" src="https://github.com/user-attachments/assets/99f798c7-b585-45fd-a4b8-a4200e45901c" />

---

### Task 4: Working with Running Containers
1. Run an Nginx container in detached mode
2. View its **logs**
3. View **real-time logs** (follow mode)
4. **Exec** into the container and look around the filesystem
5. Run a single command inside the container without entering it
6. **Inspect** the container — find its IP address, port mappings, and mounts
<img width="1662" height="980" alt="4" src="https://github.com/user-attachments/assets/d68aac84-6aa5-421f-8e8d-e2e1ad6b82ed" />
<img width="1811" height="897" alt="5" src="https://github.com/user-attachments/assets/52913b41-53af-4abe-9c39-ef8823ae057c" />
<img width="1627" height="977" alt="5 1" src="https://github.com/user-attachments/assets/79a9199f-bc4c-42ac-8da6-9b517d1e4bf2" />
<img width="900" height="317" alt="5 2" src="https://github.com/user-attachments/assets/0ad785ad-599f-4ff1-93e6-322e2ff660b3" />

---

### Task 5: Cleanup
1. Stop all running containers in one command
2. Remove all stopped containers in one command
3. Remove unused images
4. Check how much disk space Docker is using
<img width="1262" height="870" alt="6" src="https://github.com/user-attachments/assets/9659a5de-7f27-4d7b-b77d-3adbff0c444b" />
<img width="1402" height="842" alt="6 1" src="https://github.com/user-attachments/assets/67553ca5-3d94-4d0a-b506-cc271fa119c0" />

---
