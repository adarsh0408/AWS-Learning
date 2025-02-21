# **Chapter 1: AWS EC2 (Elastic Compute Cloud)**

## **📌 Introduction**

AWS EC2 (Elastic Compute Cloud) is a foundational service that provides **virtual servers (instances)** in the cloud. These instances can run different operating systems, host applications, and scale based on demand.

## **1️⃣ What is EC2?**

EC2 allows users to launch and manage **virtual machines** on AWS infrastructure.

✅ **Key Features:**

- **Scalability** – Easily increase or decrease the number of instances.
- **Customization** – Choose OS, CPU, RAM, storage, and network configurations.
- **Pay-as-you-go** – Only pay for what you use.
- **Security** – Control access using **Key Pairs** and **Security Groups**.

## **2️⃣ EC2 Instance Types**

AWS provides different EC2 instance types optimized for various workloads.

| **Instance Type**     | **Best For**              | **Examples**              |
| --------------------- | ------------------------- | ------------------------- |
| **General Purpose**   | Web apps, small databases | `t2.micro`, `t3.medium`   |
| **Compute Optimized** | High CPU tasks            | `c5.large`, `c6g.xlarge`  |
| **Memory Optimized**  | Large databases, caching  | `r5.large`, `x1e.2xlarge` |
| **Storage Optimized** | Big data, file processing | `i3.large`, `d2.2xlarge`  |

## **3️⃣ How to Launch an EC2 Instance (Step-by-Step Guide)**

### **🔹 Step 1: Open EC2 Dashboard**

1. Go to **AWS Console → EC2 Dashboard**
2. Click **Instances → Launch Instance**

### **🔹 Step 2: Choose an AMI (Amazon Machine Image)**

✅ Select **Amazon Linux 2023** (Free Tier Eligible)

### **🔹 Step 3: Choose an Instance Type**

✅ Select **t2.micro (1 vCPU, 1 GB RAM)** (Free Tier Eligible)

### **🔹 Step 4: Configure Instance Details**

- **Number of Instances:** 1
- **Network (VPC):** Default
- **Auto-assign Public IP:** Enabled

### **🔹 Step 5: Add Storage**

✅ Default: **8GB EBS (gp3 SSD)** (Free Tier Eligible)

### **🔹 Step 6: Configure Security Group**

- **Allow SSH (port 22) from your IP**
- **(Optional) Allow HTTP (port 80) for web access**

### **🔹 Step 7: Create & Download a Key Pair**

- Name it **adarsh-key.pem**
- Download and **store securely**

### **🔹 Step 8: Launch the Instance**

✅ Go to **EC2 Dashboard → Instances** and wait for the status to be **Running**.

## **4️⃣ Connecting to Your EC2 Instance (SSH Access)**

### **🔹 Step 1: Get Public IP**

- Go to **EC2 Dashboard → Instances**
- Copy the **Public IPv4 Address**

### **🔹 Step 2: Connect via SSH**

```sh
ssh -i path/to/adarsh-key.pem ec2-user@your-ec2-public-ip
```

📌 Example:

```sh
ssh -i ~/Downloads/adarsh-key.pem ec2-user@3.84.216.35
```

## **5️⃣ Elastic IPs (Static Public IPs)**

By default, EC2 instances get **dynamic public IPs** that change when restarted. **Elastic IPs** provide a permanent public IP.

### **🔹 Allocating and Associating an Elastic IP**

1. Go to **EC2 Dashboard → Elastic IPs**
2. Click **Allocate Elastic IP** → **Allocate**
3. Select **Actions → Associate Elastic IP**
4. Choose your EC2 instance → Click **Associate**

## **6️⃣ Elastic Load Balancer (ELB)**

An **Elastic Load Balancer (ELB)** distributes traffic across multiple EC2 instances for high availability.

### **🔹 Creating an Application Load Balancer (ALB)**

1. Go to **EC2 Dashboard → Load Balancers → Create Load Balancer**
2. Select **Application Load Balancer**
3. Name it **adarsh-alb** → Choose **Internet-facing**
4. Add a listener for **HTTP (Port 80)**
5. Create a **Target Group** → Register EC2 instances
6. Click **Create Load Balancer**

📌 **Now, your Load Balancer will distribute traffic to your EC2 instances!**

## **✅ Summary**

✔️ **What is EC2?** – Virtual servers in AWS\
✔️ **How to Launch an EC2 Instance** – Step-by-step guide\
✔️ **How to Connect via SSH** – Securely access your server\
✔️ **What is an Elastic IP?** – Assign a static IP\
✔️ **What is a Load Balancer?** – Distribute traffic across instances

## **🚀 Next Steps**

Next, we will learn about **Auto Scaling (Scaling EC2 instances automatically)** and AWS storage services like **S3, EBS, and EFS**!

