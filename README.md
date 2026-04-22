# E-Learning Platform Analysis

## Context

Exploratory analysis of a 2-year dataset from an online education platform: student activity, course metrics, and subscription patterns. Goal: identify key metrics, segment users, compare courses, and evaluate assessment effectiveness.

## Stack

### Python

- pandas — data manipulation
- numpy — numerical computation
- requests, urllib.parse — data loading
- seaborn, matplotlib — visualization

## Workflow

1. **Define "course"** from raw data (no documentation was available).
2. **Data quality**: missing values, outliers, recording errors.
3. **Distribution analysis** across key variables.
4. **Targeted questions**:
   - How many users completed exactly one course?
   - Which exam was hardest / easiest?
   - Average time to exam completion?
   - Most popular subjects; highest churn?
   - Lowest completion rate and longest average exam time?
5. **User-level metric design and RFM segmentation**.

## Key Findings

- The highest-revenue potential segment is the smallest: users who enroll early but perform only moderately. This segment can likely be grown by nurturing impulse-purchasers between enrollment and course start.
- Leveraging all assessment types (not just exams) for course completion would prevent courses without exams from falling off the radar — and these are the majority.
- Detected a data anomaly: some unsubscribed users were never recorded as having subscribed. Flagged for engineering review.
