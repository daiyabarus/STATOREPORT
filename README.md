# STATOREPORT - Network Stability Report Generator

[![Version](https://img.shields.io/badge/version-1.0.2-blue.svg)](https://github.com/yourusername/statoreport)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-orange.svg)](LICENSE)

**STATOREPORT** is a powerful network stability analysis tool designed for telecommunications professionals to process and analyze LTE (4G) and GSM (2G) network performance data. It generates comprehensive Excel reports with KPI analysis, visualizations, and tower-level summaries.

**✨ No Python Installation Required** - Ready to use executable application!

---

## 📋 Table of Contents

- [Features](#features)
- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Quick Start Guide](#quick-start-guide)
- [Detailed Usage](#detailed-usage)
- [Input File Formats](#input-file-formats)
- [Understanding the Output](#understanding-the-output)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)

---

## ✨ Features

### Core Capabilities
- ✅ **Standalone Application** - No Python or dependencies required
- ✅ **Dual Technology Support** - Process both LTE (4G) and GSM (2G) network data simultaneously
- ✅ **Automated KPI Analysis** - 16 pre-configured KPIs with automatic PASS/FAIL evaluation
- ✅ **Tower-Level Aggregation** - Consolidates cell-level data into tower summaries
- ✅ **Visual Analytics** - Generates 16 charts per tower showing hourly KPI trends
- ✅ **Interactive Navigation** - Index sheet with hyperlinks to all tower reports
- ✅ **Multi-Sheet Reports** - Organized data in multiple Excel sheets for easy analysis
- ✅ **Real-time Progress** - Live progress bar and elapsed time display
- ✅ **Dark Theme UI** - Modern, easy-on-the-eyes interface

### Key Performance Indicators (KPIs)

#### LTE (4G) KPIs
| KPI Name | Type | Target | Unit |
|----------|------|--------|------|
| Availability | WD | ≥ 99% | % |
| Total Payload | WD | > 0 | GByte |
| Volte Traffic | WD | > 0 | Erl |
| Session Setup Success Rate | BH | ≥ 99% | % |
| Volte CSSR | BH | ≥ 99% | % |
| Erab Drop | BH | < 2% | % |
| RRC User | BH | > 0 | - |
| DL User Throughput | BH | ≥ 3 | Mbps |
| UL User Throughput | BH | ≥ 0.5 | Mbps |
| DL Cell Throughput | BH | > 0 | Mbps |
| UL Cell Throughput | BH | > 0 | Mbps |

#### GSM (2G) KPIs
| KPI Name | Type | Target | Unit |
|----------|------|--------|------|
| Radio Network Availability Rate | WD | ≥ 99% | % |
| Call Setup Success Rate | WD | ≥ 98% | % |
| SDCCH Success Rate | WD | ≥ 98% | % |
| Voice Traffic / Erl | WD | > 0 | Erl |
| Perceive Drop Rate | WD | < 5% | % |

*WD = Whole Day (24h aggregation), BH = Busy Hour (peak hour)*

---

## 💻 System Requirements

### Minimum Requirements
- **Operating System**: 
  - Windows 10/11 (64-bit) **[Recommended]**
  - Linux (Ubuntu 18.04+, Debian 10+, CentOS 7+)
- **Processor**: Intel Core i3 or equivalent
- **RAM**: 4 GB minimum (8 GB recommended for large datasets)
- **Disk Space**: 
  - 150 MB for application
  - Additional space for data files and reports
- **Display**: 1366x768 minimum resolution (1920x1080 recommended)

### No Additional Software Required
- ✅ All dependencies are bundled in the executable
- ✅ No Python installation needed
- ✅ No pip packages to install
- ✅ Ready to run immediately after extraction

---

## 🚀 Installation

### Windows Installation

#### Step 1: Download the Application
1. Download `STATOREPORT-v1.0.2-Windows.zip` from the releases page
2. Extract the ZIP file to your desired location (e.g., `C:\Programs\STATOREPORT\`)

#### Step 2: Verify Folder Structure
After extraction, you should see:
```
STATOREPORT/
├── STATOREPORT.exe          ← Main executable
├── assets/
│   ├── template.xlsx        ← Excel template (required)
│   ├── xlsmart.png          ← Logo image
│   └── zte.png              ← Logo image
├── README.md                ← This file
└── LICENSE.txt
```

#### Step 3: Run the Application
**Option A: Double-click**
- Double-click `STATOREPORT.exe` to launch

**Option B: From Command Prompt**
```cmd
cd C:\Programs\STATOREPORT
STATOREPORT.exe
```

#### Step 4: Create Desktop Shortcut (Optional)
1. Right-click on `STATOREPORT.exe`
2. Select "Send to" > "Desktop (create shortcut)"

---

### Linux Installation

#### Step 1: Download and Extract
```bash
# Download the application
wget https://github.com/yourusername/statoreport/releases/download/v1.0.2/STATOREPORT-v1.0.2-Linux.tar.gz

# Extract
tar -xzf STATOREPORT-v1.0.2-Linux.tar.gz

# Navigate to directory
cd STATOREPORT/
```

#### Step 2: Make Executable
```bash
chmod +x STATOREPORT.bin
```

#### Step 3: Run the Application
```bash
./STATOREPORT.bin
```

#### Step 4: Create Application Launcher (Optional)
Create `~/.local/share/applications/statoreport.desktop`:
```ini
[Desktop Entry]
Version=1.0
Type=Application
Name=STATOREPORT
Comment=Network Stability Report Generator
Exec=/path/to/STATOREPORT/STATOREPORT.bin
Icon=/path/to/STATOREPORT/assets/xlsmart.png
Terminal=false
Categories=Office;Utility;
```

---

## 🎯 Quick Start Guide

### 5-Minute Tutorial

#### Step 1: Launch the Application
- **Windows**: Double-click `STATOREPORT.exe`
- **Linux**: Run `./STATOREPORT.bin`

The application window will open with a dark theme interface.

![Application Screenshot](docs/screenshot_main.png)

---

#### Step 2: Select Input Files

##### 2.1 Select CDD File
1. Click **[Browse]** button next to "CDD File (xlsx)"
2. Navigate to your CDD Excel file
3. Select the file and click "Open"
4. The file path will appear in the text box

**Example**: `D:\NetworkData\CDD_Database_2025.xlsx`

##### 2.2 Select LTE CSV Files
1. Click **[Browse]** button next to "LTE CSV Files"
2. Navigate to your LTE performance data folder
3. Select one or more CSV files (use Ctrl+Click for multiple files)
4. Click "Open"
5. All selected file paths will appear in the text box

**Example**:
```
D:\NetworkData\Performance Management-History Query-4G_20251008.csv
D:\NetworkData\Performance Management-History Query-4G_20251009.csv
```

##### 2.3 Select GSM CSV Files
1. Click **[Browse]** button next to "GSM CSV Files"
2. Navigate to your GSM performance data folder
3. Select one or more CSV files
4. Click "Open"

**Note**: If you only have LTE data, you can skip GSM file selection.

---

#### Step 3: Configure Tower List

You have two options for entering tower information:

##### Option A: Manual Input (Recommended for small lists)

1. Ensure **"Manual Input"** radio button is selected
2. In the text area, enter tower configurations in this format:
   ```
   TOWER_ID,ON_AIR_DATETIME
   ```
   
3. **Example**:
   ```
   SUM-AC-STR-0013,10/8/2025 16:00
   SUM-AC-LSK-0068,10/8/2025 16:00
   SUM-ME-BTG-0042,10/9/2025 08:00
   ```

4. Click **[Parse Tower List]** button
5. You should see: `✅ Parsed 3 towers successfully` in the log

##### Option B: Import from File (Recommended for large lists)

1. Create a text file (e.g., `tower_list.txt`) with tower configurations:
   ```
   SUM-AC-STR-0013,10/8/2025 16:00
   SUM-AC-LSK-0068,10/8/2025 16:00
   SUM-ME-BTG-0042,10/9/2025 08:00
   SUM-ME-PST-0015,10/9/2025 10:00
   SUM-AC-MRD-0091,10/10/2025 12:00
   ```

2. Select **"Import from TXT File"** radio button
3. Click **[Browse]** next to "Tower List File (TXT)"
4. Select your text file
5. Click **[Parse Tower List]** button

**Important Notes**:
- Date format: `MM/DD/YYYY HH:MM` or `M/D/YYYY H:MM`
- Each line = one tower
- The tool analyzes 24 hours starting from the specified time
- Blank lines are automatically ignored

---

#### Step 4: Set Output Location

1. Click **[Browse]** button next to "Output File"
2. Choose where to save the report
3. Enter a filename or use the auto-generated name:
   - Default format: `STABILITY_REPORT_YYYYMMDD_HHMMSS.xlsx`
   - Example: `STABILITY_REPORT_20251012_143052.xlsx`
4. Click "Save"

**Recommended location**: 
- Windows: `D:\Reports\` or `C:\Users\YourName\Documents\Reports\`
- Linux: `~/Reports/` or `~/Documents/Reports/`

---

#### Step 5: Process Data

1. Click the **🚀 PROCESS** button
2. **Processing starts immediately**:
   - Button changes to "⏳ Processing... Please wait, do not close the window!"
   - Progress bar shows completion percentage
   - Elapsed timer displays processing time
   - Processing log shows real-time status updates

3. **Typical Processing Stages**:
   ```
   [14:30:52] 🚀 STARTING UNIFIED PROCESSING & EXPORT
   [14:30:52] ⚙️ Initializing processor...
   [14:30:53] ⚙️ Loading CDD data...
   [14:30:54] ⚙️ Processing LTE data...
   [14:31:15] ⚙️ Processing GSM data...
   [14:31:28] ⚙️ Aggregating tower data...
   [14:31:35] ⚙️ Generating reports...
   [14:31:45] ⚙️ Finalizing results...
   [14:31:47] ✅ Processing completed successfully!
   [14:31:47] ⏱️ Total time: 00:00:55.234
   ```

4. **Processing Time Estimates**:
   - 1-5 towers: 30 seconds - 2 minutes
   - 6-10 towers: 2-5 minutes
   - 11-20 towers: 5-10 minutes
   - 21+ towers: 10-20 minutes

5. **After Completion**:
   - Button changes to "✅ COMPLETED" (blue)
   - A popup appears: "Processing completed! Would you like to open the report?"
   - Click **[Yes]** to open the Excel report immediately
   - Click **[No]** to open it later

---

#### Step 6: Review the Results

The application displays a comprehensive summary in the log:

```
============================================================
📊 PROCESSING SUMMARY
============================================================
Total towers: 3
LTE cells: 12
GSM BTS: 8
Cell summary records: 320
============================================================
📈 TOWER STATISTICS
============================================================
Towers PASS: 2
Towers FAIL: 1
Overall Pass Rate: 66.67%
============================================================
⚠️ TOP 5 WORST PERFORMING KPIs
============================================================
  Volte CSSR: 33.3% (2 failures)
  Erab drop: 66.7% (1 failures)
  DL User throughput: 66.7% (1 failures)
  Availability: 100.0% (0 failures)
  Total Payload: 100.0% (0 failures)
============================================================
📄 Tower summary sheets: 3
============================================================
✅ Report saved: D:\Reports\STABILITY_REPORT_20251012_143052.xlsx
============================================================
```

---

## 📖 Detailed Usage

### Application Interface Overview

#### Main Window Sections

**1. Header Section**
- Title: "STABILITY NEWSITE REPORT GENERATOR"
- Elapsed Timer: Shows processing time (HH:MM:SS.mmm)

**2. File Selection Section**
- CDD File browser
- LTE CSV Files browser (multi-select)
- GSM CSV Files browser (multi-select)

**3. Tower Configuration Section**
- Manual input text area
- File import option
- Parse button to validate input

**4. Output Configuration Section**
- Output file path selection
- Auto-generated filename suggestion

**5. Process Control Section**
- Large **🚀 PROCESS** button
- Processing status indicator
- Progress bar (0-100%)

**6. Results Display Section** (Tabs)
- **CELL SUMMARY**: All cells with KPI values and flags
- **LTE RAW AGG**: Aggregated LTE data
- **GSM RAW AGG**: Aggregated GSM data
- **LTE RAW HOURLY**: Hour-by-hour LTE data
- **GSM RAW HOURLY**: Hour-by-hour GSM data

**7. Processing Log Section**
- Real-time processing messages
- Timestamped entries
- Success/error indicators (✅/❌/⚠️)
- Auto-scroll to latest message

---

### Understanding Input Files

#### 1. CDD File (Cell Design Database)

**Purpose**: Contains network element configuration and parameters

**Required format**: Excel (.xlsx) workbook with multiple sheets

**Required sheets**:
- **Sheet for LTE**: Named "CDD LTE", "4G", or similar
  - Starting from row 3 (header in row 2)
- **Sheet for GSM**: Named "CDD 2G", "GSM", or similar
  - Starting from row 2 (header in row 1)

**Critical LTE CDD Columns**:
```
new_cell_name          → Cell identifier (e.g., SUM-AC-STR-0013-1)
new_tower_name         → Tower name (e.g., "Tower Alam Sutera")
cluster_14_july_2025   → Tower/Cluster ID (e.g., SUM-AC-STR-0013)
lat                    → Latitude coordinate
long                   → Longitude coordinate
sector                 → Sector information (e.g., 1, 2, 3)
cell_type              → Cell type (Indoor/Outdoor)
frequencyband          → Frequency band (e.g., 1800, 2100)
...and 30+ other configuration columns
```

**Critical GSM CDD Columns**:
```
new_tower_id           → Tower identifier (e.g., SUM-AC-STR-0013)
new_tower_name         → Tower name
new_site_name          → Site name (matches CSV Site Name)
new_ci                 → Cell ID
bsc_name               → BSC controller name
cluster_14_july_2025   → Cluster/Tower ID
lat, long              → Coordinates
...and 20+ other configuration columns
```

**File Example Location**: `D:\NetworkData\CDD_Database_October_2025.xlsx`

---

#### 2. LTE CSV Files

**Purpose**: Contains LTE/4G performance counter data

**File Naming Convention**: 
- **Must start with**: `Performance Management-History Query-4G`
- Example: `Performance Management-History Query-4G_20251008_160000.csv`

**File Structure**:
```csv
Managed Element,Begin Time,Cell Name,Counter1,Counter2,...
#SUM-AC-STR-0013(eNodeB),2025-10-08 16:00:00,SUM-AC-STR-0013-1,99.5,145.2,...
#SUM-AC-STR-0013(eNodeB),2025-10-08 17:00:00,SUM-AC-STR-0013-1,99.3,152.8,...
```

**Key Columns** (by position):
- **Column 0**: Managed Element (contains Tower ID in format `#TOWER-ID(eNodeB)`)
- **Column 1**: Begin Time (format: `YYYY-MM-DD HH:MM:SS`)
- **Column 2**: Cell Name
- **Column 3+**: Various KPI counters including:
  - Availability metrics
  - Traffic counters (numerator/denominator)
  - Success rate counters
  - Throughput metrics
  - User counts

**Data Requirements**:
- Hourly granularity
- At least 24 hours of data from on-air time
- All counter columns must be present (can be empty/zero)

**Multiple Files**: 
- You can select multiple CSV files covering different time periods
- The tool will automatically combine them
- Ensure no duplicate time periods

**File Size**: Typical file size is 5-50 MB depending on network size

---

#### 3. GSM CSV Files

**Purpose**: Contains GSM/2G performance counter data

**File Naming Convention**: 
- Any CSV file (no specific prefix required)
- Not matching LTE pattern
- Example: `GSM_Performance_20251008.csv`

**File Structure**:
```csv
Site Name,BTS Name,Begin Time,KPI1,KPI2,...
SUM-AC-STR-0013,SUM-AC-STR-0013_001,2025-10-08 16:00:00,99.2,97.5,...
SUM-AC-STR-0013,SUM-AC-STR-0013_002,2025-10-08 16:00:00,98.8,96.9,...
```

**Key Columns**:
- **Site Name**: Must match CDD `new_site_name`
- **BTS Name**: Base Transceiver Station name
- **Begin Time**: Timestamp
- **KPI Columns**:
  - Radio Network Availability Rate
  - Call Setup Success Rate (with numerator/denominator)
  - SDCCH Success Rate (with numerator/denominator)
  - Voice Traffic (Erlang)
  - Perceive Drop Rate (with numerator/denominator)

---

### Tower List Configuration

#### Format Specification

**Basic Format**:
```
TOWER_ID,ON_AIR_DATETIME
```

**TOWER_ID Rules**:
- Must match Tower ID in CDD file exactly
- Case-sensitive
- Usually follows pattern: `SITE-AREA-DISTRICT-NUMBER`
- Examples: `SUM-AC-STR-0013`, `SUM-ME-BTG-0042`

**ON_AIR_DATETIME Rules**:
- Accepted formats:
  - `M/D/YYYY H:MM` (e.g., `10/8/2025 16:00`)
  - `MM/DD/YYYY HH:MM` (e.g., `10/08/2025 16:00`)
- 24-hour or 12-hour format supported
- The tool analyzes 24 hours starting from this time
- Must be within the range of your CSV data

#### Example Configurations

**Single Tower**:
```
SUM-AC-STR-0013,10/8/2025 16:00
```

**Multiple Towers (Same Date)**:
```
SUM-AC-STR-0013,10/8/2025 16:00
SUM-AC-LSK-0068,10/8/2025 16:00
SUM-ME-BTG-0042,10/8/2025 16:00
```

**Multiple Towers (Different Dates)**:
```
SUM-AC-STR-0013,10/8/2025 16:00
SUM-AC-LSK-0068,10/9/2025 08:00
SUM-ME-BTG-0042,10/10/2025 14:30
```

**With Comments** (text file only):
```
# North Region Towers
SUM-AC-STR-0013,10/8/2025 16:00
SUM-AC-LSK-0068,10/8/2025 16:00

# South Region Towers
SUM-ME-BTG-0042,10/9/2025 08:00
SUM-ME-PST-0015,10/9/2025 10:00
```

---

## 📊 Understanding the Output

### Excel Report Structure

The generated Excel report contains multiple sheets organized for easy navigation and analysis.

---

#### 1. **Index Sheet** (First Sheet)

**Purpose**: Master navigation hub for all towers

**Layout**:
| No | Tower ID | Tower Name | FLAG |
|----|----------|------------|------|
| 1  | SUM-AC-STR-0013 | Tower Alam Sutera | PASS |
| 2  | SUM-AC-LSK-0068 | Tower Lippo Karawaci | FAIL |
| 3  | SUM-ME-BTG-0042 | Tower Bintaro | PASS |

**Features**:
- **Clickable Tower IDs**: Click any Tower ID to jump to that tower's detailed sheet
- **Color Coding**:
  - 🟢 Green = PASS (all KPIs passed)
  - 🔴 Red = FAIL (one or more KPIs failed)
- **Auto-numbered**: Sequential numbering for easy reference
- **Sortable**: Can be sorted by FLAG to see failed towers first

**Usage Tips**:
- Use this sheet as your starting point
- Failed towers appear in red - investigate these first
- Hold Ctrl+Click to open links in new window

---

#### 2. **Tower Summary Sheets** (One per Tower)

Each tower gets a dedicated sheet with comprehensive analysis.

**Sheet Name**: Same as Tower ID (e.g., "SUM-AC-STR-0013")

**Section A: Tower Information Header**
```
┌─────────────────────────────────────────────┐
│ [Logo]           TOWER SUMMARY      [Logo]  │
├─────────────────────────────────────────────┤
│ Tower ID:        SUM-AC-STR-0013            │
│ Tower Name:      Tower Alam Sutera          │
│ Cluster:         SUM-AC-STR                 │
│                                              │
│ Latitude:        -6.2345                    │
│ Longitude:       106.7890                   │
│ Technology:      4G/2G                      │
└─────────────────────────────────────────────┘
```

**Section B: KPI Summary Table** (Rows 10-25)
| Row | KPI Name | Value | Status |
|-----|----------|-------|--------|
| 10  | Availability | 99.5% | ✅ PASS |
| 11  | Session Setup Success Rate | 99.2% | ✅ PASS |
| 12  | Volte CSSR | 0.0% | ⚠️ No Attempt |
| 13  | Erab drop | 1.8% | ✅ PASS |
| 14  | Total Payload | 145.2 GByte | ✅ PASS |
| ... | ... | ... | ... |

**Color Coding**:
- 🟢 Green background = PASS
- 🔴 Red background = FAIL
- 🟡 Yellow background = No Attempt (Volte CSSR only)

**Section C: Visualization Charts** (Below row 28)

16 charts in 6 rows × 3 columns layout:

**Row 1**: LTE Availability KPIs
- Chart 1: Availability (line chart, 24-hour trend)
- Chart 2: Session Setup Success Rate (line chart)
- Chart 3: Volte CSSR (line chart)

**Row 2**: LTE Drop & Traffic
- Chart 4: Erab Drop (line chart)
- Chart 5: Total Payload (stacked area, by cell)
- Chart 6: Volte Traffic (stacked area, by cell)

**Row 3**: LTE Users & Throughput
- Chart 7: RRC User (stacked area)
- Chart 8: DL User Throughput (line chart)
- Chart 9: UL User Throughput (line chart)

**Row 4**: LTE Cell Throughput
- Chart 10: DL Cell Throughput (line chart)
- Chart 11: UL Cell Throughput (line chart)

**Row 5**: GSM Availability
- Chart 12: Radio Network Availability Rate (line chart)
- Chart 13: Call Setup Success Rate (line chart)
- Chart 14: SDCCH Success Rate (line chart)

**Row 6**: GSM Traffic & Drop
- Chart 15: Voice Traffic / Erl (stacked area, by BTS)
- Chart 16: Perceive Drop Rate (line chart)

**Chart Features**:
- **X-axis**: Time (hourly from on-air time)
- **Y-axis**: KPI value with unit
- **Legend**: Shows individual cells/BTS (up to 20)
- **Colors**: Distinct colors for each cell/BTS
- **Title**: KPI name
- **Grid**: Light grid lines for easier reading

---

#### 3. **CELL SUMMARY Sheet**

**Purpose**: Comprehensive table with all cells and their KPI evaluations

**Columns**:
```
TOWER_ID | CELL_NAME | Type | Tech | KPI | Value | Baseline | FLAG
```

**Example Data**:
| TOWER_ID | CELL_NAME | Type | Tech | KPI | Value | Baseline | FLAG |
|----------|-----------|------|------|-----|-------|----------|------|
| SUM-AC-STR-0013 | SUM-AC-STR-0013-1 | WD | LTE | Availability | 99.5 | 99 | PASS |
| SUM-AC-STR-0013 | SUM-AC-STR-0013-1 | BH | LTE | Session Setup Success Rate | 99.2 | 99 | PASS |
| SUM-AC-STR-0013 | SUM-AC-STR-0013-2 | WD | LTE | Availability | 98.8 | 99 | FAIL |

**Usage**:
- **Filter by TOWER_ID**: See all KPIs for specific tower
- **Filter by FLAG**: Find all failed KPIs across network
- **Filter by KPI**: Compare specific KPI across all cells
- **Pivot Table**: Create custom analysis views
- **Export**: Copy to separate file for further analysis

**Total Records**: Approximately 16 × number of cells/BTS

---

#### 4. **LTE RAW HOURLY Sheet**

**Purpose**: Detailed hourly LTE data for deep-dive analysis

**Columns** (50+ columns):
```
TOWER_ID, CELL_NAME, BEGIN_TIME, 
NEW_TOWER_NAME, LONG, LAT, SECTOR, RRU_MODEL, CELL_TYPE,
Availability, Total Payload, Volte Traffic,
Session Setup Success Rate, Volte CSSR, Erab drop,
RRC User, DL User throughput, UL User throughput,
DL Cell Throughput, UL Cell Throughput,
...and 30+ CDD configuration columns
```

**Data Granularity**: One row per cell per hour

**Example**:
| TOWER_ID | CELL_NAME | BEGIN_TIME | Availability | Total Payload |
|----------|-----------|------------|--------------|---------------|
| SUM-AC-STR-0013 | -0013-1 | 2025-10-08 16:00:00 | 99.5 | 6.2 |
| SUM-AC-STR-0013 | -0013-1 | 2025-10-08 17:00:00 | 99.3 | 6.8 |
| SUM-AC-STR-0013 | -0013-1 | 2025-10-08 18:00:00 | 99.7 | 7.5 |

**Usage**:
- Identify peak hours
- Analyze hour-by-hour trends
- Compare cells side-by-side
- Create custom charts in Excel
- Export for analysis in other tools

---

#### 5. **GSM RAW HOURLY Sheet**

**Purpose**: Detailed hourly GSM data

**Columns** (30+ columns):
```
TOWER_ID, SITE_NAME, BTS_NAME, BEGIN_TIME,
NEW_TOWER_NAME, LONG, LAT, SECTOR, CELL_TYPE, BSC_NAME,
Radio Network Availability Rate, Call Setup Success Rate,
SDCCH Success rate, Voice Traffic / Erl, Perceive Drop Rate,
...and 20+ CDD configuration columns
```

**Similar structure to LTE RAW HOURLY** but for GSM/2G network elements.

---

### Reading KPI Status

#### Status Values

**PASS (Green)**
- KPI meets or exceeds target
- Network element performing as expected
- No action required

**FAIL (Red)**
- KPI does not meet target
- Requires investigation
- Possible causes:
  - Network congestion
  - Hardware issues
  - Configuration problems
  - Environmental factors

**No Attempt (Yellow)** - Volte CSSR only
- No VoLTE calls were attempted during analysis period
- Not necessarily a problem
- Common in areas with low VoLTE adoption
- Or during off-peak hours

**Blank/Empty**
- Data not available in source files
- Automatically marked as FAIL
- Check if:
  - CSV file has the required columns
  - Data exists for the time period
  - Cell/BTS name matches CDD

---

### KPI Evaluation Logic

#### LTE Availability (≥99%)
```
If Availability ≥ 99% → PASS
If Availability < 99% → FAIL
```

#### LTE Erab Drop (<2%)
```
If Erab drop < 2% → PASS
If Erab drop ≥ 2% → FAIL
```

#### LTE Total Payload (>0)
```
If Total Payload > 0 → PASS
If Total Payload = 0 or NULL → FAIL
```

#### GSM Call Setup Success Rate (≥98%)
```
If Call Setup SR ≥ 98% → PASS
If Call Setup SR < 98% → FAIL
```

---

## 🔧 Troubleshooting

### Common Issues and Solutions

---

#### Issue 1: Application Won't Start

**Symptoms**:
- Double-clicking does nothing
- Error message: "Application failed to start"
- Black window flashes and closes

**Solutions**:

1. **Check Windows Defender/Antivirus**
   - The executable may be blocked by antivirus software
   - Right-click `STATOREPORT.exe` → Properties → Unblock
   - Add to antivirus exceptions if needed

2. **Run as Administrator** (Windows)
   - Right-click `STATOREPORT.exe`
   - Select "Run as administrator"

3. **Check Missing DLL Files** (Windows)
   - Install [Visual C++ Redistributable](https://aka.ms/vs/17/release/vc_redist.x64.exe)
   - Restart computer after installation

4. **Check File Permissions** (Linux)
   ```bash
   chmod +x STATOREPORT.bin
   ls -l STATOREPORT.bin  # Should show execute permission
   ```

5. **Check Assets Folder**
   - Ensure `assets/` folder exists in the same directory as executable
   - Verify `template.xlsx` is present
   - Folder structure must be intact

---

#### Issue 2: "Template not found" Error

**Error Message**:
```
FileNotFoundError: Template not found: assets/template.xlsx
```

**Solutions**:

1. **Verify Folder Structure**
   ```
   STATOREPORT/
   ├── STATOREPORT.exe (or .bin)
   └── assets/
       └── template.xlsx  ← Must exist here
   ```

2. **Don't Move Executable**
   - Keep the executable in the original extracted folder
   - Don't move it to Desktop or other locations without the `assets` folder

3. **Re-extract ZIP File**
   - If files are missing, re-extract the original ZIP
   - Don't use "Run from ZIP" - always extract first

4. **Create Shortcut Instead**
   - Instead of moving the executable, create a shortcut
   - Right-click → Send to → Desktop (create shortcut)

---

#### Issue 3: "No Data in Output Report"

**Symptoms**:
- Report generates successfully
- But towers show no data or all blank values

**Causes & Solutions**:

**Cause 1: Tower ID Mismatch**
- Tower ID in your list doesn't match CDD or CSV files
- **Solution**: 
  - Open CDD file and verify exact Tower ID spelling
  - Check for extra spaces or special characters
  - Tower IDs are case-sensitive

**Cause 2: Wrong On-Air DateTime**
- On-air time is outside the CSV data range
- **Solution**:
  - Check your CSV files' date range
  - Ensure on-air time + 24 hours is within CSV coverage
  - Example: If CSV has data for Oct 8-10, on-air time must be Oct 8 or 9

**Cause 3: LTE File Naming**
- LTE CSV files don't start with correct prefix
- **Solution**:
  - Rename files to start with: `Performance Management-History Query-4G`
  - Example: `Performance Management-History Query-4G_mydata.csv`

**Cause 4: Site Name Mismatch (GSM)**
- GSM data uses Site Name, not Tower ID directly
- **Solution**:
  - Verify Site Name in CDD matches Site Name in CSV exactly
  - Check for trailing spaces or special characters

---

#### Issue 4: Charts Not Displaying

**Symptoms**:
- Tower sheets created successfully
- But charts are missing or show errors

**Solutions**:

1. **Check Data Availability**
   - Charts only appear if hourly data exists
   - Verify "LTE RAW HOURLY" or "GSM RAW HOURLY" sheets have data

2. **Excel Compatibility**
   - Open in Excel 2016 or later
   - Earlier versions may not support embedded PNG images
   - Try opening in LibreOffice Calc or Google Sheets as alternative

3. **Image Generation Failed**
   - Check log for matplotlib errors
   - Usually indicates memory issues with large datasets

4. **Chart Too Large**
   - If many cells (>20), charts may be cropped
   - This is normal - legend shows only first 20 cells

---

#### Issue 5: Application Freezes During Processing

**Symptoms**:
- Progress bar stuck at certain percentage
- Window shows "Not Responding"
- Elapsed timer still running

**What's Happening**:
- Application is NOT frozen - it's processing large datasets
- Processing happens in background thread
- Windows may show "Not Responding" but it's still working

**What to Do**:
1. **DO NOT CLOSE** the window
2. **WAIT** - Check the progress bar and log messages
3. **Be Patient** - Large datasets take time:
   - 10+ towers: 5-10 minutes is normal
   - 20+ towers: 10-20 minutes is normal
4. Check Task Manager - CPU should be active

**If Truly Frozen** (>30 minutes with no progress):
1. Check Task Manager for memory usage (might be out of RAM)
2. Close and retry with fewer towers
3. Process in smaller batches

---

#### Issue 6: "Processing Error" Popup

**Symptoms**:
- Red error message in log
- Popup: "An error occurred"

**Common Errors**:

**Error: "list indices must be integers, not str"**
- **Cause**: CSV file structure doesn't match expected format
- **Solution**: 
  - Verify CSV has correct column order
  - First row should be headers
  - No extra rows before data

**Error: "KeyError: 'TOWER_ID'"**
- **Cause**: Managed Element column format is wrong
- **Solution**: 
  - LTE CSV must have Tower ID in format: `#TOWER-ID(eNodeB)`
  - Example: `#SUM-AC-STR-0013(eNodeB)`

**Error: "Cannot parse datetime"**
- **Cause**: Date format in tower list is invalid
- **Solution**: 
  - Use format: `MM/DD/YYYY HH:MM`
  - Check for typos in date/time
  - Use 24-hour format or AM/PM

---

#### Issue 7: High Memory Usage

**Symptoms**:
- Computer slows down
- Task Manager shows high memory usage
- Application takes very long time

**Solutions**:

1. **Process Fewer Towers at Once**
   - Split tower list into batches of 10-15
   - Process separately, then combine results

2. **Close Other Applications**
   - Close Excel, Chrome, and other memory-intensive apps
   - Processing requires 2-4 GB RAM for moderate datasets

3. **Reduce CSV File Size**
   - If CSV files are very large (>100 MB), consider:
   - Splitting by date range
   - Processing only necessary time periods

4. **Upgrade RAM**
   - For regular use with 20+ towers, 8 GB RAM recommended
   - 16 GB RAM ideal for large-scale processing

---

#### Issue 8: Excel Report Won't Open

**Symptoms**:
- "File is corrupted" message
- "Excel cannot open the file"
- Report generated but can't be opened

**Solutions**:

1. **Check File Size**
   - If file is 0 bytes, generation failed
   - Check log for errors during export phase

2. **Disk Space**
   - Ensure adequate disk space (500 MB+ free)
   - Reports with many towers can be 50-200 MB

3. **Excel Repair**
   - Open Excel
   - File → Open → Browse
   - Select the report file
   - Click dropdown next to "Open" → Open and Repair

4. **Try Alternative Apps**
   - LibreOffice Calc (free)
   - Google Sheets (upload to Drive)
   - WPS Office

---

#### Issue 9: Wrong KPI Values

**Symptoms**:
- Values seem incorrect or unexpected
- KPIs marked FAIL but appear to be passing

**Verification Steps**:

1. **Check Source CSV Files**
   - Open CSV in Excel or text editor
   - Verify raw counter values
   - Application uses these exact values

2. **Understand Aggregation**
   - WD (Whole Day) KPIs:
     - Availability: **MEAN** of 24 hours
     - Traffic: **SUM** of 24 hours
   - BH (Busy Hour) KPIs:
     - From the hour with **maximum RRC users**

3. **Check Calculation Logic**
   - Session Setup SR = (Numerator ÷ Denominator) × 100
   - Erab Drop = (Drop Count ÷ Total Attempts) × 100
   - If denominator is 0, result is 0

4. **Verify Against Manual Calculation**
   - Use "LTE RAW HOURLY" sheet
   - Manually calculate KPI for one cell
   - Compare with CELL SUMMARY result

---

### Linux-Specific Issues

#### Issue 10: "Permission Denied" Error

```bash
bash: ./STATOREPORT.bin: Permission denied
```

**Solution**:
```bash
chmod +x STATOREPORT.bin
./STATOREPORT.bin
```

---

#### Issue 11: Missing Shared Libraries

```
./STATOREPORT.bin: error while loading shared libraries
```

**Solution - Ubuntu/Debian**:
```bash
sudo apt-get update
sudo apt-get install libxcb-xinerama0 libxcb-cursor0 libxkbcommon-x11-0
```

**Solution - CentOS/RHEL**:
```bash
sudo yum install xcb-util-wm xcb-util-image xcb-util-keysyms xcb-util-renderutil
```

---

#### Issue 12: Display/Graphics Issues (Linux)

**Symptoms**:
- Application window appears corrupted
- Charts not rendering properly

**Solution**:
```bash
# Set Qt graphics backend
export QT_QPA_PLATFORM=xcb
./STATOREPORT.bin

# Or try
export QT_QPA_PLATFORM=wayland
./STATOREPORT.bin
```

---

## 📚 FAQ

### General Questions

**Q: Do I need Python installed?**  
A: No! The executable is completely standalone. All dependencies are bundled.

**Q: Is this free to use?**  
A: Yes, for internal use. Check LICENSE.txt for details.

**Q: Can I use this on multiple computers?**  
A: Yes, just copy the entire STATOREPORT folder to each computer.

**Q: How do I update to a new version?**  
A: Download the new version and extract to a new folder. You can delete the old folder after verifying the new version works.

**Q: Does this send data to the internet?**  
A: No. All processing is 100% local. No data leaves your computer.

---

### Data Questions

**Q: How long does processing take?**  
A: Typical times:
- 1-5 towers: 30 seconds - 2 minutes
- 6-10 towers: 2-5 minutes  
- 11-20 towers: 5-10 minutes
- 21+ towers: 10-20 minutes
- Depends on data size and computer specs

**Q: What's the maximum number of towers I can process?**  
A: No hard limit, but practical limits based on memory:
- 4 GB RAM: Up to 15-20 towers
- 8 GB RAM: Up to 40-50 towers
- 16 GB RAM: 100+ towers
- For large batches, consider processing in groups

**Q: Can I process only LTE or only GSM?**  
A: Yes! Just don't select files for the technology you don't need. The tool handles mixed scenarios.

**Q: What if I don't have hourly data?**  
A: The tool requires hourly granularity. Daily or weekly data won't work correctly.

**Q: Can I process multiple dates for the same tower?**  
A: Yes, add the same tower multiple times with different on-air dates:
```
SUM-AC-STR-0013,10/8/2025 16:00
SUM-AC-STR-0013,10/9/2025 16:00
SUM-AC-STR-0013,10/10/2025 16:00
```

**Q: What timezone should I use?**  
A: Use the same timezone as your CSV file timestamps. The tool doesn't convert timezones.

---

### Technical Questions

**Q: What Excel version do I need?**  
A: Excel 2013 or later recommended. Also works with:
- LibreOffice Calc 6.0+
- Google Sheets (after upload)
- WPS Office

**Q: Can I edit the template.xlsx?**  
A: Yes, but:
- Don't change KPI row positions (rows 10-25)
- Don't remove key cells (D5, D6, D7, I5, I6, I7)
- You can change colors, fonts, logos
- Changes apply to all future reports

**Q: Can I run multiple instances?**  
A: Yes, you can run multiple copies of the application simultaneously. Each processes independently.

**Q: Is there a command-line version?**  
A: Not in the current release. This is a GUI-only application.

**Q: Can I automate this with scripts?**  
A: The executable version is GUI-only. For automation, you'd need the Python source version.

**Q: What about other vendors (Huawei, Ericsson, Nokia)?**  
A: This version is optimized for ZTE format. Other vendors would require custom development.

---

### Report Questions

**Q: How do I compare multiple reports?**  
A: 
1. Generate reports with descriptive filenames
2. Open both in Excel
3. Use Excel's "View Side by Side" feature
4. Or copy sheets between workbooks

**Q: Can I customize the KPI targets?**  
A: Not in the executable version. KPI targets are hard-coded. Contact us for custom versions.

**Q: What if a chart shows "No Data"?**  
A: This means:
- No hourly data available for that KPI
- Tower has no cells/BTS for that technology
- Data was filtered out (outside 24-hour window)

**Q: Why are some KPIs blank?**  
A: Possible reasons:
- CSV file doesn't have that counter
- Counter column is empty in source
- Cell didn't report during the period
- Configuration issue (e.g., VoLTE not enabled)

**Q: Can I export to PDF?**  
A: Not directly. But you can:
1. Open report in Excel
2. File → Save As → PDF
3. Or use Excel's "Export to PDF" feature

---

### Troubleshooting Questions

**Q: Why does the application look different than screenshots?**  
A: The application uses dark theme by default. If it appears in light theme, it means the system overrode the theme settings. Functionality is the same.

**Q: Application worked yesterday but not today. What changed?**  
A: Common causes:
- Antivirus quarantined the file
- Windows update changed permissions
- Moved application to different folder without assets
- Disk space ran out

**Q: How do I report bugs or request features?**  
A: Contact the development team with:
- Your version number (shown in window title)
- Operating system details
- Clear description of the issue
- Sample input files (if possible, anonymized)

---

## 🎓 Best Practices

### Data Preparation

1. **Organize Your Files**
   ```
   NetworkData/
   ├── CDD/
   │   └── CDD_Database_October_2025.xlsx
   ├── LTE/
   │   ├── Performance Management-History Query-4G_20251008.csv
   │   └── Performance Management-History Query-4G_20251009.csv
   ├── GSM/
   │   ├── GSM_Performance_20251008.csv
   │   └── GSM_Performance_20251009.csv
   └── TowerLists/
       └── NewSites_October.txt
   ```

2. **Verify Data Before Processing**
   - Open CSV files to check structure
   - Verify date ranges cover your on-air times
   - Ensure Tower IDs exist in CDD

3. **Use Descriptive Output Names**
   - Include date and batch info
   - Example: `STABILITY_REPORT_October_Week1_20251012.xlsx`

---

### Processing Workflow

**Recommended Workflow**:

1. **Test with 1-2 Towers First**
   - Verify file formats are correct
   - Check output quality
   - Adjust if needed

2. **Process in Batches**
   - Group 10-15 towers per batch
   - Easier to troubleshoot if issues occur
   - Faster processing

3. **Review Logs Carefully**
   - Check for warnings about missing data
   - Note any towers that failed to process
   - Save log text for documentation

4. **Verify Results**
   - Spot-check a few KPIs manually
   - Compare with previous reports if available
   - Review failed KPIs for patterns

---

### Report Management

1. **Organize Reports by Date**
   ```
   Reports/
   ├── 2025-10/
   │   ├── Week1/
   │   │   └── STABILITY_REPORT_20251008.xlsx
   │   └── Week2/
   │       └── STABILITY_REPORT_20251015.xlsx
   ```

2. **Archive Old Reports**
   - Keep last 3 months readily accessible
   - Archive older reports to external drive
   - Maintain backup copies

3. **Create Summary Dashboard**
   - Extract Index sheets from multiple reports
   - Combine into master tracking file
   - Track trends over time

---

## 🔄 Workflow Examples

### Example 1: Daily New Site Stability Check

**Scenario**: Check 5 new sites daily

**Steps**:
1. Receive new site list from deployment team
2. Export previous day's performance data (CSV)
3. Launch STATOREPORT
4. Select CDD and CSV files
5. Enter 5 tower IDs with their on-air times
6. Set output: `Daily_Stability_20251012.xlsx`
7. Process
8. Review Index sheet for failures
9. Share report with stakeholders

**Time Required**: 5-10 minutes

---

### Example 2: Weekly Regional Analysis

**Scenario**: Analyze 30 towers in North region

**Steps**:
1. Create tower list file: `North_Region_Week42.txt`
2. Collect week's performance data
3. Launch STATOREPORT
4. Import tower list from file
5. Select all CSV files for the week
6. Set output: `North_Region_Week42_20251012.xlsx`
7. Process (will take 10-15 minutes)
8. Create summary presentation from results

**Time Required**: 20-30 minutes total

---

### Example 3: Monthly Network Health Report

**Scenario**: Generate comprehensive report for 50 towers

**Approach**: Process in 5 batches of 10 towers each

**Day 1-5**: Process batches
- Batch 1: Towers 1-10
- Batch 2: Towers 11-20
- Batch 3: Towers 21-30
- Batch 4: Towers 31-40
- Batch 5: Towers 41-50

**Day 6**: Consolidation
- Extract Index sheets from all 5 reports
- Combine into master dashboard
- Identify trends and issues
- Prepare executive summary

---

## 📞 Support & Contact

### Getting Help

**Before Contacting Support**:
1. ✅ Read this README thoroughly
2. ✅ Check Troubleshooting section
3. ✅ Review FAQ
4. ✅ Verify file formats match specifications
5. ✅ Try with a small test dataset

### Reporting Issues

**Include in Your Report**:
- Application version (shown in window title)
- Operating system and version
- Clear description of the problem
- Steps to reproduce
- Error messages from log (copy the text)
- Sample data files (anonymized if possible)

**Do NOT Include**:
- Sensitive network data
- Customer information
- Proprietary configurations

### Contact Information

- **Email**: support@yourcompany.com
- **Issue Tracker**: github.com/yourcompany/statoreport/issues
- **Documentation**: github.com/yourcompany/statoreport/wiki

---

## 📜 License

This software is provided under the MIT License.

**You are free to**:
- ✅ Use for commercial purposes
- ✅ Modify the software
- ✅ Distribute copies
- ✅ Use privately

**Conditions**:
- Include copyright notice
- Include license text

See `LICENSE.txt` for full terms.

---

## 🙏 Credits

**Developed by**: [Your Company Name]  
**Version**: 1.0.2  
**Release Date**: October 2025  
**Built with**: Nuitka, Python, PyQt6, pandas, matplotlib

**Technologies Used**:
- PyQt6 - Modern GUI framework
- pandas - Data processing engine
- openpyxl - Excel file handling
- matplotlib - Chart generation
- numpy - Numerical operations
- Nuitka - Python to executable compiler

---

## 🎯 Quick Reference Card

### File Requirements
| Item | Format | Requirement |
|------|--------|-------------|
| CDD File | .xlsx | Must have LTE and GSM sheets |
| LTE CSV | .csv | Starts with "Performance Management-History Query-4G" |
| GSM CSV | .csv | Any CSV with GSM data |
| Tower List | .txt or manual | Format: `TOWER_ID,MM/DD/YYYY HH:MM` |

### KPI Types
| Type | Meaning | Aggregation |
|------|---------|-------------|
| WD | Whole Day | 24-hour average or sum |
| BH | Busy Hour | Peak hour (max RRC users) |

### Status Colors
| Color | Meaning | Action |
|-------|---------|--------|
| 🟢 Green | PASS | No action needed |
| 🔴 Red | FAIL | Investigate |
| 🟡 Yellow | No Attempt | Normal for Volte CSSR |

### Keyboard Shortcuts
| Key | Action |
|-----|--------|
| Ctrl+O | Open file dialog (when focused) |
| Ctrl+C | Copy selected text from log |
| Ctrl+A | Select all in text fields |
| Ctrl+Click | Open tower link in new tab |

---

## 📖 Appendix

### A. Sample Tower List File

**Content of `sample_towers.txt`**:
```
SUM-AC-STR-0013,10/8/2025 16:00
SUM-AC-LSK-0068,10/8/2025 16:00
SUM-ME-BTG-0042,10/9/2025 08:00
SUM-ME-PST-0015,10/9/2025 10:00
SUM-AC-MRD-0091,10/10/2025 12:00
```

### B. Expected CSV Column Positions

**LTE CSV Critical Columns**:
- Column 0: Managed Element (format: `#TOWER-ID(eNodeB)`)
- Column 1: Begin Time (format: `YYYY-MM-DD HH:MM:SS`)
- Column 2: Cell Name
- Columns 3+: Various counters

**GSM CSV Critical Columns**:
- Site Name column (must match CDD)
- BTS Name column
- Begin Time column
- KPI counter columns

### C. Performance Benchmarks

**Processing Speed (Reference)**:
- Computer: Intel i5, 8GB RAM, SSD
- 10 towers: ~3 minutes
- 20 towers: ~6 minutes
- 50 towers: ~15 minutes

Your results may vary based on:
- Computer specifications
- Data density
- Number of cells per tower
- CSV file sizes

---

**End of Documentation**

For the latest updates and detailed documentation, visit:
**[GitHub Repository](https://github.com/yourcompany/statoreport)**

---

*Last Updated: October 2025*  
*Document Version: 1.0.2*  
*Application Version: 1.0.2*
