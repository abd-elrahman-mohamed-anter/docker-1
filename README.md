# 🐳 Docker Nginx and Spring PetClinic Guide

# This guide demonstrates how to use Docker to run and manage an Nginx web server,
# a Spring PetClinic application, and how to pull common base images.

# ---------------------------------------------------
# 1️⃣ Nginx Web Server
# ---------------------------------------------------

# Step 1: Login and Run Nginx
docker login
docker pull nginx
docker run -d -p 9000:80 nginx
# (screenshot: 1.png)

# Step 2: View Nginx in the Browser
# Open http://localhost:9000
# (screenshot: 2.png)

# Step 3: Run Nginx on a Different Port
docker run -d -p 9001:80 nginx
docker ps
# (screenshot: 3.png)

# Step 4: Access the Second Nginx Instance
# Open http://localhost:9001
# (screenshot: 4.png)

# ---------------------------------------------------
# 2️⃣ Modifying the Nginx Content
# ---------------------------------------------------

# Step 5: Enter the Container
docker exec -it <container_id> /bin/sh
# (screenshot: 5.png)

# Step 6: Change the Default Page
echo "hiiii it is docker here" > /usr/share/nginx/html/index.html
# (screenshot: 6.png)

# Step 7: View the Changes
# Refresh http://localhost:9001
# (screenshot: 7.png)

# ---------------------------------------------------
# 3️⃣ Spring PetClinic Application
# ---------------------------------------------------

# Step 8: Clone and Build the Project
git clone https://github.com/spring-projects/spring-petclinic.git
cd spring-petclinic
docker build -t spring-petclinic .
# (screenshot: 8 (1).jpg)

# Step 9: Run the Application Container
docker run -d -p 8080:8080 spring-petclinic
# (screenshot: 9 (1).jpg)

# Step 10: Access the Application
# Open http://localhost:8080
# (screenshot: 10 (1).png)

# ---------------------------------------------------
# 4️⃣ Pulling Different Docker Images
# ---------------------------------------------------

# Step 11: Pull Alpine
docker pull alpine
# ✅ Pulled successfully

# Step 12: Pull PHP
docker pull php
# ✅ Pulled successfully

# Step 13: Pull Ubuntu
docker pull ubuntu
# ✅ Pulled successfully

# Step 14: Pull Node.js
# Note: 'docker pull nodejs' and 'docker pull nodjs' fail.
# Correct name is 'node'.
docker pull node
# ✅ Pulled successfully
# (screenshot: 11.png)

# ---------------------------------------------------
# ✅ Useful Notes
# ---------------------------------------------------
# List all containers (running + stopped)
docker ps -a

# Stop a container
docker stop <container_id>

# Remove a container
docker rm <container_id>

# Remove an image
docker rmi <image_name>
