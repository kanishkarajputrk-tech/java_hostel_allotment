# 🏠 Hostel Room Allotment System

> A console-based Java application to digitally manage hostel room allotments, student records, occupancy tracking, and report generation for college hostels.

[![Java](https://img.shields.io/badge/Java-8%2B-orange?style=flat-square&logo=java)](https://www.oracle.com/java/)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20Mac-blue?style=flat-square)]()
[![Type](https://img.shields.io/badge/Type-Console%20Application-green?style=flat-square)]()
[![License](https://img.shields.io/badge/License-Academic-lightgrey?style=flat-square)]()

---

## 📋 Table of Contents

- [Problem Statement](#-problem-statement)
- [Features](#-features)
- [Project Structure](#-project-structure)
- [Tech Stack & Concepts](#-tech-stack--java-concepts-used)
- [Room Configuration](#-room-configuration)
- [Setup & How to Run](#️-setup--how-to-run)
- [Screenshots](#-screenshots)
- [Data Persistence](#-data-persistence)
- [Future Enhancements](#-future-enhancements)
- [Author](#-author)

---

## 📌 Problem Statement

College hostels often rely on manual registers or basic spreadsheets to manage room allotments, leading to errors, double bookings, and difficulty in tracking student details. This system provides a structured, menu-driven Java application to automate these tasks efficiently.

Key problems solved:
- Eliminates double-booking with duplicate student ID validation
- Instant student search by ID or name — no manual scanning of registers
- Automatic occupancy reports with revenue calculation
- File-based data persistence so records survive application restarts

---

## ✨ Features

| # | Feature | Description |
|---|---|---|
| 1 | **Allot Room** | Assign an available room to a student with full personal details |
| 2 | **Vacate Room** | Check out a student with confirmation prompt and free the room |
| 3 | **View All Rooms** | Display all rooms grouped by floor with type, status, fee, and occupant |
| 4 | **Search Student** | Find a student by exact ID or partial name match |
| 5 | **View Available Rooms** | Filter and list only rooms open for new allotment |
| 6 | **View Occupied Rooms** | List all currently occupied rooms with occupant names |
| 7 | **Generate Report** | Summary with occupancy rate, floor-wise breakdown, and monthly revenue |
| 8 | **Save Data** | Persist all allotment data to a local text file |
| 9 | **Load Data** | Restore previously saved data when restarting the application |

---

## 🏗️ Project Structure

```
HostelSystem/
├── src/
│   ├── Main.java               # Entry point — menu loop and user input handling
│   ├── Student.java            # Student entity class with serialization support
│   ├── Room.java               # Room entity with RoomType and RoomStatus enums
│   └── HostelManager.java      # Core business logic for all 9 operations
├── out/                        # Compiled .class files (auto-generated after build)
├── screenshots/
│   ├── 01_main_menu.png        # Application startup and main menu
│   ├── 02_allot_room.png       # Room allotment with student details
│   ├── 03_view_all_rooms.png   # All rooms grouped by floor
│   ├── 04_search_student.png   # Student search by ID
│   ├── 05_generate_report.png  # Hostel occupancy report
│   └── 06_vacate_and_save.png  # Room vacating and data save
├── hostel_data.txt             # Auto-generated data file (created after Save)
└── README.md                   # This file
```

---

## 🛠️ Tech Stack & Java Concepts Used

| Concept | Where Applied |
|---|---|
| **OOP — Encapsulation** | Private fields + getters in `Student` and `Room` |
| **OOP — Abstraction** | `HostelManager` hides all logic behind public methods |
| **OOP — toString()** | Custom display formatting in `Room` and `Student` |
| **Enums** | `RoomType` (SINGLE/DOUBLE/TRIPLE), `RoomStatus` (AVAILABLE/OCCUPIED/MAINTENANCE) |
| **ArrayList** | Stores all `Room` objects in `HostelManager` |
| **Stream API** | Filtering, counting, aggregating room data (`filter`, `count`, `mapToDouble`, `sum`) |
| **File I/O** | `FileWriter`, `PrintWriter` for save; `BufferedReader`, `FileReader` for load |
| **Exception Handling** | try-catch on all I/O; `hasNextInt()` for input validation |
| **Java Date/Time API** | `LocalDate.now()` to record allotment date automatically |
| **Custom Serialization** | `toFileString()` / `fromFileString()` for file persistence without libraries |

---

## 🏠 Room Configuration

The hostel is pre-configured with **15 rooms across 3 floors**:

| Floor | Room Numbers | Room Types | Fee Range |
|---|---|---|---|
| Floor 1 | 101–105 | 3 Single, 2 Double | Rs. 2,000 – Rs. 3,000 |
| Floor 2 | 201–205 | 2 Double, 2 Triple, 1 Single | Rs. 1,500 – Rs. 3,500 |
| Floor 3 | 301–305 | 2 Single, 2 Double, 1 Triple | Rs. 1,800 – Rs. 4,000 |

| Room Type | Fee / Month |
|---|---|
| Single | Rs. 3,000 – Rs. 4,000 |
| Double | Rs. 2,000 – Rs. 2,500 |
| Triple | Rs. 1,500 – Rs. 1,800 |

---

## ⚙️ Setup & How to Run

### Prerequisites
- Java JDK 8 or higher installed
- A terminal / command prompt / VS Code with Java Extension Pack

### Step 1 — Clone the Repository
```bash
git clone https://github.com/Naman-mehta22/Hostel-Allotment-System/blob/main/README.md
cd hostel-room-allotment-system
```

### Step 2 — Compile All Java Files
```bash
mkdir out
javac -d out src/*.java
```

On **Windows** if wildcard does not work:
```bash
javac -d out src/Student.java src/Room.java src/HostelManager.java src/Main.java
```

✅ No output means compilation succeeded.

### Step 3 — Run the Application
```bash
java -cp out Main
```

### Running in VS Code (Easiest)
1. Install **Extension Pack for Java** from the VS Code marketplace
2. Open the `HostelSystem/` folder in VS Code
3. Open `Main.java` and click the **▶ Run** button at the top right
4. The integrated terminal compiles and runs everything automatically

---

## 📸 Screenshots

> All screenshots below show the application running in the **VS Code integrated terminal on Windows**.
> To add screenshots to your local clone, create a `screenshots/` folder and place each `.png` inside.

---

### 1. 🖥️ Application Startup — Main Menu

**File:** `screenshots/01_main_menu.png`

When the application is launched using `java -cp out Main`, it displays a formatted welcome banner followed by a numbered main menu. The user navigates the entire system by typing a number (0–9) and pressing Enter. No mouse interaction is required.

![Main Menu](screenshots/01_main_menu.png)

**What this shows:**
- The compile command `javac -d out src/*.java` ran successfully with no errors
- The welcome banner appears with a visual border (===) for clarity
- All 9 feature options are displayed clearly, numbered 1–9
- Option 0 exits the application cleanly
- The `Enter your choice:` prompt waits for user input

---

### 2. 📝 Room Allotment — Capturing Student Details

**File:** `screenshots/02_allot_room.png`

Selecting option `1` launches the room allotment workflow. The system collects student details step by step — Student ID, Name, Course, Year, Contact Number, and Email. It then lists all currently available rooms and prompts the user to select one by room number. The allotment date is automatically recorded using `LocalDate.now()`.

![Allot Room](screenshots/02_allot_room.png)

**What this shows:**
- Sequential prompts collect all required student information
- Available rooms are listed before the user selects — so they can see options first
- Each room row shows: Room No, Type, Floor, Fee (Rs.), Status, and Occupant
- The success confirmation shows the student name, monthly fee, and the auto-recorded allotment date
- The system does not require the admin to manually type the date — it is captured automatically

> **Validation built in:** If the Student ID already exists in the system, the allotment is rejected immediately with an error message. If the selected room is already occupied, allotment is blocked.

---

### 3. 🏢 View All Rooms — Floor-wise Display

**File:** `screenshots/03_view_all_rooms.png`

Option `3` displays all 15 rooms grouped under floor headings. Each row shows the room number, type, floor, monthly fee, current status (AVAILABLE or OCCUPIED), and the occupant's name and student ID for occupied rooms.

![View All Rooms](screenshots/03_view_all_rooms.png)

**What this shows:**
- Rooms are organized under `--- Floor 1 ---`, `--- Floor 2 ---`, `--- Floor 3 ---` headings
- OCCUPIED rooms display the occupant name and student ID
- AVAILABLE rooms show `---` in the Occupant column
- Multiple students allotted across different floors confirm the system handles multi-record data correctly
- The consistent column-aligned format makes it easy to scan any room's status at a glance

---

### 4. 🔍 Search Student — by ID or Name

**File:** `screenshots/04_search_student.png`

Option `4` supports two search modes: by Student ID (exact match) or by Student Name (partial match). The search result displays the student's full profile — all 7 data fields — alongside their room details including floor, room type, and monthly fee.

![Search Student](screenshots/04_search_student.png)

**What this shows:**
- The system offers clear mode selection before prompting for search input
- Search by Student ID returns a single exact match with complete student profile
- Both student information and room details are displayed together — no separate lookup needed
- The display includes: Student ID, Name, Course, Year, Contact, Email, Allotment Date, Room Number, Room Type, Floor, and Monthly Fee
- If no student is found, the message "No student record found." is displayed gracefully

---

### 5. 📊 Generate Hostel Report

**File:** `screenshots/05_generate_report.png`

Option `7` generates a complete hostel status report. The report displays the current date, total/available/occupied room counts, occupancy percentage, room type breakdown (Single/Double/Triple), total monthly revenue from all occupied rooms, and a floor-wise occupancy summary.

![Generate Report](screenshots/05_generate_report.png)

**What this shows:**
- Report date is auto-populated — the admin does not type it
- Occupancy Rate (%) is computed dynamically: `(occupied / total) × 100`
- Monthly Revenue is the sum of fees from all currently occupied rooms — varies by room type
- Floor-wise summary (e.g., `Floor 1 : 2/5 occupied`) helps identify availability per floor
- All figures are computed using the Java Stream API — no hardcoded values
- The formatted border (`========`) makes the output clean and visually organized

---

### 6. 🚪 Vacate Room, Save Data, and Exit

**File:** `screenshots/06_vacate_and_save.png`

This screenshot demonstrates three operations in sequence: room vacating (Option 2), saving data to file (Option 8), and clean application exit (Option 0).

- **Vacate (Option 2):** The system shows the current occupant's full details and asks for `yes/no` confirmation before checking out.
- **Save (Option 8):** All current room and student data is written to `hostel_data.txt`.
- **Exit (Option 0):** A farewell message is printed and the program ends cleanly.

![Vacate and Save](screenshots/06_vacate_and_save.png)

**What this shows:**
- The vacate workflow shows full occupant details before asking for confirmation — prevents accidental checkouts
- The `yes/no` confirmation is a safety step to protect against data loss
- After vacating, the room is immediately marked as AVAILABLE
- The save confirmation message shows the exact filename (`hostel_data.txt`)
- The exit message confirms a professional and clean application shutdown
- The terminal prompt returns after exit — confirming no crash or hanging thread

---

## 💾 Data Persistence

- Use **Option 8** to save all room and student data to `hostel_data.txt`
- Use **Option 9** to reload saved data on any future application restart
- If the file is missing or corrupted, the system falls back to default room data safely
- Data uses pipe (`|`) as room-level separator and comma (`,`) for student fields

**Example of a saved data line (occupied room):**
```
101|SINGLE|1|3000.0|OCCUPIED|VIT2024001,Rahul Sharma,B.Tech CSE,2,9876543210,rahul@vit.ac.in,2024-04-01
```

**Example of a saved data line (vacant room):**
```
102|SINGLE|1|3000.0|AVAILABLE|NONE
```

---

## 🔮 Future Enhancements

- SQLite / MySQL database integration via JDBC for robust persistence
- Java Swing GUI with input forms and room status tables
- Fee payment tracking and monthly dues report per student
- Admin login and role-based access control
- Export hostel report to PDF using Apache PDFBox
- Multi-hostel support for managing multiple buildings
- Complaint management module for maintenance requests
- Email confirmation via JavaMail API on allotment

---

## 👨‍💻 Author

**Kanishka Rajput**  
Registration No: 25BAI11215 
Course: Programming in Java  

---

## 📄 License

This project is developed for academic purposes as part of the BYOP Capstone Project for the Programming in Java course.
