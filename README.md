# ☁️ Three-Tier Web Application (PHP + AWS EC2 + RDS)

**Author:** Prasad
**LinkedIn:** [linkedin.com/in/prasad-bhoite-a38a64223](#)
**Project Type:** AWS Cloud | Three-Tier Architecture
**Version:** 1.0
**License:** MIT

---

## 🧭 Project Summary

This project showcases a **Three-Tier Cloud Architecture** built using **AWS EC2 (Ubuntu)** and **RDS MySQL**.
It separates the application into **Presentation**, **Application**, and **Database** layers to achieve **scalability, security, and modularity**.

### Architecture Overview

* 🖥️ **Tier 1 – Web Tier:**
  Hosts the frontend on an **EC2 (Ubuntu)** instance with **Nginx** serving the HTML interface.

* ⚙️ **Tier 2 – Application Tier:**
  Another **EC2 instance** running **PHP backend logic** that processes user requests and interacts with the database.

* 💾 **Tier 3 – Database Tier:**
  Uses **AWS RDS (MySQL)** to securely store and manage application data.

---

## 🔄 Data Flow Summary

**User (Web Tier)** → **PHP Logic (App Tier)** → **Database Insert (RDS)** → **Response Sent Back to User**

---

## 💡 Key Highlights

✅ Secure communication between all tiers using AWS Security Groups
✅ Modular design for easy scaling and maintenance
✅ Real-world **3-Tier architecture** used in enterprise applications
✅ Simple setup with clear separation of frontend, backend, and database
✅ Beginner to intermediate-level project for **Cloud & DevOps** learners

---

## 🧠 Learning Outcomes

* Understood **3-Tier Architecture** and its practical implementation on AWS
* Gained experience deploying apps across **multiple EC2 instances**
* Configured **AWS RDS (MySQL)** and securely connected it with backend EC2
* Practiced setting up **networking rules and IAM roles** for secure access
* Learned how to separate and manage web, app, and database layers efficiently

---

## 🧱 Application Overview

Users interact with a **frontend form (Web Tier)** that sends data to a **PHP backend (App Tier)**, which then stores it in an **RDS MySQL database (DB Tier)**.

### Core Components

| Tier         | Component       | Description                                    |
| ------------ | --------------- | ---------------------------------------------- |
| 1️⃣ Web Tier | `form.html`    | Frontend UI form served by Nginx/Apache        |
| 2️⃣ App Tier | `submit.php`   | Handles logic, connects to RDS, processes data |
| 3️⃣ DB Tier  | AWS RDS (MySQL) | Stores form submissions securely               |

---

## 📁 Folder Structure

```
three-tier-app/
│
├── web/
│   └── form.html         # Frontend (Presentation Layer)
│
├── app/
│   └── submit.php        # Application Logic (Backend)
│
├── images/                # Screenshots or architecture diagrams
│
└── README.md              # Project documentation
```

---

## 🛠️ Tech Stack

* **Frontend:** HTML
* **Backend:** PHP
* **Database:** MySQL (AWS RDS)
* **Servers:** Ubuntu (EC2 Instances)
* **Web Server:** Nginx 
* **Platform:** Amazon Web Services (AWS)

---

## ⚙️ AWS Setup Summary

### 🧩 EC2 Instances

* **Web Server EC2:** Hosts frontend (`form.html`)
* **App Server EC2:** Hosts backend (`submit.php`) and connects to RDS
* Use **Ubuntu 22.04** AMI for both instances

### 💾 RDS (MySQL)

* Create **RDS MySQL** instance with public accessibility *disabled*
* Connect using private endpoint from **App EC2**

### 🔒 Security Groups

| Component | Inbound Rules                                       | Outbound Rules |
| --------- | --------------------------------------------------- | -------------- |
| Web EC2   | HTTP (80), SSH (22)                                 | Allow all      |
| App EC2   | HTTP (80), SSH (22), MySQL (3306 from App EC2 only) | Allow all      |
| RDS       | MySQL (3306) from App EC2 SG                        | Allow all      |

---

## 🚀 Deployment Steps

1. **Launch EC2 Instances:**

   * One for Web Tier and one for Application Tier (Ubuntu OS).

2. **Install Required Packages:**

   ```bash
   sudo apt update
   sudo apt install nginx php php-mysql -y
   ```

3. **Set Up Web Tier (Frontend):**

   * Place `form.html` in `/var/www/html/`

4. **Set Up Application Tier (Backend):**

   * Place `submit.php` in `/var/www/html/`
   * Update PHP file with RDS credentials and endpoint

5. **Create RDS MySQL Database:**

   * Configure database name, username, and password
   * Enable inbound access for App EC2 Security Group only

6. **Configure Connections:**

   * Ensure App EC2 can reach RDS via `telnet <RDS-endpoint> 3306`

7. **Access Application:**

   * Visit your **Web EC2 public IP** in the browser
   * Submit the form and verify data in **RDS Database**


---

## 🌱 Future Enhancements

* Add CSS and JS for better frontend design
* Implement **Load Balancer (ALB)** between Web and App tiers
* Add **Auto Scaling** for App Tier
* Use **AWS Secrets Manager** for database credentials
* Deploy using **Terraform or CloudFormation** for automation

---

## 🏁 Conclusion

This project demonstrates how a **Three-Tier Web Application** can be deployed on **AWS** using **EC2 and RDS** with a secure, scalable architecture.
It provides a **solid foundation for Cloud & DevOps learners** to understand how real-world applications are designed, deployed, and scaled in the cloud environment.

---

**👤 Author:** Prasad

**LinkedIn:** [linkedin.com/in/prasad-bhoite-a38a64223](#)

**License:** MIT
