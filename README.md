 LakeView-Attendance-Tracker-
 Student Attendance Tracker & Audit System (Excel)

An Excel workbook that lets a university record class attendance, monitor students at risk, manage absence and leave requests, and audit the quality of the attendance data itself. It is built entirely with Excel formulas, data validation, conditional formatting and charts, with no macros, so it runs on any machine with Excel.

Note: All names, emails, phone numbers and the institution ("Lakeview University") are fictional and exist only to demonstrate the system.

The Problem
Many institutions still track attendance on paper registers or loose spreadsheets. This causes recurring problems:

- Slow reporting. Counting presents and absences per student by hand takes hours, so at-risk students are found too late.
- Inconsistent rules. Is "Late" counted as attended? What about "Excused"? Different lecturers apply different rules.
- Unreliable data. Duplicate entries, wrong dates, a student marked in two classes at the same time, and registers filled in days after the lesson all go unnoticed.
- No accountability. There is no record of who entered a mark, when, or how it was verified.
- Leave requests disconnected from the register.An absence is approved on paper, but the register still says "Absent".

 The Solution
A connected, multi-sheet workbook where staff only type into a few input columns and everything else is calculated automatically:

- Attendance is entered once and flows into student summaries, course statistics, a dashboard and printable student reports.
- Attendance rules (required %, at-risk threshold, whether Late/Excused count) live in **one Settings sheet**, so changing a rule updates the whole workbook.
- A dedicated Audit & Review sheet checks the data for suspicious entries and reviews lecturers' registers.
- Absence & Leave requests are cross-checked against what the attendance register actually shows.

 Workbook Structure (8 sheets)

Students- Student register (ID, programme, department, year, semester, contacts). Auto-calculates sessions, present, absent, late, excused, attendance % and standing (Good / Warning / At Risk) for every student. 
Attendance- The main data-entry sheet. One row per student per class. Auto-fills the student name, course name and lecturer from the ID/code, calculates the week, and runs integrity checks on every row. 
Timetable & Courses -  Course catalogue with lecturer, classroom, day and time. Shows average attendance and sessions recorded per course. 
Reports & Dashboard - Management view: KPI cards, a course filter, 4 charts, a "lowest 5 attendance" watch list and a student lookup. 
Student Report- A printable one-page report for any student chosen from a dropdown, with a course breakdown, recent absences/late arrivals, leave history and signature lines. 
Audit & Review- Flags time clashes, duplicates, late entries and unusual lecturer registers. Includes 2 charts. 
Absence & Leave - Leave request log with reason, supporting document reference and approval status, cross-checked against the attendance sheet. 
Settings- Institution details, attendance rules, dropdown lists, authorised staff and their responsibilities. 

 How It Works

Settings (rules + lists)
        |
        v
Students + Timetable  --->  Attendance (daily entry)  --->  Absence & Leave
                                   |
          +------------------------+------------------------+
          v                        v                        v
 Reports & Dashboard        Student Report          Audit & Review


1. Setup: the Registrar sets the semester dates, the required attendance % and the dropdown lists in `Settings`.
2. Register: the Records Officer adds students and courses.
3. Record: after each class, the lecturer adds one row per student in `Attendance` (ID, course code, date, time, status, who recorded it, date recorded, verification method). Dropdowns prevent typing mistakes.
4. Calculate: the workbook automatically updates each student's attendance %, standing, course averages, dashboard KPIs and charts.
5. Review:the Registrar checks the dashboard weekly, follows up on At Risk students, and uses `Audit & Review` to investigate flagged entries.

Attendance rules (configurable in Settings)

- Attendance % = (Present + Late if counted + Excused if counted) / total sessions
- Good: at or above the required % (default 75%)
- Warning: between the at-risk threshold and the required %
- At Risk: below the at-risk threshold (default 60%)


Key Excel Skills Demonstrated

- Lookup and reference:`INDEX` / `MATCH` for auto-filled names, courses and lecturers
- Conditional counting: `COUNTIFS`, `SUMPRODUCT`, `AVERAGEIFS` for per-student, per-course and per-lecturer statistics
- Ranking and dynamic lists: `SMALL` / `LARGE` with helper columns to build the "lowest 5" watch list and the flagged-entries list without any manual sorting
- Data validation: dropdown lists driven by 11 named ranges, plus date, time and whole-number rules
- Conditional formatting: colour-coded status, standing and review flags
- Dashboard design: KPI cards, doughnut, line and bar charts, and a course filter using a wildcard (`*`) for "All Courses"
- Dynamic text: headers and rule descriptions that update from the Settings values
- System design: input vs calculated columns, a single settings sheet, role-based responsibilities, and an audit layer

 Example Output (with the demo data)

With 25 students, 10 courses and 512 attendance records, the dashboard reports:

- Overall attendance: 90.4%(Present 404, Absent 49, Late 43, Excused 16)
- Students flagged At Risk: 1, with a watch list of the five lowest attendance rates
- Pending leave requests: 4
- Audit sheet: 4 time clashes and **31** late entries flagged, and one lecturer register flagged as "unusually high"


How to Use

1. Download `My_Attendance_tracker_project.xlsx` and open it in Microsoft Excel.
2. Go to Settings and enter your institution name, semester dates and attendance rules.
3. Replace the demo data in Students, Timetable & Courses and Attendance with your own (type only in the blue input columns; teal columns are formulas).
4. Open Reports & Dashboard to view results. Use the course dropdown to filter.
5. Pick a student ID in Student Report to print an individual report.

Capacity: 100 students, 995 attendance records, 500 leave requests, 20 courses and 20 staff.

Limitations and Future Improvements

- Built for a single semester; archiving past semesters would need a copy of the workbook.
- Several formulas scan the full attendance range, so very large datasets may recalculate slowly. A Power Query or database version would suit larger institutions.
- Sheet protection could be added so users cannot overwrite formula columns.
- Planned ideas: automatic email alerts for At Risk students (Power Automate), QR-code check-in, and a Power BI version of the dashboard.


Author

Masereka Benet
Software Engineering and Education student | Building bridges between education and technology

"Feel free to open an issue or get in touch with feedback."
