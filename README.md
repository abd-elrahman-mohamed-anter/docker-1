تمام ✅ خلّيت العناوين كبيرة واضحة برا الكود، والـ **commands** نفسها جوا بلوكات `shell` عشان تبان إنها قابلة للكوبي زي GitHub.

شوف الشكل ده:

---

# 🐳 Docker Nginx and Spring PetClinic Guide

This guide demonstrates how to use Docker to run and manage an **Nginx web server**, a **Spring PetClinic application**, and how to pull common base images.

---

## 1️⃣ Nginx Web Server

### Step 1: Login and Run Nginx

```sh
docker login
docker pull nginx
docker run -d -p 9000:80 nginx
```

![Nginx Run](1.png)

---

### Step 2: View Nginx in the Browser

Navigate to **[http://localhost:9000](http://localhost:9000)**
![Nginx Browser](2.png)

---

### Step 3: Run Nginx on a Different Port

```sh
docker run -d -p 9001:80 nginx
docker ps
```

![Docker ps](3.png)

---

### Step 4: Access the Second Nginx Instance

Go to **[http://localhost:9001](http://localhost:9001)**
![Second Nginx](4.png)

---

## 2️⃣ Modifying the Nginx Content

### Step 5: Enter the Container

```sh
docker exec -it <container_id> /bin/sh
```

![Exec into Container](5.png)

---

### Step 6: Change the Default Page

```sh
echo "hiiii it is docker here" > /usr/share/nginx/html/index.html
```

![Change HTML](6.png)

---

### Step 7: View the Changes

Refresh **[http://localhost:9001](http://localhost:9001)**
![Modified Page](7.png)

---

## 3️⃣ Spring PetClinic Application

### Step 8: Clone and Build the Project

```sh
git clone https://github.com/spring-projects/spring-petclinic.git
cd spring-petclinic
docker build -t spring-petclinic .
```

!\[Clone and Build]\(8 (1).jpg)

---

### Step 9: Run the Application Container

```sh
docker run -d -p 8080:8080 spring-petclinic
```

!\[Run PetClinic]\(9 (1).jpg)

---

### Step 10: Access the Application

Go to **[http://localhost:8080](http://localhost:8080)**
!\[PetClinic Running]\(10 (1).png)

---

## 4️⃣ Pulling Different Docker Images

### Step 11: Pull Alpine

```sh
docker pull alpine
```

✅ Pulled successfully

---

### Step 12: Pull PHP

```sh
docker pull php
```

✅ Pulled successfully

---

### Step 13: Pull Ubuntu

```sh
docker pull ubuntu
```

✅ Pulled successfully

---

### Step 14: Pull Node.js

❌ `docker pull nodejs` → Not found
❌ `docker pull nodjs` → Not found

✅ Correct:

```sh
docker pull node
```

![Pull](11.png)

---


تحب أعمل **TOC (جدول محتويات)** صغير فوق يوديك لكل Section
