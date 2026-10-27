# Robotics Equipment Maintenance Log

**Course:** CS-1281 – Python Programming Lab  
**Branch:** Mechanical and Smart Manufacturing  
**Institution:** Veer Surendra Sai University of Technology (VSSUT), Burla  
**Work Order:** 09 – The Data Layer


**Peer Name** Shreeya Routray,2502190005

## 📌 Project Overview

The Robotics Equipment Maintenance Log is a Python-based project designed to record and analyze maintenance activities for robotics equipment, including motors, batteries, sensors, wheels, and encoders.

The program reads maintenance records from a text file, validates the input, summarizes equipment-wise maintenance frequency and downtime, and generates a dated report. Invalid records are documented with their line numbers and reasons instead of being silently discarded.

## 🎯 Objectives

- Read structured maintenance data from a text file.
- Validate records using regular expressions and data checks.
- Handle malformed and out-of-range records safely.
- Summarize maintenance frequency and total downtime for each equipment type.
- Generate formatted, timestamped reports.
- Maintain a record of rejected input lines for reliable data processing.

## 🛠️ Technologies Used

- Python 3
- Regular Expressions (`re`)
- File Handling
- `os` and `datetime` modules
- `collections.Counter`

## 📂 Project Structure

```text
project/
├── README.md
├── main.py
├── datalayer.py
├── data/
│   └── sample.txt
└── reports/
    └── report_YYYY-MM-DD_HHMM.txt
```

## 📄 Input Format

Each nonblank line contains five pipe-separated fields:

```text
equipment_id|equipment_name|date|issue|downtime_hours
```

**Example:**

```text
RB01|DC_Motor|2026-09-01|Overheating|2
```

### Data Validation

- Leading and trailing spaces around fields are removed.
- Records must contain exactly five fields.
- Dates must follow the `YYYY-MM-DD` format and be valid calendar dates.
- Downtime must be a numeric value between 0 and 100 hours.
- Invalid records are skipped and listed with their line numbers and error reasons.
- A missing input file raises a `FileNotFoundError`, which is handled by the main program.

## ⚙️ How to Run

### Prerequisites
Install Python 3 on your system.

### Steps

1. Clone or download this repository.
2. Open a terminal in the project directory.
3. Run the program:

```bash
python main.py
```

The program reads `data/sample.txt` and saves a new report in the `reports/` directory.

You can also run the notebook cells in Google Colab.

## 📊 Output

The generated report contains:

- Report generation date and time.
- Source file path.
- Number of valid records.
- Number of rejected records.
- Equipment-wise maintenance counts and total downtime.
- A problems section listing each rejected line and the reason for rejection.

## 🧪 Testing

The sample dataset includes at least 15 manually prepared records and deliberately imperfect entries to test the validation layer.

| Test case | Expected behavior |
|---|---|
| Valid record | Accepted |
| Extra spaces around fields | Recovered after trimming |
| Missing field | Rejected with a reason |
| Downtime above 100 hours | Rejected with a reason |
| Missing input file | Clear error message |

## 📈 Future Improvements

- Add equipment maintenance history visualization.
- Identify equipment requiring preventive maintenance.
- Export reports to CSV.
- Add a simple user interface for entering maintenance records.

## 👩‍💻 Contributors

- Ayushi Srivastava
- Project Partner: Add partner name

## 📜 Academic Context

Developed as part of the CS-1281 Python Programming Lab, Work Order 09: The Data Layer, at VSSUT Burla.
