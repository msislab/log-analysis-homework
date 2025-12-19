# Autograding Setup

## Overview

This assignment uses GitHub Classroom's autograding feature to provide immediate feedback to students and reduce manual grading workload.

---

## Grading Breakdown

### Total Points: 20

**Auto-Graded: 12 points**
- Submission completeness: 4 points
- Individual task effort: 8 points (2 per task)

**Manual Review: 8 points**
- Command correctness
- Output accuracy
- Quality of explanations

---

## Auto-Grading Tests

### 1. Pre-Flight Check (Fail Fast)
**Before any grading starts:**
- Checks if all 4 required files exist
- If ANY file is missing → Entire workflow fails immediately
- Student sees clear error message listing missing files
- **Action Required:** Must resubmit with all files

### 2. All Files Submitted (4 points)
**Test:** `test -f task1_results.txt && test -f task2_results.txt && test -f task3_results.txt && test -f task4_results.txt`

**Passes if:** All four task files are present
**Points:** 4
**Purpose:** Ensures complete submission

### 3. Task 1 Effort Check (2 points)
**Test:** File exists AND has more than 15 lines
**Points:** 2
**Purpose:** Checks student put in reasonable effort

### 4. Task 2 Effort Check (2 points)
**Test:** File exists AND has more than 10 lines
**Points:** 2
**Purpose:** Checks student put in reasonable effort

### 5. Task 3 Effort Check (2 points)
**Test:** File exists AND has more than 15 lines
**Points:** 2
**Purpose:** Checks student put in reasonable effort

### 6. Task 4 Effort Check (2 points)
**Test:** File exists AND has more than 15 lines
**Points:** 2
**Purpose:** Checks student put in reasonable effort

---

## What Students See

### ✅ Successful Submission
```
✅ All required files present. Proceeding with grading...
✅ All Files Submitted (4/4 points)
✅ Task 1 Effort Check (2/2 points)
✅ Task 2 Effort Check (2/2 points)
✅ Task 3 Effort Check (2/2 points)
✅ Task 4 Effort Check (2/2 points)

Total: 12/12 auto-graded points
```

### ❌ Incomplete Submission
```
❌ SUBMISSION INCOMPLETE!
Missing required files: task3_results.txt task4_results.txt

Please create all four task result files:
  - task1_results.txt
  - task2_results.txt
  - task3_results.txt
  - task4_results.txt

Refer to README.md for instructions.
Resubmit after creating all required files.
```

---

## Manual Grading (8 points remaining)

You still need to review each submission for:

### Task 1 (5 points total, 2 auto-graded, 3 manual)
- Correct use of grep flags (-i, -E, -A, -B, -C)
- Accurate command syntax
- Valid output/line counts

### Task 2 (3 points total, 2 auto-graded, 1 manual)
- Correct tail/head usage
- Accurate timestamp analysis

### Task 3 (5 points total, 2 auto-graded, 3 manual)
- Proper awk pattern matching
- Field extraction correctness
- Command accuracy

### Task 4 (7 points total, 2 auto-graded, 5 manual)
- Effective command combinations
- Correct pipe usage
- Analysis accuracy
- Bonus challenge (if attempted)

---

## How to Access Student Submissions

### Via GitHub Classroom Dashboard
1. Go to your assignment in GitHub Classroom
2. View the roster
3. Click on student repositories
4. Check the "Actions" tab to see autograding results
5. Review the actual files for manual grading

### Download for Batch Grading
```bash
# Clone all student repos
gh classroom clone student-repos <assignment-url>

# Or download specific student repo
git clone https://github.com/msislab/log-analysis-homework-student-name
```

---

## Grading Workflow

### Step 1: Check Autograding Results
- Open GitHub Classroom dashboard
- Sort by autograding score
- Students with 12/12 → submitted everything
- Students with 0/12 → missing files (ask to resubmit)

### Step 2: Manual Review (for complete submissions)
Open each student's repository and check:

**Quick Check List:**
```
Task 1 (3 points to assign):
[ ] Correct grep syntax
[ ] Appropriate flags used
[ ] Line counts reasonable

Task 2 (1 point to assign):
[ ] Timestamp analysis accurate

Task 3 (3 points to assign):
[ ] Awk patterns correct
[ ] Field extraction works
[ ] Output makes sense

Task 4 (5 points to assign):
[ ] Commands properly piped
[ ] Analysis accurate
[ ] Bonus attempted
```

### Step 3: Enter Grades
- Use GitHub Classroom's grade export feature
- Or maintain a spreadsheet
- Provide feedback via GitHub comments

---

## Autograding File Locations

```
.github/
├── classroom/
│   └── autograding.json          # Test definitions
└── workflows/
    └── classroom.yml              # GitHub Actions workflow
```

---

## Modifying Autograding

### Change Point Values
Edit `.github/classroom/autograding.json`:
```json
{
  "name": "Task 1 Effort Check",
  "points": 3  // Change this value
}
```

### Change Line Count Requirements
Edit the `run` command:
```json
{
  "run": "test $(wc -l < task1_results.txt) -gt 20"  // Change 15 to 20
}
```

### Add New Tests
Add new test object to the `tests` array in `autograding.json`

Then regenerate the workflow:
- GitHub Classroom will update it automatically
- Or manually update `.github/workflows/classroom.yml`

---

## Troubleshooting

### Autograding Doesn't Run
- Check if GitHub Actions is enabled for the repository
- Verify workflow file exists: `.github/workflows/classroom.yml`
- Check Actions tab for error messages

### False Positives/Negatives
- Student might have extra spaces/formatting
- Check actual file content manually
- Adjust line count thresholds if needed

### Students Can't See Results
- Make sure repository visibility is set correctly
- Students need "read" access to see Actions tab
- Check if Actions are public in repository settings

---

## Benefits of This Setup

✅ **Immediate Feedback:** Students see results right away
✅ **Reduced Grading Time:** 60% of points are automated
✅ **Clear Expectations:** Students know exactly what to submit
✅ **Fail Fast:** Incomplete submissions are caught immediately
✅ **Quality Focus:** You grade command quality, not file existence

---

## Stats at a Glance

- **Setup Time:** 5 minutes (already done!)
- **Per-Student Review Time:** ~3-5 minutes (vs 8-10 without autograding)
- **Auto-Graded Coverage:** 60% of total points
- **Resubmission Rate:** Expected to drop significantly with fail-fast check

---

## Next Steps

1. ✅ Autograding configured
2. ✅ Fail-fast check in place
3. ⏳ Test with a sample submission (optional)
4. ⏳ Create assignment in GitHub Classroom
5. ⏳ Share with students

---

**Questions?** Refer to the INSTRUCTOR_NOTES.md for more details.
