# Instructor Notes

## Setup for GitHub Classroom

### 1. Create GitHub Classroom Assignment

1. Go to GitHub Classroom (https://classroom.github.com)
2. Create a new assignment: "Log Analysis Commands Homework"
3. Set deadline (20 minutes recommended during lab time)
4. Use this repository as a template
5. Enable feedback pull requests (optional)

### 2. Upload This Repository

```bash
# If you haven't already, create a repo on GitHub
# Then push this directory

cd ~/Desktop/log-analysis-homework

# Add remote (replace with your repo URL)
git remote add origin https://github.com/YOUR_USERNAME/log-analysis-homework.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Assignment Link

After creating the assignment:
- Share the GitHub Classroom invitation link with students
- Students will accept and get individual private repositories
- You can track submissions through the GitHub Classroom dashboard

---

## Grading Guide

### Task 1: grep Operations (5 points)

**Expected Commands:**
```bash
# 1.1 - Find ERROR (case-insensitive)
grep -i "error" log.log

# 1.2 - Multiple patterns
grep -E "DEBUG|INFO|WARNING" log.log

# 1.3 - SELFTEST with 5 lines after
grep -A 5 "SELFTEST" log.log

# 1.4 - alarm with context
grep -i -C 2 "alarm" log.log
```

**Grading:**
- 1.25 points per sub-task
- Full credit if command is correct and output is documented
- Partial credit (0.5) if command works but documentation is incomplete

---

### Task 2: tail/head Operations (3 points)

**Expected Commands:**
```bash
# 2.1 - Last 25 lines
tail -n 25 log.log

# 2.2 - First 10 lines
head -n 10 log.log

# 2.3 - Timestamp difference
# First: 2025-12-19 08:16:33.157
# Last: (depends on log file)
# Students should calculate time difference
```

**Grading:**
- 1 point per sub-task
- Full credit for correct commands and analysis
- Deduct 0.5 for missing timestamp analysis

---

### Task 3: awk Processing (5 points)

**Expected Commands:**
```bash
# 3.1 - Count log levels
awk '{print $3}' log.log | sort | uniq -c

# Alternative:
grep -oE "DEBUG|INFO|WARNING|ERROR|SUCCESS" log.log | sort | uniq -c

# 3.2 - Extract timestamp and log level
awk '{print $1, $2, $3}' log.log

# 3.3 - AlarmNotifier.py entries
awk '/AlarmNotifier.py/ {print $1, $2, $NF}' log.log
```

**Grading:**
- 1.67 points per sub-task
- Award full credit for any working solution
- Partial credit for attempts that show understanding

---

### Task 4: Combined Commands (7 points)

**Expected Commands:**
```bash
# 4.1 - tail + grep for MQTT
tail -n 100 log.log | grep "MQTT"

# 4.2 - tail + grep + awk for timestamps
tail -n 200 log.log | grep "Published MQTT MSG" | awk '{print $1, $2}'

# 4.3 - grep + awk for unique error files
grep "ERROR" log.log | awk '{print $6}' | sort -u | wc -l
```

**Grading:**
- 2.33 points per sub-task
- Bonus: +2 points for bonus challenge
- Look for correct pipe usage and logical flow

---

## Expected Results Summary

Based on the provided `log.log`:

- Total lines: ~10,400+
- ERROR lines: Variable (students should count)
- DEBUG entries: Majority of log
- INFO entries: Second most common
- MQTT messages: Multiple throughout
- AlarmNotifier.py: Significant presence

---

## Common Student Mistakes

1. **Forgetting quotes** - `grep ERROR` vs `grep "ERROR"`
2. **Wrong pipe order** - Using awk before grep when not needed
3. **Not counting** - Forgetting `| wc -l`
4. **Case sensitivity** - Missing `-i` flag when needed
5. **Field numbers** - awk field numbering starts at $1, not $0

---

## Time Allocation Monitoring

During lab session, watch for:
- **5 min mark**: Students should be on Task 1
- **10 min mark**: Starting Task 3
- **15 min mark**: Working on Task 4
- **18 min mark**: Final checks and submission

---

## Extension Activities

For fast finishers:

1. **Create visualizations**: Plot log levels over time
2. **Performance analysis**: Time different grep patterns
3. **Custom filters**: Find patterns specific to their research
4. **Log monitoring**: Use `tail -f` to watch live logs

---

## Discussion Points (Post-Homework)

1. **Efficiency**: Which commands were fastest?
2. **Readability**: Complex one-liners vs. simple pipes
3. **Real-world use**: How to apply to their research
4. **Debugging**: How they troubleshot errors
5. **Tools**: Introduction to `sed`, `cut`, `sort`, `uniq`

---

## GitHub Classroom Features

### Auto-grading (Optional)

You can set up auto-grading tests:

```yaml
# .github/classroom/autograding.json
{
  "tests": [
    {
      "name": "Task 1 File Exists",
      "setup": "",
      "run": "test -f task1_results.txt",
      "input": "",
      "output": "",
      "comparison": "included",
      "timeout": 1,
      "points": 1
    }
  ]
}
```

### Feedback Pull Requests

Enable to provide inline feedback on student submissions.

---

## Support Resources

Share these with students:
- GNU Grep Manual: https://www.gnu.org/software/grep/manual/
- AWK Tutorial: https://www.grymoire.com/Unix/Awk.html
- Command Line Cheat Sheet: Include in repository

---

## Assignment Variations

For different skill levels:

**Easier Version:**
- Provide more example commands
- Reduce number of sub-tasks
- Allow 30 minutes

**Harder Version:**
- Add sed and cut commands
- Require regular expressions
- Include performance optimization

**Research-Specific:**
- Replace log.log with domain-specific data
- Add tasks relevant to their field
- Include data extraction for analysis

---

## Questions to Expect

1. **"Why use grep instead of Python?"**
   - Speed for simple tasks
   - Available everywhere
   - Foundational knowledge

2. **"Can we use other tools?"**
   - Yes, if they accomplish the task
   - Encourage learning the specified tools first

3. **"What if the output is too long?"**
   - Use `| head` to limit output
   - Or `| less` to page through

---

## Post-Assignment Survey (Optional)

Consider asking:
1. Which command was most useful?
2. Which task was most challenging?
3. How will you use these in your research?
4. What other tools would you like to learn?

---

**Good luck with the assignment! 📚**
