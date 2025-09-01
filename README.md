# Docker Nginx and Spring PetClinic Guide 🐳

This guide demonstrates how to use Docker to run and manage an **Nginx web server**, a **Spring PetClinic** application, and how to pull common base images.

---

## 1. Nginx Web Server

### Step 1: Login and Run Nginx
Login to Docker, pull the latest Nginx image, and run a container mapping host port **9000** to container port **80**:

docker login  
docker pull nginx  
docker run -d -p 9000:80 nginx  

![Nginx Run](1.png)

---

### Step 2: View Nginx in the Browser
Navigate to **http://localhost:9000** in your browser to see the default Nginx welcome page.

![Nginx Browser](2.png)

---

### Step 3: Run Nginx on a Different Port
Run another instance of Nginx on port **9001**:

docker run -d -p 9001:80 nginx  

Check running containers:

docker ps  

![Docker ps](3.png)

---

### Step 4: Access the Second Nginx Instance
Go to **http://localhost:9001**.  
You’ll see the Nginx welcome page again.

![Second Nginx](4.png)

---

## 2. Modifying the Nginx Content

### Step 5: Enter the Container
Access the container shell:

docker exec -it <container_id> /bin/sh  

![Exec into Container](5.png)

---

### Step 6: Change the Default Page
Replace the default `index.html`:

echo "hiiii it is docker here" > /usr/share/nginx/html/index.html  

![Change HTML](6.png)

---

### Step 7: View the Changes
Refresh `http://localhost:9001` to see the new content.

![Modified Page](7.png)

---

## 3. Spring PetClinic Application

### Step 8: Clone and Build the Project
Clone the PetClinic repo and build the Docker image:

git clone https://github.com/spring-projects/spring-petclinic.git  
cd spring-petclinic  
docker build -t spring-petclinic .  

![Clone and Build](8 (1).jpg)

---

### Step 9: Run the Application Container
Run the PetClinic container on port **8080**:

docker run -d -p 8080:8080 spring-petclinic  

![Run PetClinic](9 (1).jpg)

---

### Step 10: Access the Application
Navigate to **http://localhost:8080**.  
The Spring PetClinic app will be running.

![PetClinic Running](10 (1).png)

---

## 4. Pulling Different Docker Images

Here we try pulling different base images from Docker Hub.

### Step 11: Pull images
Alpine is a very lightweight Linux distribution, often used as a base image.

docker pull alpine  

✅ Image pulled successfully.  
---

### Step 12: Pull PHP
Pull the official PHP image:

docker pull php  

✅ Image pulled successfully.  
---

### Step 13: Pull Ubuntu
Pull the official Ubuntu image:

docker pull ubuntu  

✅ Image pulled successfully.  
---

### Step 14: Pull Node.js
At first, the commands `docker pull nodejs` and `docker pull nodjs` failed because such repositories don’t exist.  
The correct image name is `node`.

docker pull node  

✅ Image is downloading successfully.  
![Pull](11.png)






Pull nginx and make it run on 9000:80 and do login
![ 1](1.png)

Open the nginx page on browser 
![ 2](2.png)

Run nginx on another port 9001
![ 3](3.png)

Open the nginx page on browser 
![ 4](4.png)

Enter the nginx container
![ 5](5.png)

Change the conf 
![ 6](6.png)

Open the nginx page on browser and see the new conf 
![ 7](7.png)

clone the bit clinic project and build the container 
![ 8](8.png)

Made the container 
![ 9](9.png)

Open the bitclinic page on browser 
![ 10](10.png)

pull the images
![ 11](11.png)


