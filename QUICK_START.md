# Quick Start Guide

## Getting Started (5 minutes)

### 1. Accept the GitHub Classroom Assignment
- Click the assignment link provided by your instructor
- Accept the assignment
- GitHub will create a private repository for you

### 2. Clone Your Repository
```bash
git clone <your-repository-url>
cd log-analysis-homework
```

### 3. Verify Files
Check that you have these files:
```bash
ls -l
# You should see:
# - README.md (main instructions)
# - log.log (data file)
# - task_template.txt (submission template)
# - QUICK_START.md (this file)
```

### 4. Test Basic Commands
Try a simple command to verify everything works:
```bash
# Count total lines in log
wc -l log.log

# View first 5 lines
head -n 5 log.log

# Search for ERROR
grep -i "error" log.log | wc -l
```

---

## Workflow (15 minutes)

### Step 1: Read the Tasks (2 min)
Open `README.md` and read through the homework tasks.

### Step 2: Complete Tasks (10 min)

For each task:
1. Write your command
2. Run it
3. Document results

**Example for Task 1.1:**
```bash
# Try the command
grep -i "error" log.log

# Count matches
grep -i "error" log.log | wc -l

# Save to results file
echo "=== Task 1.1: Find ERROR lines (case-insensitive) ===" > task1_results.txt
echo "" >> task1_results.txt
echo "Command:" >> task1_results.txt
echo 'grep -i "error" log.log | wc -l' >> task1_results.txt
echo "" >> task1_results.txt
echo "Output:" >> task1_results.txt
grep -i "error" log.log | wc -l >> task1_results.txt
```

### Step 3: Submit (3 min)
```bash
# Add your result files
git add task1_results.txt task2_results.txt task3_results.txt task4_results.txt

# Commit
git commit -m "Complete log analysis homework"

# Push to GitHub
git push origin main
```

---

## Time Management Tips

| Task | Time | Focus |
|------|------|-------|
| Task 1 | 5 min | grep flags |
| Task 2 | 3 min | tail/head basics |
| Task 3 | 5 min | awk patterns |
| Task 4 | 7 min | Command combinations |

---

## Common Pitfalls to Avoid

1. **Don't overthink** - Start with simple commands
2. **Test incrementally** - Build complex commands step by step
3. **Use wc -l** for counting - Don't manually count lines
4. **Copy-paste carefully** - Watch out for quote marks
5. **Document as you go** - Don't wait until the end

---

## Emergency Commands

If you get stuck, these might help:

```bash
# Clear terminal
clear

# Stop a running command
Ctrl+C

# View command history
history

# Check last command
!!

# See manual for a command
man grep
man awk
```

---

## Example Task Completion

Here's a complete example for Task 1.1:

```bash
# Create task1_results.txt
cat > task1_results.txt << 'EOF'
=== Task 1.1: Find ERROR lines (case-insensitive) ===

Command:
grep -i "error" log.log | wc -l

Output:
42

Explanation:
Used grep with -i flag for case-insensitive search and piped to wc -l to count matching lines.

---
EOF
```

---

## Checklist Before Submission

- [ ] All four task files created
- [ ] Each file contains commands, outputs, and explanations
- [ ] Tested all commands and verified they work
- [ ] Committed changes to git
- [ ] Pushed to GitHub

---

## Getting Help

1. **Check the README** - Most answers are there
2. **Try man pages** - `man grep`, `man awk`
3. **Test simple versions** - Start basic, then add complexity
4. **Ask during lab hours** - Instructor is available

---

**Ready? Start with Task 1! 🚀**
