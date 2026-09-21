# Oracle Pluggable Database (PDB) Management — Individual Assignment II

**Course:** Database Development with PL/SQL (INSY 8311)  
**Instructor:** Eric Maniraguha  
**Student Name:** Michel GIRINSHUTI  
**Student ID:** 29055  
**Submission Date:** September 2026

---

## 1. Overview of Tasks

This assignment demonstrates practical skills in Oracle Multitenant Architecture, including:
- Creating and managing Pluggable Databases (PDBs)
- Creating users inside a PDB
- Using Oracle Enterprise Manager Database Express (EM Express)
- Professional documentation on GitHub

---

## 2. Oracle Environment Used

| Component | Details |
|---|---|
| Oracle Version | Oracle AI Database 26ai Free |
| Oracle Home | OraDB23Home1 |
| Container DB (CDB) | FREE |
| Operating System | Windows |
| Tools Used | SQL*Plus, SQL Developer |

---

## 3. Task Explanations

### Task 1 — Creating a New PDB
I created a PDB named `mi_pdb_29055` using the `CREATE PLUGGABLE DATABASE` command. I then opened it in READ WRITE mode and verified its state using `v$pdbs`. Finally, I created a local user `michel_plsqlauca_29055` inside the PDB with DBA privileges.

**Evidence:** See `screenshots/pdb_creation/`

### Task 2 — Creating and Deleting a PDB
I created a temporary PDB named `mi_to_delete_pdb_29055`, verified its existence, then deleted it completely using `DROP PLUGGABLE DATABASE ... INCLUDING DATAFILES`. I confirmed its removal by querying `v$pdbs`.

**Evidence:** See `screenshots/pdb_deletion/`

### Task 3 — Oracle Enterprise Manager (OEM)
I configured EM Express HTTPS ports and accessed the OEM dashboard via my browser. The dashboard reflected my Oracle environment, and my PDB creation task was visible. My username was displayed in the top-right corner.

**Evidence:** See `screenshots/oem_dashboard/`

---

## 4. Challenges Faced and Solutions

- **Challenge 1:** [The `FILE_NAME_CONVERT` paths were initially incorrect for my Oracle 23ai Free installation.]  
  **Solution:** [I used `SHOW PARAMETER db_create_file_dest` to identify the correct datafile location and adjusted the paths accordingly.]

- **Challenge 2:**I initially tried to create the user in CDB$ROOT instead of inside the PDB.]  
  **Solution:** [I learned that local users must be created after switching to the PDB container using `ALTER SESSION SET CONTAINER = mi_pdb_29055`.]

---

## 5. Integrity Statement

I, **Michel GIRINSHUTI**, declare that this assignment is entirely my own work. I performed all commands myself, captured my own screenshots, and wrote this documentation independently. I did not copy from classmates, reuse screenshots, or use AI tools to generate my solutions.

---

## 6. Submission Details

- **Repository Link:** [Your GitHub URL]
- **PDB Name Created:** `mi_pdb_29055`
- **Issues Encountered:** [Yes/No — brief note if Yes]
