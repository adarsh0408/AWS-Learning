# **Chapter 2: Auto Scaling & AWS Storage (S3, EBS, EFS)**

## **📌 Introduction**
Auto Scaling ensures that your AWS environment scales up or down automatically based on demand. AWS storage services like **S3, EBS, and EFS** provide flexible storage solutions for various workloads.

---

# **🔹 Section 1: Auto Scaling**
## **1️⃣ What is Auto Scaling?**
Auto Scaling allows AWS to automatically adjust the number of EC2 instances based on traffic demand to ensure optimal performance and cost efficiency.

✅ **Key Benefits:**
- **Scalability** – Adjusts instance count based on traffic load.
- **Cost Optimization** – Reduces unnecessary costs by terminating idle instances.
- **High Availability** – Ensures application reliability with redundant instances.

## **2️⃣ Components of Auto Scaling**
### **1. Launch Template or Launch Configuration**
Defines how EC2 instances should be created (OS, instance type, security groups, etc.).

### **2. Auto Scaling Group (ASG)**
A group of instances that AWS scales automatically.

### **3. Scaling Policies**
Rules for when and how instances should be added or removed.
- **Dynamic Scaling** – Automatically adjusts based on metrics (CPU utilization, request count).
- **Scheduled Scaling** – Increases/decreases instances at specific times.

## **3️⃣ How to Set Up Auto Scaling (Step-by-Step)**
### **🔹 Step 1: Create a Launch Template**
1. Go to **EC2 Dashboard → Launch Templates → Create Launch Template**
2. Configure instance details (AMI, instance type, security groups, etc.)
3. Save the template

### **🔹 Step 2: Create an Auto Scaling Group**
1. Go to **EC2 Dashboard → Auto Scaling Groups → Create Auto Scaling Group**
2. Select the **Launch Template**
3. Define desired, min, and max instance counts (e.g., min=1, max=5)
4. Attach a Load Balancer (if needed)
5. Configure scaling policies (CPU usage threshold, scheduled actions)
6. Create the Auto Scaling Group

📌 **Now, AWS will automatically add or remove instances based on traffic demand!**

---

# **🔹 Section 2: AWS Storage Services**
## **1️⃣ Amazon S3 (Simple Storage Service)**
S3 is an object storage service used for storing and retrieving large amounts of data.

✅ **Key Features:**
- **Highly Scalable** – Stores unlimited data.
- **Durability & Security** – 99.999999999% (11 9s) durability.
- **Storage Classes** – Standard, IA (Infrequent Access), Glacier (Archival Storage).

### **📌 How to Create an S3 Bucket**
1. Go to **S3 Dashboard → Create Bucket**
2. Set a unique **Bucket Name** (e.g., `adarsh-bucket`)
3. Choose a region
4. Set permissions (public/private access)
5. Click **Create**

### **📌 Uploading Files to S3**
- Go to the bucket → Click **Upload** → Select files → Click **Upload**
- Use AWS CLI:
```sh
aws s3 cp myfile.txt s3://adarsh-bucket/
```

---

## **2️⃣ Amazon EBS (Elastic Block Store)**
EBS provides **persistent block storage** for EC2 instances.

✅ **Key Features:**
- **High Performance** – SSD and HDD options available.
- **Durability** – Data is retained even if an EC2 instance is stopped.
- **Snapshots** – Create backups of volumes.

### **📌 How to Attach an EBS Volume**
1. Go to **EC2 Dashboard → Volumes → Create Volume**
2. Choose **Size & Type** (e.g., 10GB, gp3 SSD)
3. Attach it to an EC2 instance
4. SSH into the instance and mount the volume:
```sh
sudo mkfs -t ext4 /dev/xvdf
sudo mkdir /data
sudo mount /dev/xvdf /data
```

---

## **3️⃣ Amazon EFS (Elastic File System)**
EFS provides **shared, scalable file storage** for multiple EC2 instances.

✅ **Key Features:**
- **Fully Managed** – AWS handles scaling and maintenance.
- **Concurrent Access** – Multiple instances can access the same file system.
- **Pay for Usage** – No need to pre-provision storage.

### **📌 How to Create and Mount an EFS File System**
1. Go to **EFS Dashboard → Create File System**
2. Choose the VPC and Security Group
3. Mount the file system using AWS CLI:
```sh
sudo yum install -y amazon-efs-utils
sudo mkdir /mnt/efs
sudo mount -t efs fs-12345678:/ /mnt/efs
```

---

## **✅ Summary**
✔️ **Auto Scaling** – Automatically scales EC2 instances based on demand  
✔️ **S3** – Object storage for unlimited data  
✔️ **EBS** – Persistent block storage for EC2 instances  
✔️ **EFS** – Shared file system for multiple EC2 instances  

## **🚀 Next Steps**
Next, we will learn about **AWS Networking (VPC, Subnets, Route Tables, and Security Groups)!**

