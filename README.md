# Attendance Manager - Shortage Predictor

## DA2 C++ Mini Project

**Student:** Daksh Agarwal  
**Registration Number:** 25BCE5098  
**Question Number:** 6

---

## 📋 Project Description

A class advisor tool to track student attendance, identify shortage students (below 75%), and predict how many consecutive classes a student needs to attend to reach the 75% threshold.

## ✨ Features

### Core Operations
- ➕ Add Student (with duplicate RegNo validation)
- 📝 Mark Attendance for specific date (P/A only)
- 🔍 Search Student (by RegNo or name)
- 🗑️ Delete Student (with confirmation)
- 📄 View All Students

### Reports
- 📊 Attendance Percentage per Student
- ⚠️ Shortage Students (Below 75%)
- 📈 Class Average Statistics

### Technical Features
- 💾 File persistence (auto save/load)
- ✅ Input validation
- 🎯 OOP Design with proper encapsulation

## 🏗️ OOP Structure

```
┌─────────────────────────────────────┐
│           Student Class             │
├─────────────────────────────────────┤
│ - regNo: string                     │
│ - name: string                      │
│ - attendanceRecords: vector         │
├─────────────────────────────────────┤
│ + markAttendance()                  │
│ + calculateAttendancePercentage()   │
│ + display()                         │
│ + serialize() / deserialize()       │
└─────────────────────────────────────┘

┌─────────────────────────────────────┐
│       AttendanceManager Class       │
├─────────────────────────────────────┤
│ - students: vector<Student>         │
│ - dataFile: string                  │
├─────────────────────────────────────┤
│ + addStudent()                      │
│ + markAttendanceForDate()           │
│ + reportShortageStudents()          │
│ + reportClassAverage()              │
│ + saveToFile() / loadFromFile()     │
└─────────────────────────────────────┘
```

## 🚀 How to Compile & Run

```bash
cd src
g++ -std=c++17 -o attendance_manager.exe main.cpp
./attendance_manager.exe
```

## 📁 File Format

Data is stored in `attendance_data.txt`:
```
RegNo|Name|Date1:P,Date2:A,Date3:P,...
```

## 📝 Documentation

See [DOCUMENTATION.md](DOCUMENTATION.md) for full project documentation including:
- Problem Statement
- Class Structure Tables
- Test Cases
- Screenshots

---

**© 2026 Daksh Agarwal | VIT University**