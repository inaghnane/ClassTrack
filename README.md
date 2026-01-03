📌 QR-Based Absenteeism Management System

🧠 Project Overview

This project is a distributed absenteeism management system designed for universities. It allows students to confirm their attendance by scanning a QR code displayed by the professor during a session.

The main objective of this project is to apply and demonstrate gRPC architecture in a real-world academic use case, as required in the Distributed Systems module. The professor explicitly required the use of gRPC to ensure efficient, scalable, and well-structured communication between services.

🎯 Objectives

Eliminate manual attendance sheets

Prevent cheating and false attendance

Simplify attendance management for professors

Provide real-time, reliable communication using gRPC

Apply concepts of distributed systems in practice

🛠️ Technologies Used

Front-End

Next.js (React framework)

Role-based interfaces (Admin / Professor / Student)

Back-End

Python (gRPC server)

Protocol Buffers (Protobuf) for service definitions

Database

MariaDB

Architecture

gRPC (Google Remote Procedure Call)

🧩 Why gRPC?

The core goal of this project is to implement a distributed system using gRPC instead of traditional REST APIs.

gRPC allows:

🔹 High-performance communication (binary data)

🔹 Strongly typed contracts using .proto files

🔹 Clear separation between services

🔹 Easy scalability and service-to-service communication

In this system:

The Next.js client communicates with the Python gRPC server

The server handles business logic and database access

All interactions (authentication, sessions, attendance, QR validation) are exposed as gRPC services

🏗️ System Architecture

[ Next.js Client ]
        │
        │ gRPC calls
        ▼
[ Python gRPC Server ]
        │
        │ SQL Queries
        ▼
[ MariaDB Database ]

Each role (Admin, Professor, Student) communicates with the backend via defined gRPC services.

👥 User Roles & Features

👨‍💼 Administrator

Manage professors

Manage students

Create and manage sessions

Global system supervision

👨‍🏫 Professor

Create and manage students

Create sessions

Generate QR codes for sessions

Mark attendance:

Automatically (via QR scan)

Manually (if needed)

View attendance reports

🎓 Student

Scan QR code to confirm presence

View attendance and absence history

Join sessions securely

🔄 Communication Flow (How It Works)

1️⃣ Session Creation

The professor creates a session via the interface

Backend stores the session in MariaDB

2️⃣ QR Code Generation

The professor requests a QR code

Backend generates a unique session token

Token is encoded into a QR code and displayed

3️⃣ Attendance Validation

Student scans the QR code

The client sends the token via gRPC

Backend verifies:

Session validity

Student identity

Time constraints

Attendance is recorded in the database

4️⃣ Consultation

Students and professors can consult attendance data

All data is retrieved through gRPC services

🔐 Security & Anti-Cheating Measures

Unique QR codes per session

Time-limited session tokens

Student authentication before validation

Server-side verification

📂 Project Structure (Simplified)

/frontend
  └── Next.js application

/backend
  ├── grpc_server.py
  ├── services/
  ├── proto/
  │     └── attendance.proto
  └── database/

/database
  └── MariaDB schema

📚 Academic Context

This project was developed as part of the Distributed Systems module. The main pedagogical goal was to:

Understand service-oriented architectures

Implement gRPC-based communication

Design a scalable and efficient distributed application

✅ Conclusion

This QR-based absenteeism system successfully combines:

Modern web technologies

A real academic use case

A robust gRPC distributed architecture

It demonstrates how gRPC can be used effectively beyond microservices, in educational platforms requiring speed, reliability, and structure.
