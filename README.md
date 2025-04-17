# Monitor-System-Resources-using-Netdata
# 🖥️ Monitor System Resources Using Netdata (Docker)

## 📌 Objective
Install and run Netdata using Docker to monitor real-time system metrics and view performance dashboards. Explore logs and properly clean up the environment after use.

## 🛠️ Tools & Technologies
- Netdata (Containerized)
- Docker

## 🧪 Steps Performed

### ✅ Step 1: Run Netdata Using Docker
```bash
docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE --security-opt apparmor=unconfined netdata/netdata
This command:

Runs Netdata in detached mode (-d)

Names the container netdata

Maps host port 19999 to container port 19999

Grants necessary permissions for system metrics

✅ Step 2: Access Netdata Dashboard
Open your browser and go to:


http://localhost:19999
Here you can monitor:

CPU usage per core

RAM and swap memory

Disk I/O statistics

Network traffic and packet stats

Docker container metrics (if running)

Alerts, alarms, and historical charts

✅ Step 3: Access Logs Inside the Container
Enter the Netdata container shell:

docker exec -it netdata /bin/bash
Navigate to the logs directory:

cd /var/log/netdata
ls
View log files:

cat error.log      # View errors and internal issues
cat access.log     # View dashboard access logs
Exit the container:

✅ Step 4: Stop & Clean Up
Stop the running Netdata container:

docker stop netdata
Remove the container:

docker rm netdata

docker rmi netdata/netdata
