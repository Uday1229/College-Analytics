# 🎓 College Analytics Dashboard | Power BI

![Overview](screenshots/01_overview.png)

## Description

An interactive Power BI dashboard for engineering colleges. It brings **student attendance, academic performance and library usage** into one place, so principals, HODs and faculty can catch problems early and act on them before results day.

Users can filter by **Branch (CSE, IT, ECE, EEE) → Year → Section → Student**, and drill down from the whole college to one student in a few clicks.

## Business problem

Colleges collect data every day, but very little of it is used to make decisions:

- **Scattered data:** attendance lives in the ERP or biometric system, marks in faculty Excel sheets, and library records in a separate system.
- **Late reports:** attendance shortage lists are compiled by hand at month-end, after students have already slipped below the 75% rule.
- **Hidden academic risks:** a subject with a falling pass rate, or a section with low attendance, goes unnoticed until results come out.
- **Slow mentoring:** a mentor has to collect a student's full record from several places before every parent meeting.
- **Heavy accreditation work:** NAAC and NBA evidence is assembled by hand, over weeks.

**This dashboard solves it** by combining every source into one model that refreshes automatically. Each role sees the numbers it needs, when it needs them:

| Role | Sees |
|---|---|
| Principal | Whole college: attendance, pass %, backlogs and library reach by branch and year |
| HOD | Own branch only: section-wise shortage lists, weak subjects, faculty trends |
| Faculty / Mentor | Only the students they teach, plus a full profile of any student in one click |

## Tech stack

| Layer | Tools |
|---|---|
| Visualisation | Power BI Desktop, Power BI Service |
| Data preparation | Power Query (M) |
| Modelling | Star schema with dimension and fact tables |
| Calculations | DAX: time intelligence, dynamic banding, ranking |
| Security | Dynamic Row-Level Security (RLS) |

## Data source

The demo runs on a **synthetic dataset** modelled on a JNTUH-affiliated engineering college (R22 regulation). It has about 1,600 students across 4 branches and 4 years, with sections A–C, covering one full semester plus past results.

| Data | What it contains |
|---|---|
| Students | Roll number, branch, year, section, batch, admission category, residence, mentor |
| Subjects and faculty | Subjects by branch and semester with credits; faculty by department and designation |
| Attendance | Period-wise attendance per student, subject and day (~300,000 records) |
| Exams | Mid-exam marks for the current semester; internal, external, grades and backlogs for past semesters |
| Library | Gate entry and exit logs, book issues, returns, overdues and fines |
| Calendar | Working days, holidays, exam days |

> All names, roll numbers and figures are fictional and represent no real institution or person.

**In a live deployment**, the same model connects to the college's existing systems: Excel files on OneDrive or SharePoint, ERP databases (MySQL or SQL Server), biometric attendance systems, and Koha library software. It refreshes on a schedule.

## Features

- **Overview page:** headline KPIs, attendance by class against the 75% line, branch × year heat map
- **Attendance tracking:** daily and weekly trends, subject-wise attendance, and a shortage list flagging each student as *Eligible*, *Condonation (65–75%)* or *Detention Risk (<65%)*
- **Academic performance:** pass %, all-clear %, semester GPA, pending backlogs, Mid-exam results, and pass-rate trends across batches
- **Library analytics:** visits, active users, exam-time peaks, most-issued books, overdue returns and fines
- **Faculty insights:** attendance and exam outcomes by faculty and subject
- **Student 360°:** right-click any student to see their attendance trend, grades, SGPA trend, backlogs and library history
- **Role-based security:** one report, and each login sees only its own branch or students
- **Exportable:** any page exports to PDF for NAAC/NBA documentation and parent meetings

| | |
|---|---|
| ![Attendance](screenshots/02_attendance.png) | ![Academics](screenshots/03_academics.png) |
| ![Library](screenshots/04_library.png) | ![Student 360](screenshots/06_student360.png) |

## Highlights

Insights the dashboard surfaces from the demo data:

- 📉 **One section's attendance runs about 6 points below its parallel sections.** It comes down to two subjects taught by the same faculty member.
- ⚠️ **A core ECE subject's pass rate fell from 71% to 66% over two batches**, and the current batch's Mid-1 scores are the lowest in their semester.
- 📚 **Library visits double in the week before Mid exams**, and regular library users score higher GPAs.
- 🎯 **Final-year attendance drops once placement season begins.** It is an early signal for the training and placement cell.
- 🚨 **276 of 1,585 students are below 75% attendance, and 97 are at detention risk**, each identified with weeks still left in the semester.

## Contact

Want this for your institution? I build custom dashboards on your existing data, whether it's in Excel sheets, your ERP or your library system.

📧 email- · 💼udaykumar.koram@gmail.com
