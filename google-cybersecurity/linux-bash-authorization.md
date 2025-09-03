---
layout: default
title: Linux commands in the Bash shell – Manage Authorization
---

In this lab, I practiced using Linux commands to manage file and directory permissions. The goal was to check and adjust authorization settings in the `/home/researcher2/projects` directory, making sure only the right users and groups had access.

### Task 1: Check file and directory details
Navigated to the `projects` directory, listed all files with their permissions, and verified ownership.  
**Group owner of files:** `research_team`  
**Hidden file detected:** `.project_x.txt`  

![Task 1: File and directory details](./images/linux-task-1.jpeg)

---

### Task 2: Change file permissions
Checked for files allowing "other" users to write and corrected permissions. Also restricted group access on sensitive files.  
**Files fixed:** `project_k.txt` (removed write for others), `project_m.txt` (removed read for group).

![Task 2: Corrected file permissions](./images/linux-task-2.jpeg)

---

### Task 3: Change permissions on a hidden file
Checked the hidden file `.project_x.txt`, removed write permissions for others, ensured the group could read it, and the user retained read access.

![Task 3: Hidden file permissions](./images/linux-task-3.jpeg)

---

### Task 4: Change directory permissions
Updated the `drafts` directory permissions so only `researcher2` can access it, removing execute rights for the group.  

![Task 4: Directory permissions](./images/linux-task-4.jpeg)


