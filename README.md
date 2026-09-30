# MongoDB-report
Yes. For GitHub, use plain Markdown in README.md. Copy everything below directly into your README file.

# 📚 MongoDB Student Database Project

A practical MongoDB project demonstrating student record management using **MongoDB Shell (mongosh)**. The project covers CRUD operations, query operators, logical operators, searching, and database verification.

---

## 📌 Project Overview

This project demonstrates practical **NoSQL database operations** using MongoDB.

### 🗄️ Database Details

| Property | Value |
|---|---|
| Database | `studentProjectDB` |
| Collection | `studentRecords` |
| Total Records | 51 |
| Roll Numbers | 201–250 |
| Database Type | NoSQL |
| Tool | MongoDB Shell (`mongosh`) |

---

## 🛠️ Technologies Used

- MongoDB
- MongoDB Shell (mongosh)
- MongoDB Query Language
- NoSQL Database

---

## 📊 Student Record Structure

Each student document contains:

```text
rollNo
name
age
department
marks

Some update operations also add:

status

Example Document

{
  rollNo: 201,
  name: "Aman",
  age: 20,
  department: "AI",
  marks: 84
}


---

🔄 CRUD Operations

1. Create / Select Database

use studentProjectDB


---

2. Insert One

Inserts a single student record.

db.studentRecords.insertOne({
  rollNo: 201,
  name: "Aman",
  age: 20,
  department: "AI",
  marks: 84
})


---

3. Insert Many

Inserts multiple student records from roll number 202 to 250.

Example:

db.studentRecords.insertMany([
  {
    rollNo: 202,
    name: "Rohan",
    age: 19,
    department: "DS",
    marks: 76
  },
  {
    rollNo: 203,
    name: "Meera",
    age: 21,
    department: "AI",
    marks: 91
  }
])

Departments Used

AI

DS

BCA

CS



---

4. Update One

Updates the marks of roll number 201.

84 → 90

db.studentRecords.updateOne(
  { rollNo: 201 },
  { $set: { marks: 90 } }
)


---

5. Update Many

Adds status: "Active" to all AI department students.

db.studentRecords.updateMany(
  { department: "AI" },
  { $set: { status: "Active" } }
)


---

6. Delete One

Deletes the student with roll number 250.

db.studentRecords.deleteOne({
  rollNo: 250
})


---

7. Delete Many

Deletes students whose marks are less than 40.

db.studentRecords.deleteMany({
  marks: { $lt: 40 }
})


---

🔎 Query Operations

$gt — Greater Than

Find students with marks greater than 80.

db.studentRecords.find({
  marks: { $gt: 80 }
})


---

$lt — Less Than

Find students with marks less than 80.

db.studentRecords.find({
  marks: { $lt: 80 }
})


---

$eq — Equal To

Find students with exactly 85 marks.

db.studentRecords.find({
  marks: { $eq: 85 }
})


---

$gte — Greater Than or Equal To

db.studentRecords.find({
  marks: { $gte: 80 }
})


---

$ne — Not Equal To

db.studentRecords.find({
  marks: { $ne: 85 }
})


---

🧠 Logical Operators

$and

Find students whose:

Marks are greater than 70

Age is less than 23


db.studentRecords.find({
  $and: [
    { marks: { $gt: 70 } },
    { age: { $lt: 23 } }
  ]
})


---

$or

Find students from either AI or DS.

db.studentRecords.find({
  $or: [
    { department: "AI" },
    { department: "DS" }
  ]
})


---

$not

Find students whose marks are not greater than 80.

db.studentRecords.find({
  marks: { $not: { $gt: 80 } }
})


---

📋 Verification Operations

Show Current Database

db

Show Collections

show collections

Display All Students

db.studentRecords.find()

Display Records in Readable Format

db.studentRecords.find().pretty()

Count Total Documents

db.studentRecords.countDocuments()

Count AI Students

db.studentRecords.countDocuments({
  department: "AI"
})

Count DS Students

db.studentRecords.countDocuments({
  department: "DS"
})

Count BCA Students

db.studentRecords.countDocuments({
  department: "BCA"
})

Count CS Students

db.studentRecords.countDocuments({
  department: "CS"
})


---

🔍 Student Search Operations

Find Student by Roll Number

db.studentRecords.find({
  rollNo: 201
})

Find AI Students

db.studentRecords.find({
  department: "AI"
})

Find DS Students

db.studentRecords.find({
  department: "DS"
})

Find BCA Students

db.studentRecords.find({
  department: "BCA"
})

Find CS Students

db.studentRecords.find({
  department: "CS"
})


---

🎯 Learning Objectives

This project provides practical understanding of:

NoSQL databases

MongoDB databases

Collections and documents

CRUD operations

MongoDB Shell

MongoDB Query Language

Comparison operators

Logical operators

Updating documents

Deleting documents

Searching and filtering records

Counting documents

Database verification



---

🚀 How to Run

Step 1 — Install MongoDB

Install MongoDB and MongoDB Shell (mongosh).

Step 2 — Open MongoDB Shell

mongosh

Step 3 — Select Database

use studentProjectDB

Step 4 — Use Collection

db.studentRecords

Step 5 — Run the Commands

Run the commands from the project in sequence and verify the output after each operation.


---

📂 Project Structure

MongoDB-Student-Database-Operations/
│
├── README.md
│
└── MongoDB_Student_Database_Project.pdf


---

🎓 Academic Information

Field	Details

Project	MongoDB Student Database Project
Course	NoSQL and DBaaS
Program	BCA DS & AI
Session	2026–2027



---

👨‍💻 Author

Ujjval Singh

BCA DS & AI


---

⭐ Project Highlights

✅ MongoDB NoSQL Database

✅ Student Records Management

✅ CRUD Operations

✅ Insert One & Insert Many

✅ Update One & Update Many

✅ Delete One & Delete Many

✅ Comparison Operators

✅ Logical Operators

✅ Department-wise Searching

✅ Document Counting

✅ Database Verification

✅ MongoDB Shell Practice

✅ Academic Practical Project



---

📜 License

This project is created for educational and academic purposes.

You are welcome to study and use the concepts demonstrated in this project for learning and practical practice.

**One correction:** your dataset has **51 records total**, but the roll-number range is **201–250**, which is only 50 roll numbers. That's because **201 is inserted separately and 202–250 are inserted with `insertMany()`**. This README reflects that correctly.
