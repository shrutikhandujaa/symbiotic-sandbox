# Product Requirements Document: Symbiotic Sandbox

## 1. Goal

Help people learn faster and become more productive while building technology by strengthening their ability to **identify, reason about, and fix real-world logical bugs** using an AI-powered adversarial learning approach.

---

## 2. Target Users

### Primary Users
- **Students & Bootcamp Learners**
  - Learning programming fundamentals
  - Struggle with debugging and edge cases
  - Over-rely on AI-generated answers

- **Junior Developers (0–2 years experience)**
  - Can write working code but lack debugging confidence
  - Need exposure to realistic failure scenarios
  - Want to improve problem-solving speed and accuracy

### Secondary Users
- **Coding Instructors**
  - Need scalable debugging exercises
  - Want automated assessment of reasoning skills

- **Technical Interviewers**
  - Need realistic debugging challenges
  - Want to evaluate thinking, not memorization

---

## 3. Core Features

### 3.1 Logical Ghost Injection Engine
- AI analyzes user code to understand intent
- Injects **context-aware logical flaws** (not syntax errors)
- Bugs mimic real production issues such as:
  - Silent failures
  - Incorrect success states
  - Edge-case mishandling

---

### 3.2 Dual Execution Environment
- **Gold Master**: Original user code
- **Ghost Sandbox**: Mutated version with hidden logic flaws
- System compares outputs, side effects, and logs

---

### 3.3 Adversarial Learning Mode
- Learners are shown incorrect or unexpected behavior
- AI challenges users to locate and explain the flaw
- No direct answers—only guided hints and reasoning prompts

---

### 3.4 Adaptive Difficulty System
- Bug complexity scales with learner performance
- Progresses from simple condition errors to complex logic flows
- Prevents both boredom and overload

---

### 3.5 Feedback & Reflection
- AI explains *why* the bug occurred after resolution
- Highlights transferable debugging patterns
- Reinforces long-term learning instead of quick fixes

---

## 4. Success Metrics

### Learning Effectiveness
- Bug detection accuracy over time
- Reduction in time taken to diagnose issues
- Quality of learner explanations (reasoning depth)

### User Engagement
- Challenges completed per session
- Voluntary retries on higher difficulty
- Time spent in diagnostic reasoning mode

### Skill Transfer
- Improved performance on unseen debugging problems
- Reduced reliance on direct AI answers

---

## 5. Constraints

### Technical Constraints
- Mutations must remain realistic and non-obvious
- Code execution must be sandboxed and secure
- Response time under 3 seconds per challenge

### Educational Constraints
- Must not overwhelm beginners
- Feedback must adapt to skill level
- Focus on logic, not language-specific trivia

---

## 6. MVP Scope (Hackathon)

- Single-language prototype
- Logical Ghost engine for basic control flow bugs
- Dual execution comparison
- AI-guided challenge interface

---

## 7. Future Extensions

- IDE plugin integration
- Multi-language support
- Classroom dashboards for instructors
- Interview preparation modes
