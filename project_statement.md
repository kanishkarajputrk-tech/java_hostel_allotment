# Project Statement

## Hostel Room Allotment System

### The Problem
Managing hostel accommodations in academic institutions often relies on manual paper registers or basic spreadsheets. This creates several administrative challenges. Handwritten logs are easy to misread, leading to name and room number errors. Without automated validation, the same student can accidentally end up assigned to multiple rooms. Wardens spend unnecessary time searching through pages to look up basic student details. Physical registers are also vulnerable to being misplaced, damaged, or destroyed over time. Furthermore, calculating monthly revenue and occupancy statistics by hand is slow and prone to errors.

### The Solution
The Hostel Room Allotment System is a console-based Java application built to digitize and streamline hostel administration. By replacing paper logbooks with structured digital records and file storage, the application provides a reliable and fast solution for managing room check-ins and check-outs.

### Key Objectives
The application simplifies room allotments and vacating for administrative staff. It enforces automatic validation checks to prevent duplicate student IDs and avoid double-booking occupied rooms. Staff can search for student records instantly using a student ID or name. The system automatically calculates overall occupancy rates, floor-by-floor availability, and monthly revenue using Java Streams. All active records are persisted locally to a text file named hostel_data.txt so data is retained across application restarts.

### System Scope
The application is configured to manage 15 rooms distributed across 3 floors. It supports Single, Double, and Triple occupancy room types with corresponding fee structures. The system records essential student details including Student ID, Name, Course, Year, Phone Number, Email, and Allotment Date.