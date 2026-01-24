# Digital Forensic Analysis of Warehouse Shipment Records

## Overview

This project simulates a **digital forensic investigation** of warehouse shipment data, focusing on the detection and reconstruction of **tampered, incomplete, or non-compliant shipment records**.  

It is designed to mirror real-world scenarios in logistics and warehouse environments, including **weight manipulation, timestamp alteration, missing audit trails, and SOP/GMP violations**.

The project leverages **Python** and **SQLite** to perform reverse engineering of shipment records and generate forensic findings suitable for audits or internal investigations.

---

## Objectives

- Simulate a realistic warehouse shipment database
- Introduce intentional data manipulation and integrity failures
- Perform forensic analysis using Python
- Detect anomalies and SOP/GMP violations
- Reconstruct event timelines from incomplete or altered data
- Produce structured forensic findings

---

## Technical Scope

**Domain:** Warehouse Operations, Logistics, Digital Forensics  
**Focus Areas:**
- Shipment ticketing
- Scalehouse weight records
- Operator accountability
- SOP and GMP compliance
- Data integrity and auditability

---

## Architecture

### Database
- **SQLite** relational database
- Structured to resemble warehouse shipment systems

### Core Tables
- `shipments`
- `weigh_ins`
- `weigh_outs`
- `operators`
- `audit_logs`

### Data Characteristics
- Timestamped transactions
- Operator-linked actions
- Calculated and stored net weights
- Audit records with intentional gaps

---

## Simulated Forensic Scenarios

The dataset includes intentional anomalies such as:

- Modified shipment weights after approval
- Gross/Tare mismatches resulting in incorrect net weights
- Duplicate ticket numbers
- Timestamp manipulation outside authorized shift hours
- Missing or altered audit log entries
- Unauthorized operator activity

These scenarios replicate **internal fraud, human error, or system misuse** commonly encountered in warehouse environments.

---

## Forensic Methodology

The Python forensic tool performs the following steps:

1. **Data Ingestion**
   - Connects to the SQLite database
   - Extracts shipment, weight, operator, and audit data

2. **Integrity Validation**
   - Recalculates net weights from gross and tare values
   - Compares calculated values to stored records
   - Flags discrepancies

3. **Timeline Reconstruction**
   - Orders events chronologically
   - Identifies gaps or inconsistencies in timestamps
   - Detects post-approval modifications

4. **Compliance Analysis**
   - Verifies operator authorization
   - Checks adherence to SOP-required approvals
   - Identifies GMP-relevant violations

5. **Anomaly Detection**
   - Flags suspicious or invalid records
   - Associates anomalies with operators and timestamps

---

## Tools & Technologies

- **Python 3**
- **SQLite**
- `sqlite3`
- `pandas`
- `datetime`
- `hashlib` (for record integrity checks)

---

## Output

The tool generates:
- Console-based forensic findings
- Structured CSV reports of flagged records
- Evidence summaries suitable for audits or investigations

Example findings include:
- Weight inconsistencies
- Unauthorized record modifications
- Missing audit trail entries
- SOP violations by shipment or operator

---

## Use Cases

- Internal warehouse investigations
- Compliance and audit preparation
- Digital forensics training
- Logistics data integrity validation

---

## Limitations

- Dataset is simulated and does not contain real operational data
- No real-time monitoring (batch analysis only)
- Focused on internal data integrity rather than network forensics

---

## Future Enhancements

- PDF forensic report generation
- Role-based access simulation
- Automated SOP rule configuration
- Visualization of shipment timelines
- Hash-based chain-of-custody tracking

---

## Author Background

The project is informed by **five years of experience in scalehouse operations, shipment ticketing, and warehouse logistics**, with applied knowledge of **GMP and SOP-controlled environments**.

---

## Disclaimer

This project is for educational and demonstration purposes only.  
All data and scenarios are fictional.

