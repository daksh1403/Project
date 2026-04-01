# Attendance Manager - "Shortage Predictor"

## DA2 C++ Mini Project Documentation

---

### Cover Page

**Project Title:** Attendance Manager - Shortage Predictor

**Student Name:** Daksh Agarwal

**Registration Number:** 25BCE5098

**Course:** Data Structures and Object Oriented Programming with C++

**Project Question Number:** 6

**GitHub Repository:** https://github.com/daksh1403/Project

---

## 1. Problem Statement

A class advisor needs a tool to quickly identify shortage students based on attendance entries. The system should:
- Maintain student registration details
- Track daily attendance (Present/Absent)
- Generate comprehensive attendance reports
- Identify students below 75% attendance threshold
- Predict how many consecutive classes a student needs to attend to reach 75%

## 2. Features Implemented

### Core Features:
1. **Add Student** - Register new students with unique RegNo
2. **Add Students List** - Bulk add multiple students
3. **Mark Attendance** - Record P/A for a specific date
4. **View Student Attendance** - Detailed summary for individual student
5. **Display All Students** - List all registered students
6. **Search Student** - Find by RegNo or name keyword
7. **Delete Student** - Remove with confirmation

### Reports:
1. **Attendance % per Student** - Shows attendance percentage with SAFE/SHORTAGE status
2. **Shortage Students** - Lists all students below 75% with classes needed to reach 75%
3. **Class Average Statistics** - Overall class statistics including highest, lowest, and average attendance

### Validations:
- Only P/A accepted for attendance marking
- Duplicate RegNo not allowed
- File persistence - data saved/loaded automatically

---

## 3. Class Structure (OOP Design)

### Class: Student
| Member | Type | Description |
|--------|------|-------------|
| regNo | string (private) | Registration number |
| name | string (private) | Student name |
| attendanceRecords | vector<pair<string,char>> (private) | Date-wise attendance |

| Method | Return Type | Description |
|--------|-------------|-------------|
| getRegNo() | string | Returns registration number |
| getName() | string | Returns student name |
| markAttendance(date, status) | bool | Marks P/A for a date |
| calculateAttendancePercentage() | double | Returns attendance % |
| getTotalPresent() | int | Count of present days |
| getTotalClasses() | int | Total classes conducted |
| display() | void | Displays student info |
| displayAttendanceSummary() | void | Detailed attendance report |
| serialize() | string | Converts to file format |
| deserialize(data) | void | Loads from file format |

### Class: AttendanceManager
| Member | Type | Description |
|--------|------|-------------|
| students | vector<Student> (private) | List of all students |
| dataFile | string (private) | Data file path |

| Method | Return Type | Description |
|--------|-------------|-------------|
| saveToFile() | void | Saves data to file |
| loadFromFile() | void | Loads data from file |
| addStudent(regNo, name) | bool | Adds new student |
| addStudentsList() | void | Bulk add students |
| markAttendanceForDate() | void | Mark attendance for all |
| viewStudentAttendance() | void | Show individual summary |
| displayAllStudents() | void | List all students |
| searchStudent() | void | Search by keyword |
| deleteStudent() | bool | Delete with confirm |
| reportAttendancePercentage() | void | Generate % report |
| reportShortageStudents() | void | List shortage students |
| reportClassAverage() | void | Class statistics |

---

## 4. File Format Description

**File Name:** attendance_data.txt

**Format:** Each line represents one student
```
RegNo|Name|Date1:Status1,Date2:Status2,...
```

**Example:**
```
25BCE5098|Daksh Agarwal|01-04-2026:P,02-04-2026:P,03-04-2026:A
25BCE5101|Pratyush Singh|01-04-2026:P,02-04-2026:A,03-04-2026:A
```

**Fields:**
- Pipe (|) separates main fields
- Colon (:) separates date from status
- Comma (,) separates multiple attendance records

---

## 5. Test Cases

| S.No | Test Case | Input | Expected Output | Actual Output | Status |
|------|-----------|-------|-----------------|---------------|--------|
| 1 | Add valid student | RegNo: 25BCE1001, Name: Test User | Student added successfully | Student added successfully | PASS |
| 2 | Add duplicate RegNo | Same RegNo twice | Error: Student already exists | Error displayed | PASS |
| 3 | Mark valid attendance | P for present | Attendance marked | Attendance marked | PASS |
| 4 | Mark invalid attendance | X instead of P/A | Error: Invalid input | Error displayed | PASS |
| 5 | Shortage detection | Student with 60% | Listed in shortage report | Listed correctly | PASS |
| 6 | Classes needed calculation | 70% attendance | Need 2 consecutive classes | Calculated correctly | PASS |
| 7 | File persistence | Exit and restart | Data loaded correctly | Data preserved | PASS |
| 8 | Search by name | Partial name | Matching students found | Found correctly | PASS |

---

## 6. Screenshots

### Screenshot 1: Main Menu
```
╔══════════════════════════════════════════════════════════════════╗
║         ATTENDANCE MANAGER - SHORTAGE PREDICTOR                  ║
║         DA2 Mini Project - C++ OOP                               ║
║         Student: Daksh Agarwal (25BCE5098)                       ║
╚══════════════════════════════════════════════════════════════════╝

┌──────────────────────────────────────┐
│           MAIN MENU                  │
├──────────────────────────────────────┤
│  1. Add Student                      │
│  2. Add Students List                │
│  3. Mark Attendance for Date         │
│  4. View Student Attendance          │
│  5. Display All Students             │
│  6. Search Student                   │
│  7. Delete Student                   │
├──────────────────────────────────────┤
│           REPORTS                    │
├──────────────────────────────────────┤
│  8. Attendance % per Student         │
│  9. Shortage Students (Below 75%)    │
│ 10. Class Average Statistics         │
├──────────────────────────────────────┤
│  0. Exit                             │
└──────────────────────────────────────┘
```

### Screenshot 2: Shortage Students Report
```
======================================================================
            SHORTAGE STUDENTS (Below 75%)
======================================================================
Reg No         Name                     Present/Total  Percentage     Classes to 75%
----------------------------------------------------------------------
25BCE5101      Pratyush Singh           4/10           40.00%         14
25BCE5098      Daksh Agarwal            7/10           70.00%         2
----------------------------------------------------------------------
Total shortage students: 2 out of 3
======================================================================
```

### Screenshot 3: Class Statistics
```
======================================================================
               CLASS ATTENDANCE STATISTICS
======================================================================

Total Students          : 3
----------------------------------------
Class Average Attendance: 66.67%
----------------------------------------
Highest Attendance      : 90.00%
                          Keerthana K (25BCE5085)
Lowest Attendance       : 40.00%
                          Pratyush Singh (25BCE5101)
----------------------------------------
Students Above 75%      : 1 (33.3%)
Students Below 75%      : 2 (66.7%)
======================================================================
```

---

## 7. AI Usage Declaration

**AI Tools Used:** GitHub Copilot CLI

**Purpose:** Code generation assistance, documentation formatting

**Verification:** All code tested manually with multiple test cases. Logic verified for correctness.

---

## 8. Conclusion

The Attendance Manager system successfully implements all required features:
- ✅ Student management with unique RegNo validation
- ✅ Date-wise attendance tracking (P/A only)
- ✅ File persistence for data storage
- ✅ Attendance percentage calculation
- ✅ Shortage prediction (below 75% identification)
- ✅ Classes needed calculation to reach 75%
- ✅ Class average statistics
- ✅ OOP design with proper encapsulation

The system uses two classes (`Student` and `AttendanceManager`) following proper OOP principles with encapsulation, data hiding, and file persistence.

---

**Submitted by:** Daksh Agarwal (25BCE5098)
