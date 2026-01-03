# 📌 ClassTrack – QR-Based Absenteeism Management System

## 🧠 Project Overview
**ClassTrack** is a distributed absenteeism management system designed for universities.  
It allows students to confirm their attendance by scanning a **QR code** displayed by the professor during a session.

The main objective of this project is to **apply and demonstrate the gRPC architecture** in a real academic use case, as required in the **Distributed Systems** module.  
The use of **gRPC** was a core requirement to ensure efficient, scalable, and well-structured communication between distributed services.

---

## 🎯 Objectives
- Eliminate manual attendance sheets  
- Prevent cheating and false attendance  
- Simplify attendance management for professors  
- Provide real-time and reliable communication using **gRPC**  
- Apply distributed systems concepts in practice  

---

## 🛠️ Technologies Used

### Front-End
- **Next.js** (React framework)
- Role-based interfaces (Administrator / Professor / Student)

### Back-End
- **Python** (gRPC server)
- **Protocol Buffers (Protobuf)** for service definitions

### Database
- **MariaDB**

### Architecture
- **gRPC (Google Remote Procedure Call)**

---

## 🧩 Why gRPC?
The core goal of **ClassTrack** is to implement a **distributed system** using **gRPC** instead of traditional REST APIs.

gRPC provides:
- High-performance communication using binary data  
- Strongly typed service contracts via `.proto` files  
- Clear separation between services  
- Easy scalability and service-to-service communication  

In this system:
- The **Next.js client** communicates with the **Python gRPC server**
- The server handles business logic and database access
- All interactions (authentication, sessions, attendance, QR validation) are exposed as **gRPC services**

---

## 🏗️ System Architecture

[ Next.js Client ]
│
│ gRPC calls
▼
[ Python gRPC Server ]
│
│ SQL Queries
▼
[ MariaDB Database ]

yaml
Copier le code

Each role (Administrator, Professor, Student) communicates with the backend through defined **gRPC services**.

---

## 👥 User Roles & Features

### 👨‍💼 Administrator
- Manage professors  
- Manage students  
- Create and manage sessions  
- System supervision  

### 👨‍🏫 Professor
- Create and manage students  
- Create sessions  
- Generate QR codes for sessions  
- Mark attendance:
  - Automatically (via QR scan)
  - Manually if needed  
- View attendance reports  

### 🎓 Student
- Scan QR codes to confirm presence  
- View attendance and absence history  
- Join sessions securely  

---

## 🔄 Communication Flow

### 1. Session Creation
- The professor creates a session via the interface  
- The backend stores the session in MariaDB  

### 2. QR Code Generation
- The professor requests a QR code  
- The backend generates a **unique session token**  
- The token is encoded into a QR code and displayed  

### 3. Attendance Validation
- The student scans the QR code  
- The client sends the token via gRPC  
- The backend verifies:
  - Session validity  
  - Student identity  
  - Time constraints  
- Attendance is recorded in the database  

### 4. Consultation
- Students and professors consult attendance data  
- Data is retrieved through gRPC services  

---

## 🔐 Security & Anti-Cheating Measures
- Unique QR codes per session  
- Time-limited session tokens  
- Student authentication before validation  
- Server-side verification  

---

## 📂 Project Structure

/frontend
└── Next.js application

/backend
├── grpc_server.py
├── services/
├── proto/
│ └── attendance.proto
└── database/

/database
└── MariaDB schema

yaml
Copier le code

---

## 📚 Academic Context
This project was developed as part of the **Distributed Systems** module.  
Its main pedagogical goals were to:
- Understand service-oriented architectures  
- Implement **gRPC-based communication**  
- Design a scalable distributed application  

---

## ✅ Conclusion
**ClassTrack** demonstrates how **gRPC** can be effectively used in an academic system requiring speed, reliability, and structured communication.  
It combines modern web technologies with a real-world university use case.

---

## 👨‍🏫 Supervision
Supervised by **Mr. Youssef El Habouz**

---

## 🔗 GitHub Repository
https://github.com/inaghnane/ClassTrack
