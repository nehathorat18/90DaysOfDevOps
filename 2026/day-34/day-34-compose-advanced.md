# Day 34 – Docker Compose: Real-World Multi-Container Apps

---

### Task 1: Build Your Own App Stack
Create a `docker-compose.yml` for a 3-service stack:
- A **web app** (use Python Flask, Node.js, or any language you know)
- A **database** (Postgres or MySQL)
- A **cache** (Redis)

Write a simple Dockerfile for the web app. The app doesn't need to be complex — even a "Hello World" that connects to the database is enough.

See the [docker-compose.yml](./docker-compose.yml)  and [Dockerfile](./Dockerfile) file.  

---

### Task 2: depends_on & Healthchecks
1. Add `depends_on` to your compose file so the app starts **after** the database
2. Add a **healthcheck** on the database service
3. Use `depends_on` with `condition: service_healthy` so the app waits for the database to be truly ready, not just started

**Test:** Bring everything down and up — does the app wait for the DB?
<img width="1900" height="323" alt="2 1" src="https://github.com/user-attachments/assets/aa733391-c1fc-4a88-9cff-895580a2e1e5" />
<img width="1892" height="327" alt="2 2" src="https://github.com/user-attachments/assets/bc464884-d804-4be1-b26b-087866b0405b" />

---

### Task 3: Restart Policies
1. Add `restart: always` to your database service
2. Manually kill the database container — does it come back?
3. Try `restart: on-failure` — how is it different?
4. Write in your notes: When would you use each restart policy?
<img width="1727" height="231" alt="3 1" src="https://github.com/user-attachments/assets/3af399cd-ad1c-48dc-a96c-7ab29904bcc9" />
<img width="1897" height="352" alt="3 2" src="https://github.com/user-attachments/assets/f0f5d552-87b1-4f58-bf2e-5e79b3651501" />

---

### Task 4: Custom Dockerfiles in Compose
1. Instead of using a pre-built image for your app, use `build:` in your compose file to build from a Dockerfile
2. Make a code change in your app
3. Rebuild and restart with one command
<img width="1858" height="955" alt="4 1" src="https://github.com/user-attachments/assets/ac2b420e-f4ca-4e75-9b15-a75fd307e377" />
<img width="1888" height="457" alt="4 2" src="https://github.com/user-attachments/assets/e0fe2729-1bad-4c9d-9cb0-113c63335c94" />

---

### Task 5: Named Networks & Volumes
1. Define **explicit networks** in your compose file instead of relying on the default
2. Define **named volumes** for database data
3. Add **labels** to your services for better organization
<img width="1850" height="830" alt="5 1" src="https://github.com/user-attachments/assets/44f0e563-93f8-4968-9961-33654bdef4c9" />
<img width="803" height="163" alt="5 2" src="https://github.com/user-attachments/assets/f6843a92-7060-4258-a11f-c7ef2fbfb861" />
<img width="930" height="300" alt="5 3" src="https://github.com/user-attachments/assets/582ff876-e552-413c-b79c-132aa9814a57" />
<img width="1253" height="366" alt="5 4" src="https://github.com/user-attachments/assets/2b9332d5-6d9c-4f8c-8ad9-8804bf66fe87" />
<img width="1323" height="406" alt="5 5" src="https://github.com/user-attachments/assets/1cc08350-a1a7-480b-baa3-895ab885883f" />
<img width="1901" height="153" alt="5 6" src="https://github.com/user-attachments/assets/417e052d-34f9-4ae0-86ed-c145013418d1" />
<img width="1901" height="153" alt="5 7" src="https://github.com/user-attachments/assets/d140f8c7-a7f5-4bbc-a301-445699dae550" />

<img width="1902" height="427" alt="6" src="https://github.com/user-attachments/assets/0c876f4c-bce4-4a22-9b4f-1de3de48c8a1" />

---
