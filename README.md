# **AI-Assisted Testing – Task Prioritization System**

## **Part 1: Test Planning & Understanding**

### **Behavior Analysis (calculateTaskScore)**

From analyzing the function, I understood that `calculateTaskScore` determines how important a task is based on factors like priority, due date, and last updated time.

### **Key Behaviors to Test**

1. Score increases with higher priority (e.g., HIGH > LOW)
2. Overdue tasks receive higher scores
3. Tasks with closer due dates get higher scores
4. Recently updated tasks may have lower urgency
5. Tasks with no due date are handled correctly

### **Edge Cases Identified**

* Task with no due date
* Task with extremely old last-updated date
* Task with invalid or missing priority
* Tasks due today
* Negative or zero values in scoring inputs

### **Test Cases List**

1. Basic score calculation for a normal task
2. High priority vs low priority comparison
3. Overdue task scoring
4. Task with no due date
5. Recently updated task vs old task

### **Test Plan for All Functions**

#### **Functions Covered**

* `calculateTaskScore` → unit tests
* `sortTasksByImportance` → unit + integration
* `getTopPriorityTasks` → integration

#### **Test Priorities**

1. Core scoring logic (highest priority)
2. Sorting correctness
3. Top task selection

#### **Test Types**

* Unit tests: individual functions
* Integration tests: full workflow

#### **Expected Outcomes**

* Tasks are scored correctly
* Sorting orders tasks from highest to lowest score
* Top tasks function returns correct subset

## **Part 2: Improving Tests**

### **Initial Test (Simple)**

* Checked only if function returns a number

### **Improved Test Insights**

AI helped me realize:

* I was only testing output type, not behavior
* I needed clearer assertions (expected score differences)
* I missed edge cases like overdue tasks

### **Improved Test Example (Concept)**

* Compare two tasks and assert which one has a higher score
* Test overdue vs non-overdue explicitly
* Use fixed dates for predictable results

### **Key Learning**

Good tests check **behavior, not just output**.

## **Part 3: Test-Driven Development (TDD)**

### **New Feature: Assigned User Boost (+12)**

#### **TDD Steps**

1. Write failing test → task assigned to current user should have higher score
2. Implement minimal logic → add +12 if assigned user matches
3. Run test → passes
4. Refactor → clean up logic

### **Bug Fix: Incorrect Days Calculation**

1. Write test showing incorrect “days since update”
2. Fix logic (use correct `.days` calculation)
3. Re-run test → passes
4. Add extra tests to prevent regression

### **Key Learning**

TDD helps:

* Catch bugs early
* Ensure features work correctly
* Build confidence in code changes

## **Part 4: Integration Testing**

### **Workflow Tested**

1. Calculate scores for all tasks
2. Sort tasks by importance
3. Retrieve top priority tasks

### **Integration Test Scenario**

* Create multiple tasks with different priorities and due dates
* Run full workflow
* Assert:

  * Tasks are sorted correctly
  * Top results match expected highest scores

### **Key Insight**

Integration tests ensure that **functions work together correctly**, not just individually.


### **What I Learned**

* Testing is not just about writing code, but understanding behavior
* AI helped guide my thinking instead of just giving answers
* Edge cases are very important and easy to miss
* Writing tests first (TDD) improves code quality

### **Challenges**

* Understanding what to test vs how to test
* Identifying all edge cases
* Writing precise assertions

### **How AI Helped**

* Asked guiding questions instead of giving solutions
* Helped identify missing scenarios
* Improved my test design thinking

### **Future Approach**

* Start with behavior analysis before writing tests
* Always consider edge cases
* Use TDD for new features
* Use integration tests for full workflows


This exercise helped me understand how to:

* Plan tests effectively
* Improve test quality
* Use TDD in practice
* Think critically about code behavior

I now feel more confident in testing and using AI as a learning tool rather than just a shortcut.

