# Lab Reflection: Git Version Control + Debugging (BuggyProgram)

## Student Name
Joseph Wacha

## GitHub Repository URL
https://github.com/TS-Tallo/codinglab

---

# Commit 1: Initial Commit

## What did you include in this commit?
- Initial project files

## What was the purpose of this commit?
- To initialize the repository.

---

# Commit 2: Task 1 (getGrade)

## Which tests in Task1Test were failing before your fix?
- expected: <Exceeds> but was: <Meets>
- expected: <Meets> but was: <Does Not Meet>

## What was the issue in the code?
- Bad conditionals

## What change did you make to fix it?
- Fixed conditionals with returns

## How did the tests help guide your fix?
- Checked for proper return values.

---

# Commit 3: Task 2 (sumEvenNumbers)

## Which tests in Task2Test were failing before your fix?
- CodingRoomsUnitTests.testEmpty threw ArrayIndexOutOfBoundsException at index 0
- CodingRoomsUnitTests.testOddNumbers threw ArrayIndexOutOfBoundsException at index 3
- CodingRoomsUnitTests.testSumEvenNumbers threw ArrayIndexOutOfBoundsException at index 4

## What was the issue in the code?
- The loop used `i <= values.length`, so it read one past the last element. The sum also started at 1 instead of 0.

## What change did you make to fix it?
- Changed the loop to `i < values.length` and started the sum at 0.

## How did the tests help guide your fix?
- All three failures crashed at an index equal to the array length, including the empty array.

---

# Commit 4: Task 3 (sumRange)

## Which tests in Task3Test were failing before your fix?
- CodingRoomsUnitTests.testSumRangeReverseOrder expected 15 but was 0

## What was the issue in the code?
- The loop only runs while `start <= end`, so a reversed range never adds anything and returns 0.

## What change did you make to fix it?
- Swapped `start` and `end` when `start > end`, then kept the inclusive sum.

## How did the tests help guide your fix?
- The only failure was the reverse-order case. Forward order already returned the right sum, so the missing behavior was summing the same range when the arguments are reversed.

---

# Overall Reflection

## Which task was the easiest to fix? Why?
-

## Which task was the most difficult? Why?
-

## How did Git help you track your progress through the debugging process?
-

## Why is it important to make small, frequent commits when debugging code?
-

## What did you learn about using JUnit tests to guide debugging?
-

---

# Commit 5: Final Reflection

## What did you complete or update before making this final commit?
-

## Why is it useful to document your work after completing a programming task?
-