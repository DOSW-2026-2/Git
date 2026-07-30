# Git
Collaborative Git, GitHub, and functional programming lab in Java featuring branches, merges, conflict resolution, lambdas, Streams, and collections.

# Laboratory 1 — Git, GitHub, and Functional Programming

**Course:** Software Development and Operations (DOSW)  
**Institution:** Escuela Colombiana de Ingeniería Julio Garavito  
**Semester:** 2026-2  
**Language:** Java  
**Work mode:** 2 or 3 students (Except DOWS-4 -> pairs) 
**Estimated duration:** 2 hours and 30 minutes  

---

## Overview

This laboratory introduces the foundations of collaborative software development using **Git**, **GitHub**, and **functional programming in Java**.

You will work in pairs, but each student must use their own computer, branch, commits, and Git history. Throughout the laboratory, you will practice:

- Repository creation and configuration.
- Collaborative development using branches.
- Meaningful commits and pull-based workflows.
- Merge operations and conflict resolution.
- Functional programming with lambdas.
- Java Streams and collection processing.
- Technical documentation using `README.md`.
- Evidence collection and repository traceability.

The laboratory is organized as a short **express hackathon** consisting of preparation activities, six programming challenges, and a final conceptual questionnaire.

---

## Learning Objectives

By the end of this laboratory, students should be able to:

1. Configure Git and GitHub for collaborative development.
2. Apply a branching strategy based on `main`, `develop`, and `feature/*` branches.
3. Create, push, merge, and synchronize branches.
4. Identify and resolve merge conflicts.
5. Use meaningful commit messages and preserve a clear Git history.
6. Implement Java solutions using:
   - Lambda expressions.
   - Functional interfaces.
   - Streams.
   - `map()`, `filter()`, `sorted()`, and `collect()`.
   - `List`, `HashMap`, `Hashtable`, `HashSet`, and `TreeSet`.
7. Document technical work and evidence in a repository.

---

# Part 0 — Onboarding

**Weight: 5%**

## 1. Resume (CV)

Participation of each team member in Teams by responding to the Resume post.

## 2. Teamwork agreements

Each team must define teamwork agreements, meaning the rules they will use to work together during the semester:

- What times will you meet?
- What will your communication channels be: Teams, WhatsApp, Slack...?
- How often will you meet?
- If a conflict were to arise, how could you resolve it?

Write down your agreements and have them ready, as they will be revisited in later parts of this lab.

---

# Part 1 — Repository Setup and Preparation

**Weight: 25%**

## 1. GitHub Account

Each student must have a GitHub account.

- If you already have an account, connect it to your institutional email ([steps](https://docs.github.com/es/account-and-profile/how-tos/email-preferences/adding-an-email-address-to-your-github-account)).
- If you do not have one, create it before starting the laboratory.

## 2. Repository Creation

Create one repository per team using the following format:

```text
DOSW_Lab1_LastNameStudent1_LastNameStudent2
```

Example:

```text
DOSW_Lab1_Gualtero_Martinez
```

## 3. Add Collaborators

Add the following people as collaborators:

- Your teammates.
- The course instructor.

Send the repository URL to the instructor through Microsoft Teams.

## 4. Configure Git Locally

Each student must configure Git using their own name and institutional email:

```bash
git config --global user.name "Your Full Name"
git config --global user.email "your.email@escuelaing.edu.co"
```

Verify the configuration:

```bash
git config --global --list
```

## 5. Create the Development Branch

From GitHub or locally, create the `develop` branch from `main`.

```bash
git checkout main
git pull
git checkout -b develop
git push -u origin develop
```

## 6. Clone the Repository

Each student must clone the repository on their own computer:

```bash
git clone <repository-url>
cd DOSW_Lab1_LastNameStudent1_LastNameStudent2
```

## 7. Create Individual Feature Branches

Each student must create a personal branch from `develop`.

Format:

```text
feature/LastNameFirstName_2026-2
```

Example:

```bash
git checkout develop
git pull origin develop
git checkout -b feature/GualteroRodrigo_2026-2
```

## 8. Initial Project Structure

One student must create the following structure:

```text
Laboratory1/
├── challenge1/
│   └── Challenge1.java
├── challenge2/
│   └── Challenge2.java
├── challenge3/
│   └── Challenge3.java
├── challenge4/
│   └── Challenge4.java
├── challenge5/
│   └── Challenge5.java
├── challenge6/
│   └── Challenge6.java
└── README.md
```
That team member must upload these changes to the branch:

```bash
git add .
git commit -m “<Add a short comment describing the change you made>”
git push url repositorio
```

Another team member should generate the `README.md` file with the following content:

- Team members.
- Challenge evidence (At this point, only the title. In the next parts, you'll fill out the evidences).
- Technical explanations (At this point, only the title. In the next parts, you'll fill out the explanations).
- Answers to the conceptual questionnaire (At this point, only the title. In the next parts, you'll fill out the questionnaire).

That team member must upload these changes to the branch:

```bash
git add .
git commit -m “<Add a short comment describing the change you made>”
git push url repositorio
```
Merge your repository structure and `README.md` file from your personal branches into `develop`.

```bash
git checkout develop
git pull
git merge feature/GualteroRodrigo_2026-2
```

## 9. README Evidence Format

Use the following structure for each challenge:

```md
## Challenge N — Challenge Name

### Evidence

![Challenge evidence](images/challengeN.png)

### Description

Briefly explain:

- What was implemented.
- How the work was divided.
- Which Git operations were used.
- Which conflicts appeared.
- How the conflicts were resolved.
```

Store screenshots inside an `images/` directory.

---

# Part 2 — Express Hackathon

**Weight: 60%**  
**Suggested time: 1 hour and 50 minutes**

You may solve the challenges in any order. Organize your time carefully.

## General Rules

For each challenge:

1. Create a new branch from `develop`.

```text
feature/challenge_N_LastNameFirstName_2026-2
```

2. All students must contribute commits.
3. Each challenge must include evidence in `README.md`.
4. After completing a challenge, create a final commit:

```bash
git commit -m "feat: challenge N completed"
```

5. Merge the completed challenge branch into `develop`.
6. Preserve the branch history.
7. All programming challenges must be implemented in Java.

---

## Challenge 1 — Welcome Message

Create a welcome message using Java functional programming.

### Goal

Use a lambda-based solution to print information about both team members.

The output must include:

- Full name.
- Age.
- Institutional email.
- Current semester.

### Requirements

- Create an `Student` class.
- Create a `WelcomeMessage` class.
- Store both students in a `List<Student>`.
- Use:
  - `stream()`
  - `map()`
  - `collect()`
- Use at least one lambda expression.

### Example Output

```text
Hello and welcome!

We are Juan Pérez, a 6th-semester student, 21 years old,
and Miguel Roncancio, a 5th-semester student, 22 years old.

Our institutional emails are:
juan.perez@escuelaing.edu.co
miguel.roncancio@escuelaing.edu.co
```

---

## Challenge 2 — Parallel Commit Race

This challenge simulates parallel development, synchronization, and merge conflicts.

### Initial Setup

Create the challenge branch:

```text
feature/challenge_2_LastNameStudent1_LastNameStudent2_2026-2
```

Rename the Java file to:

```text
ParallelRace.java
```

Create a base class and commit it.

Then create two subbranches:

```text
feature/challenge2_lane_one_LastNameStudent1_2026-2
feature/challenge2_lane_two_LastNameStudent2_2026-2
```

### Lane One

Implement a lambda-based function that:

- Receives a list of numbers.
- Returns the largest number.

### Lane Two

Implement a lambda-based function that:

- Receives a list of numbers.
- Returns the smallest number.
- Returns the total number of elements.

### First Collision

Both students must independently create a method with the same name that combines their results.

The final result object must contain:

- Maximum value.
- Minimum value.
- Number of elements.

Merge both branches and resolve the conflict correctly.

You may use:

```bash
git stash
git stash pop
```

### Second Lap

Lane One must add:

- Validation of whether the maximum value is a multiple of 2.

Lane Two must add:

- Validation of whether the maximum value is divisible by 2.

Use a ternary operator.

### Third Collision

Lane One must determine whether the list size is even.

Lane Two must determine whether the list size is odd.

Merge both branches again and resolve any conflicts.

### Final Goal

Create a single function that receives two lists of numbers and returns a `Results` object containing, for each list:

- Maximum value.
- Minimum value.
- Number of elements.
- Whether the maximum is a multiple or divisor of 2.
- Whether the list size is even or odd.

### Evidence

Display the complete branch and merge history:

```bash
git log --oneline --graph --decorate --all
```

---

## Challenge 3 — The Mysterious Echo

A mysterious cave transforms messages in different ways.

### Student A — `StringBuilder`

Create a method that:

- Receives a `String`.
- Repeats the message three times.
- Separates each repetition with a space.

Branch format:

```text
feature/challenge3_builder_LastNameStudent1_2026-2
```

### Student B — `StringBuffer`

Create a method that:

- Receives a `String`.
- Reverses the message.

Branch format:

```text
feature/challenge3_buffer_LastNameStudent2_2026-2
```

### Collision

Both students must create a function with the same name that:

1. Repeats the message three times.
2. Reverses the final result.

Merge both branches and resolve the conflict.

### Requirements

- Use a lambda to invoke the function.
- Use `stream()` to process the repetitions.
- Use both `StringBuilder` and `StringBuffer`.

---

## Challenge 4 — The Treasure of Duplicate Keys

A treasure map is divided between two data structures:

- `HashMap`
- `Hashtable`

Your team must combine both maps while resolving duplicate keys.

### Student A — HashMap

Create a method that:

- Receives key-value pairs of type `(String, Integer)`.
- Stores them in a `HashMap`.
- Ignores duplicate keys.
- Preserves the first value found.

### Student B — Hashtable

Create the equivalent method using `Hashtable`.

### Merge Goal

Create a method that combines both maps.

Rules:

- When duplicate keys exist, prioritize the `Hashtable` value.
- Convert all keys to uppercase.
- Sort keys in ascending order.
- Print the final result.

### Requirements

Use:

- `stream()`
- `map()`
- `sorted()`
- `Collectors.toMap()`
- Lambda expressions

At least one merge conflict must be resolved.

### Example Input

```text
HashMap:
("gold", 5)
("silver", 3)
("gold", 7)
("diamond", 10)

Hashtable:
("silver", 8)
("ruby", 4)
("gold", 12)
("emerald", 6)
```

### Expected Output

```text
Key: DIAMOND | Value: 10
Key: EMERALD | Value: 6
Key: GOLD | Value: 12
Key: RUBY | Value: 4
Key: SILVER | Value: 8
```

---

## Challenge 5 — Battle of Sets

Two armies are represented by unique numbers.

- One army uses `HashSet`.
- The other uses `TreeSet`.

### Student A — HashSet

Create a method that:

- Stores random integers in a `HashSet`.
- Removes multiples of 3.

### Student B — TreeSet

Create a method that:

- Stores random integers in a `TreeSet`.
- Keeps natural ascending order.
- Removes multiples of 5.

### Final Goal

Merge both collections into a single ordered structure that:

- Removes duplicates.
- Preserves ascending order.
- Prints the final values.

### Requirements

Use:

```java
stream().filter()
```

Use a lambda to print each result.

### Example Input

```text
HashSet: [4, 9, 15, 7, 18, 21, 10, 5]
TreeSet: [12, 3, 25, 10, 7, 30, 18, 4]
```

### Example Output

```text
Number in the arena: 3
Number in the arena: 4
Number in the arena: 5
Number in the arena: 7
Number in the arena: 10
Number in the arena: 12
Number in the arena: 18
```

---

## Challenge 6 — The Decision Machine

A mysterious machine responds to text commands.

The command manual has been divided between both students.

### Student A Commands

Implement the following commands:

| Command | Response |
|---|---|
| `GREET` | Greetings, traveler of time and code! |
| `FAREWELL` | May the bits be with you until the next mission. |
| `SING` | 01010101 |
| `DANCE` | Spinning in party mode. |

### Student B Commands

Implement the following commands:

| Command | Response |
|---|---|
| `JOKE` | Why did the RAM break up with the CPU? It needed space. |
| `SHOUT` | STACK OVERFLOW ALERT! |
| `WHISPER` | Shhh... the bugs are sleeping. |
| `ANALYZE` | Processing data... result: You are amazing at programming! |

### Merge Goal

Combine all commands into a single implementation.

### Requirements

- Use a `switch` statement.
- Use a `Map<String, Runnable>`.
- Use lambdas to associate commands with actions.
- Resolve merge conflicts.
- Demonstrate every command.

### Example

```java
executeCommand("GREET");
executeCommand("JOKE");
executeCommand("ANALYZE");
executeCommand("DANCE");
```

### Runnable Hint

`Runnable` is a functional interface with one method:

```java
void run();
```

It receives no parameters and returns no value, making it suitable for command-based actions.

Example:

```java
Runnable action = () -> System.out.println("Command executed");
action.run();
```

---

# Part 3 — Conceptual Questionnaire

**Weight: 10%**

Create a dedicated branch for the questionnaire.

Divide the questions between both team members. Each student must contribute commits.

Add all answers to the `README.md`.

## Questions

1. Team agreements: Add the agreements you defined in the Onboarding section here.
2. What is the difference between `git merge` and `git rebase`?
3. What happens when two branches modify the same line of a file?
4. How can you display the branch and merge history graphically in the terminal?
5. What is the difference between a commit and a push?
6. What are `git stash` and `git stash pop` used for?
7. What is the difference between `HashMap` and `Hashtable`?
8. What advantages does `Collectors.toMap()` provide over a traditional loop?
9. When using `stream().map()` on a list of objects, what type of operation is being performed?
10. What does `stream().filter()` do, and what does it return?
11. Describe the steps required to create a new feature branch from `develop`.
12. What is the difference between `git branch` and `git checkout -b`?
13. Why should new functionality be developed in `feature/*` branches instead of directly in `main`?

---

# Recommended Git Workflow

Use the following process for each challenge:

```bash
git checkout develop
git pull origin develop

git checkout -b feature/challenge_N_LastNameFirstName_2026-2

# Implement your changes

git status
git add .
git commit -m "feat: implement challenge N"
git push -u origin feature/challenge_N_LastNameFirstName_2026-2
```

Before merging:

```bash
git checkout develop
git pull origin develop
git merge feature/challenge_N_LastNameFirstName_2026-2
git push origin develop
```

To inspect history:

```bash
git log --oneline --graph --decorate --all
```

---

# Commit Message Convention

Use clear and meaningful messages.

Recommended prefixes:

| Prefix | Purpose |
|---|---|
| `feat:` | New functionality |
| `fix:` | Bug fix |
| `docs:` | Documentation changes |
| `refactor:` | Code restructuring |
| `test:` | Test-related changes |
| `chore:` | Configuration or setup |
| `merge:` | Merge-related commit |

Examples:

```text
feat: implement welcome message with streams
fix: resolve duplicate key conflict
docs: add challenge 4 evidence
refactor: simplify result aggregation
chore: create initial project structure
```

---

# Expected Repository Structure

```text
DOSW_Lab1_LastNameStudent1_LastNameStudent2/
├── Laboratory1/
│   ├── challenge1/
│   │   └── Challenge1.java
│   ├── challenge2/
│   │   └── ParallelRace.java
│   ├── challenge3/
│   │   └── Challenge3.java
│   ├── challenge4/
│   │   └── Challenge4.java
│   ├── challenge5/
│   │   └── Challenge5.java
│   └── challenge6/
│       └── Challenge6.java
├── images/
│   ├── challenge1.png
│   ├── challenge2.png
│   ├── challenge3.png
│   ├── challenge4.png
│   ├── challenge5.png
│   └── challenge6.png
└── README.md
```

---

# Submission Checklist

Before submitting, verify that:

- [ ] Both students are repository collaborators.
- [ ] The instructor has access to the repository.
- [ ] `main` and `develop` branches exist.
- [ ] Each student created and used personal branches.
- [ ] Every challenge has a dedicated branch.
- [ ] Both students contributed commits to every challenge.
- [ ] Merge conflicts were resolved correctly.
- [ ] All Java programs compile and run.
- [ ] Evidence is included in the `README.md`.
- [ ] The questionnaire is complete.
- [ ] Commit messages are meaningful.
- [ ] The Git history is visible and understandable.
- [ ] The final version is merged into `develop`.

---

# Evaluation

| Component | Weight |
|---|---:|
| Onboarding | 5% |
| Repository setup and preparation | 25% |
| Express Hackathon challenges | 60% |
| Conceptual questionnaire | 10% |
| **Total** | **100%** |

---

# Academic Integrity

The work must be completed by the registered pair.

Artificial intelligence tools may be used as learning assistants, but students must:

- Understand all submitted code.
- Be able to explain every implementation decision.
- Document significant AI assistance.
- Avoid submitting generated code without review.
- Respect the institution's academic integrity policies.

> Use AI as a learning engine, not as a substitute for thinking.

---

# Team Members

| Name | Institutional Email | GitHub Username |
|---|---|---|
| Student 1 |  |  |
| Student 2 |  |  |
| Student 3 (Only DOSW-1, DOSW-2 and DOSW-3) |  |  |

---

# Instructor

**DOSW Teachers** 
Software Development and Operations — DOSW  
`laura.herrera@escuelaing.edu.co`
`rodrigo.gualtero-m@escuelaing.edu.co`
