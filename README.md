Question1

# 1) Create the full directory structure with ONE mkdir -p command
mkdir -p /home/ec2-user/webapp/{scripts,logs,config}

# 2) Create config/app.conf using cat >
cat > /home/ec2-user/webapp/config/app.conf

APP_NAME=WebApp

PORT=8080

# 3) Create empty log file
touch /home/ec2-user/webapp/logs/app.log

# Confirm it is 0 bytes
ls -l /home/ec2-user/webapp/logs/app.log

## Set Permissions

# scripts directory permissions
chmod 755 /home/ec2-user/webapp/scripts

# app.conf permissions
chmod 644 /home/ec2-user/webapp/config/app.conf

## Meaning of 755
755 = rwx r-x r-x
For a directory:

* read = can view files
* write = can create/delete files
* execute = can enter/access directory

So 755 means:

* Owner has full control
* Everyone else can access and read, but cannot modify

---

## Meaning of 644

644 = rw- r-- r--

So 644 means:

* Owner can edit the file
* Everyone else can only read it

---

## Change Ownership Recursively

sudo chown -R root:root /home/ec2-user/webapp/

## Verify Ownership and Permissions

ls -lR /home/ec2-user/webapp/

/home/ec2-user/webapp/:
total 0
drwxr-xr-x 2 root root 22 May 15 10:35 config

drwxr-xr-x 2 root root 21 May 15 10:35 logs

drwxr-xr-x 2 root root  6 May 15 10:35 scripts

/home/ec2-user/webapp/config:
total 4
-rw-r--r-- 1 root root 30 May 15 10:35 app.conf

/home/ec2-user/webapp/logs:
total 0
-rw-r--r-- 1 root root 0 May 15 10:35 app.log

/home/ec2-user/webapp/scripts:
total 0

<img width="900" height="836" alt="image" src="https://github.com/user-attachments/assets/86389486-3de7-4bb3-8722-57d472c78f7f" />

