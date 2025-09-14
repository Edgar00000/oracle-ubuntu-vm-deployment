# Oracle Ubuntu VM Deployment Project

## Overview
This project demonstrates setting up an Ubuntu Virtual Machine (VM) on VirtualBox, deploying Nginx locally and on AWS EC2, and managing services using Docker and Docker Compose.  
It also covers integration with VirtualBox features (shared folders, SSH setup) and shows a full container lifecycle: setup → run → scale → monitor → cleanup.

---

## Steps & Screenshots

### Step 1 – EC2 Dashboard
![EC2 Dashboard](./screenshots/ec2-dashboard.png)

### Step 2 – SSH Login
![SSH Login](./screenshots/ssh_login.png)

### Step 3 – Nginx Running in VirtualBox
![Nginx VirtualBox](./screenshots/nginx_virtualbox.png)  
![Nginx Welcome](./screenshots/nginx_welcome.png)

### Step 4 – Nginx on Port 8081
![Nginx Port 8081](./screenshots/nginx_8081_ok.png)

### Step 5 – Docker Container Running (Port 8081)
![Docker Container](./screenshots/docker_ps_8081.png)

### Step 6 – Multiple Containers via Docker Compose (Ports 8083–8085)
![Compose Curl 8083–8085](./screenshots/curl_8083_8084_8085_ok.png)

### Step 7 – Docker Monitoring & Images
![Docker Stats and HTTP Responses](./screenshots/08_docker_stats_and_http_responses.png)  
![Docker Stats and Images Combined](./screenshots/09-10-docker-stats-and-image.png)

### Step 8 – Docker Cleanup
![Docker Cleanup](./screenshots/11-docker-cleanup.png)

### Step 9 – VirtualBox Integration
![Shared Folder](./screenshots/shared_folder.png)  
![SSH VirtualBox](./screenshots/ssh_virtualbox.png)  
![VM Desktop](./screenshots/virtualbox_desktop.png)

---

## Additional Reference Screenshots
These are extra supporting screenshots that provide more details on the setup process.

- ![Docker Version](./docker-version.png)  
- ![Nginx Installed in VM](./nginx-installed-vm.png)  
- ![Nginx Port Forward Setup](./Nginx-installed-portfoward.png)  
- ![Shared Folder Proof](./shared-folder-proof.png)  
- ![SSH Localhost](./ssh-localhost.png)

---

## Extra Documentation
A Word document with additional screenshots is included for reference:  
📄 [oracle-vm-deployment.docx](./oracle-vm-deployment.docx)

---

## Commands Reference

### Docker Lifecycle
```bash
# Run Nginx container
sudo docker run -d --name demo-nginx -p 8081:80 nginx

# List containers
sudo docker ps

# Curl test
curl -I http://127.0.0.1:8081

# Run multiple containers with Compose
sudo docker-compose up -d

# Monitor usage
sudo docker stats --no-stream

# List images
sudo docker images

# Cleanup
sudo docker stop $(sudo docker ps -q)
sudo docker rm $(sudo docker ps -aq)
sudo docker network prune -f
sudo docker rmi nginx
```
