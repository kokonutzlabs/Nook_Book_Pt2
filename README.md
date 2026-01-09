# Nook_Book_Pt2 interaction logging and system visibility

## Overview
Nook_Book is a small, controlled web application designed to explore how HTML, PHP, and SQL interact within a basic system environment. While visually themed around *Animal Crossing* and structured like a social media profile, the project’s primary purpose is to serve as a **learning platform for digital forensics, system behavior analysis, and data integrity concepts**.

Version 2 builds upon the baseline established in Version 1 by introducing **interaction logging and system visibility**, while intentionally excluding security controls.

---

## Version 2 Purpose
The goals of Version 2 are to:

- Introduce system-level logging
- Improve visibility into user and system behavior
- Record contextual metadata alongside interactions
- Preserve raw, unprotected logs for forensic comparison
- Maintain uninterrupted user experience

This version establishes a **logged but untrusted system state**, which will be analyzed in future versions.

---

## System Scope

### Included
- Static HTML profile page
- User interaction via HTML forms
- Backend processing using PHP
- SQL database storage
- Local execution using XAMPP
- Interaction logging
- Page-view logging
- Timestamped system events
- IP address and user-agent capture

### Excluded (Intentional)
- User authentication or sessions
- Access controls
- Input sanitization beyond basic handling
- Log integrity protection
- Encryption or hashing
- Audit enforcement

These exclusions are deliberate and documented for educational purposes.

---

## File Structure

### HTML
- **nook-book.html**  
  Displays a single villager profile and allows users to submit reactions, votes, or comments.

### PHP
- **nook-book.php**  
  Processes form submissions and displays confirmation messages.

- **nook-book-db1.php**  
  Creates the SQL database.

- **nook-book-conn1.php**  
  Establishes the database connection.

- **nook-book-setup1.php**  
  Creates database tables for interactions and logs.

- **nook-book-forms1.php**  
  Captures user input and inserts interaction records.

- **nook-book-log1.php** *(New in Version 2)*  
  Records system events such as form submissions and page views, including metadata.

---

## Data Handling

### Interaction Data
- Each form submission creates a new record
- No user identification or authentication
- Records are never edited or deleted
- Data represents raw interaction input

### Logging Data
- Each interaction generates a corresponding log entry
- Logs capture:
  - Event type
  - Page name
  - Raw submitted data
  - IP address
  - User agent
  - Timestamp
- Logs are stored in a separate table
- Logs are not protected from modification or deletion

This separation supports future forensic comparison between interaction data and system logs.

---

## Environment & Tools

### Programs
- Visual Studio Code
- XAMPP
- phpMyAdmin

### Languages
- HTML
- CSS
- PHP
- SQL

---

## How to Run the Project

### Option 1: Frontend Only
The project can be viewed via the Neocities page listed in the repository.  
Backend functionality is unavailable due to hosting limitations.

### Option 2: Full Local Setup (Recommended)
1. Install XAMPP
2. Place all project files in a folder inside the `htdocs` directory
3. Start Apache and MySQL via the XAMPP control panel
4. Navigate to:  
   `http://localhost/your-folder-name`
5. Open `nook-book.html`

---

## Forensic Relevance
Version 2 enables:

- Timeline reconstruction
- Correlation between interactions and logs
- Identification of missing or altered records
- Analysis of abnormal system behavior

The system intentionally mirrors early-stage applications with limited monitoring and protection.

---

## Planned Future Versions
- **Version 3:** Simulated incidents and data integrity violations
- **Version 4:** Forensic investigation and reporting

---

## Notes
- Additional HTML content will be added in future updates
- PHP data handling will be refined without disrupting user experience
- A separate repository has been created for continued development

---

## Disclaimer
This project is for **educational purposes only**.  
All security weaknesses are intentional and documented as part of the learning process.

