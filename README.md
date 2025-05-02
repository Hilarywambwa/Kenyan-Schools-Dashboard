# From Data to Dashboard: Kenyan Secondary Schools Resource Analysis

## Introduction
This project transforms a dataset of 5,000+ Kenyan secondary schools across 47 counties into an interactive Excel dashboard, visualizing resource disparities in teacher staffing and land availability. The dashboard features four KPIs and three charts, filterable by county, to support policymakers and educators in addressing teacher shortages, gender imbalances, and land constraints for educational equity. Built in Microsoft Excel, it showcases data analysis, PivotTables, and visualization techniques.

## Dataset
- **Sources**:
  - Schools: [Kenya Secondary Schools](https://github.com/mapkibera/education/blob/master/data/kenya-secondary-schools.csv)
  - Counties: [Kenya Counties Data](https://github.com/pkiage/data-Kenya-Counties-Constituencies-Wards)
- **Size**: 5,000+ schools, 47 counties.
- **Preprocessing**:
  - Created sheets: Working, KPIcalculations, PivotTable, Dashboard.
  - Cleaned missing values, standardized formats, removed unwanted columns.
  - Deleted rows with zero/blank staff, enrollment, or acreage.
  - Used VLOOKUP to assign counties to schools via constituency data.
  - Removed duplicate counties using Excel’s Remove Duplicates feature.

## Dashboard Components
Located in the `Dashboard` sheet, the dashboard includes:

### KPIs (Filtered by County Slicer)
1. **% Female TSC Teachers**:
   - Average `(TSC Female Teachers / Total Teaching Staff) * 100` per county.
   - Purpose: Highlights gender imbalances (red if <33%).
2. **Schools with >15:1 Pupil-Teacher Ratio**:
   - % of schools per county with ratio >15.
   - Purpose: Identifies overcrowded classrooms (red if >24%).
3. **Additional Teachers Needed for 15:1 Ratio**:
   - Sum of `MAX(0, (Enrollment / 15) - Teachers)` per county.
   - Purpose: Quantifies teacher shortages.
4. **Average Acreage per Student**:
   - Average `(Acreage / Enrollment)` per school, by county.
   - Purpose: Reveals land constraints (red if <0.189).

### Charts
1. **100% Stacked Bar Chart: Teacher Distribution by Sponsor**:
   - Shows proportions of TSC/PTA-BOG teachers by sponsor.
   - Purpose: Compares staffing models (filterable by county).
2. **Bar Chart: Top/Bottom Pupil-Teacher Ratios**:
   - Static chart of top 10 and bottom 10 counties by ratio.
   - Purpose: Highlights disparities (e.g., Lamu: 21, Nairobi: 13).
3. **Line Chart: Land Allocation by Sponsor**:
   - Average acreage per school by sponsor, for boys, girls, mixed schools.
   - Purpose: Visualizes land disparities (filterable by county).

### County Slicer
- Filters KPIs, stacked bar, and line charts by county.
- Located at A1 in Dashboard (two slicers: CountyKPIs, CountyCharts).
- Clearing slicer shows average values.

## Setup and Usage
1. **Requirements**:
   - Microsoft Excel.
   - File: `Kenyan_Schools_Dashboard.xlsx` (in repository).
2. **Installation**:
   - Clone/download: `git clone [repository URL]`.
   - Open `Kenyan_Schools_Dashboard.xlsx` in Excel.
3. **Usage**:
   - Navigate to `Dashboard` sheet.
   - Use slicers to filter by county (e.g., Busia).
   - View KPIs and charts for county-specific or average metrics.
   - Explore raw data in `Data` sheet.

## Key Insights
- **Teacher Shortages**: High pupil-teacher ratios in counties like Kwale (21:1, 63% schools >15:1).
- **Gender Imbalance**: Only Kiambu and Embu meet 33% female TSC teacher threshold.
- **Land Constraints**: Urban areas like Nairobi have low acreage (0.033 acres/student).
- **Sponsor Variability**: NGO/CBO and private schools rely heavily on PTA/BOG teachers.
- **Land Allocation**: Boys’ schools receive more land than girls’ or mixed schools, especially government-sponsored.
- **Recommendations**: Prioritize teacher hiring in high-ratio counties, increase female TSC teachers, allocate land for urban and girls’ schools.

## Tools and Techniques
- **Excel**:
  - PivotTables for KPI calculations.
  - Slicers for dynamic filtering.
  - Charts (stacked bar, bar, line) for visualization.
  - Conditional formatting for critical KPIs.
  - GETPIVOTDATA for dynamic KPI display.
- **Data Processing**:
  - Cleaned and structured 5,000+ row dataset.
  - VLOOKUP for county assignment.

## Challenges and Solutions
- **Challenge**: Slicer not recognizing new PivotTables.
  - **Solution**: Recreated PivotTables with shared data source, reconnected slicer.
- **Challenge**: Duplicate counties in constituency data.
  - **Solution**: Used Remove Duplicates to clean data before VLOOKUP.

## Contact
- **Email**: wambwahilary@gmail.com
- **LinkedIn**: https://www.linkedin.com/in/hilary-wambwa-288610355/


## License
Licensed under the MIT License. See `LICENSE` for details.# Kenyan-Schools-Dashboard
