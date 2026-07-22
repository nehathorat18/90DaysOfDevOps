# Day 35 – Multi-Stage Builds & Docker Hub

---

### Task 1: The Problem with Large Images
1. Write a simple Go, Java, or Node.js app (even a "Hello World" is fine)
2. Create a Dockerfile that builds and runs it in a **single stage**
3. Build the image and check its **size**

Note down the size — you'll compare it later.
<img width="1885" height="728" alt="1 1" src="https://github.com/user-attachments/assets/4a232e97-817b-4125-a8fc-a6c6b1bae7ef" />


---

### Task 2: Multi-Stage Build
1. Rewrite the Dockerfile using **multi-stage build**:
   - Stage 1: Build the app (install dependencies, compile)
   - Stage 2: Copy only the built artifact into a minimal base image (`alpine`, `distroless`, or `scratch`)
2. Build the image and check its size again
3. Compare the two sizes
<img width="1037" height="873" alt="1 2" src="https://github.com/user-attachments/assets/74b19aee-0cd2-4531-af0c-819ce502c25e" />

Write in your notes: Why is the multi-stage image so much smaller?
- A multi-stage image is smaller because it only includes the files needed to run the application. It leaves out build tools, source code and other unnecessary files, making the image smaller, faster and more secure.
---

### Task 3: Push to Docker Hub
1. Create a free account on [Docker Hub](https://hub.docker.com) (if you don't have one)
2. Log in from your terminal
3. Tag your image properly: `yourusername/image-name:tag`
4. Push it to Docker Hub
5. Pull it on a different machine (or after removing locally) to verify
<img width="1898" height="771" alt="2 1" src="https://github.com/user-attachments/assets/26ecaff2-811f-49e5-8888-16a9b9228bfc" />
<img width="1867" height="735" alt="2 2" src="https://github.com/user-attachments/assets/a81382e4-9897-4232-9190-b7effb9f6f1f" />
<img width="1472" height="638" alt="2 3" src="https://github.com/user-attachments/assets/3c199f80-428f-4ae9-99f1-05a16645d4ba" />
<img width="1890" height="562" alt="2 4" src="https://github.com/user-attachments/assets/52d06c23-5ed3-4840-aff6-32e80b196797" />


---

### Task 4: Docker Hub Repository
1. Go to Docker Hub and check your pushed image
2. Add a **description** to the repository
3. Explore the **tags** tab — understand how versioning works
4. Pull a specific tag vs `latest` — what happens?
<img width="1867" height="787" alt="2 5" src="https://github.com/user-attachments/assets/51c43381-e8a1-44ff-9720-36ac6fb699d9" />
<img width="1896" height="890" alt="4" src="https://github.com/user-attachments/assets/46c5517f-d9bb-4217-b0a5-b03347f4d5f7" />

---

