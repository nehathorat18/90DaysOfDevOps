# Day 31 – Dockerfile: Build Your Own Images

### Task 1: Your First Dockerfile
1. Create a folder called `my-first-image`
2. Inside it, create a `Dockerfile` that:
   - Uses `ubuntu` as the base image
   - Installs `curl`
   - Sets a default command to print `"Hello from my custom image!"`
3. Build the image and tag it `my-ubuntu:v1`
4. Run a container from your image

**Verify:** The message prints on `docker run`
<img width="1260" height="972" alt="1" src="https://github.com/user-attachments/assets/a136e7a0-dd25-4f18-826d-26c72179d837" />
<img width="1887" height="972" alt="2" src="https://github.com/user-attachments/assets/721d99e3-f848-442b-878d-daa7805d1a25" />
<img width="1802" height="282" alt="1 3" src="https://github.com/user-attachments/assets/61a3f40f-31ad-4254-8b66-0fb0dfdb73db" />
<img width="1792" height="215" alt="1 4" src="https://github.com/user-attachments/assets/7f217ecb-d2a7-42f1-a7ab-7665b7e79851" />
<img width="1897" height="985" alt="2 0" src="https://github.com/user-attachments/assets/4018e20c-9cd4-4dff-a918-18f83fb5424c" />
<img width="1897" height="985" alt="3 1" src="https://github.com/user-attachments/assets/e611fafa-b920-4eb7-90d1-ddcc21e988f6" />
---

### Task 2: Dockerfile Instructions
Create a new Dockerfile that uses **all** of these instructions:
- `FROM` — base image
- `RUN` — execute commands during build
- `COPY` — copy files from host to image
- `WORKDIR` — set working directory
- `EXPOSE` — document the port
- `CMD` — default command

Build and run it. Understand what each line does.

---

### Task 3: CMD vs ENTRYPOINT
1. Create an image with `CMD ["echo", "hello"]` — run it, then run it with a custom command. What happens?
- Prints whatever is in front of echo eg.Hello 
2. Create an image with `ENTRYPOINT ["echo"]` — run it, then run it with additional arguments. What happens?
- Prints whatever we type at runtime. eg Hello Neha

3. Write in your notes: When would you use CMD vs ENTRYPOINT?
 **CMD**: Use to provide a **default command** that can be easily overridden at runtime.
 **ENTRYPOINT**: Use when the container should always run a **specific executable**, while allowing additional arguments to be passed.

<img width="1252" height="927" alt="3 2" src="https://github.com/user-attachments/assets/aa354486-f837-4fb1-8148-3b014d4879bd" />
<img width="1896" height="732" alt="3 3" src="https://github.com/user-attachments/assets/6f50af20-b5cd-4725-b7f7-09945a373c5e" />

---

### Task 4: Build a Simple Web App Image
1. Create a small static HTML file (`index.html`) with any content
2. Write a Dockerfile that:
   - Uses `nginx:alpine` as base
   - Copies your `index.html` to the Nginx web directory
3. Build and tag it `my-website:v1`
4. Run it with port mapping and access it in your browser
<img width="1027" height="975" alt="4 1" src="https://github.com/user-attachments/assets/8885f3d1-a08d-43ea-83f0-e9d37b3f6712" />

---

### Task 5: .dockerignore
1. Create a `.dockerignore` file in one of your project folders
2. Add entries for: `node_modules`, `.git`, `*.md`, `.env`
3. Build the image — verify that ignored files are not included

---

### Task 6: Build Optimization
1. Build an image, then change one line and rebuild — notice how Docker uses **cache**
2. Reorder your Dockerfile so that frequently changing lines come **last**
3. Write in your notes: Why does layer order matter for build speed?

---
