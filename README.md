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
- Task 3, sumRange. Only one test failed, and it said expected 15 but was 0. The name testSumRangeReverseOrder made the missing swap obvious. With prior programming experience, none of these bugs were hard, and this one was the smallest.

## Which task was the most difficult? Why?
- Task 2, sumEvenNumbers, but only relative to the others. The tests crashed with ArrayIndexOutOfBoundsException before they could show an expected sum, so the loop bound was clear and the sum starting at 1 was easy to miss. The logic itself was still basic.

## How did Git help you track your progress through the debugging process?
- Each commit held one method fix and the notes for that failure. I could look back and see getGrade, sumEvenNumbers, and sumRange as separate changes instead of one mixed diff.

## Why is it important to make small, frequent commits when debugging code?
- A small commit ties one failing test to one change. If a later edit breaks something, you can see exactly which fix introduced it and roll that change back without losing the earlier fixes.

## What did you learn about using JUnit tests to guide debugging?
- The failure is the spec. getGrade told me the returned labels were swapped, sumEvenNumbers showed the bad index in the stack trace, and sumRange gave the expected value directly. Guessing the behavior before reading the failure is what makes a simple bug take longer.

---

# Commit 5: Final Reflection

## What did you complete or update before making this final commit?
- Filled in the Overall Reflection after the three method fixes and their commit notes were already in this file.

## Why is it useful to document your work after completing a programming task?
- The test output goes away, and a later reader cannot see which failure caused which change. Writing it down keeps the reason for the fix, not just the final code.