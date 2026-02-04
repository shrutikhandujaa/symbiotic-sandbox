# Symbiotic Sandbox - System Design Document

## Project Overview

**Symbiotic Sandbox** is an AI-powered adversarial tutor that enhances learning by strategically introducing logical flaws into learner code, then guiding them through diagnosis and resolution. The system creates a symbiotic relationship where AI challenges push learners to develop stronger debugging and critical thinking skills.
The system is designed to explicitly combat the illusion of competence created by passive AI coding tools by forcing learners to reason about failure.


## 1. Architecture Overview

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Web Frontend  │    │  Backend API    │    │  AI Engine      │
│                 │◄──►│                 │◄──►│                 │
│ - Code Editor   │    │ - Session Mgmt  │    │ - Code Analysis │
│ - Chat Interface│    │ - User Progress │    │ - Mutation Gen  │
│ - Progress View │    │ - Code Storage  │    │ - Hint System   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │    Database     │
                       │                 │
                       │ - User Sessions │
                       │ - Code History  │
                       │ - Progress Data │
                       └─────────────────┘
```

## 2. Core Components

### 2.1 Frontend (React/TypeScript)
- **Code Editor**: Monaco Editor with syntax highlighting and error detection
- **Chat Interface**: Real-time conversation with AI tutor
- **Progress Dashboard**: Visual feedback on learning milestones
- **Challenge Browser**: Library of coding challenges by difficulty/topic

### 2.2 Backend API (Node.js/Express)
- **Session Management**: Track user progress and maintain context
- **Code Execution**: Sandboxed environment for running user code
- **Progress Analytics**: Learning pattern analysis and recommendations
- **Authentication**: Simple user accounts and session persistence

### 2.3 AI Engine (Python/OpenAI API)
- **Code Analyzer**: AST parsing to understand code structure and logic
- **Mutation Generator**: Strategic flaw injection based on learning objectives
- **Hint System**: Contextual guidance without giving away solutions
- **Progress Evaluator**: Assessment of user debugging skills

### 2.4 Database (PostgreSQL)
- User profiles and authentication
- Code submission history
- Learning progress metrics
- Challenge templates and solutions

## 3. Logical Ghost Mutation Strategy

### 3.1 Mutation Categories

**Foundational Ghosts** (Beginner)
- Simple conditional mistakes
- Misordered logic
- Incorrect variable initialization

Note: Pure syntax errors are intentionally minimized to keep focus on reasoning rather than tooling.

**Logic Ghosts** (Intermediate)
- Off-by-one errors in loops
- Incorrect conditional operators
- Variable scope issues

**Semantic Ghosts** (Advanced)
- Race conditions in async code
- Memory leaks
- Edge case handling failures

### 3.2 Adaptive Mutation Selection
```python
def select_mutation(user_skill_level, code_complexity, learning_objective):
    mutations = filter_by_difficulty(ALL_MUTATIONS, user_skill_level)
    relevant = filter_by_context(mutations, code_complexity)
    return prioritize_by_objective(relevant, learning_objective)
```

### 3.3 Mutation Injection Process
1. **Code Analysis**: Parse AST to identify injection points
2. **Context Evaluation**: Assess code complexity and user skill level
3. **Strategic Selection**: Choose mutations that align with learning goals
4. **Subtle Integration**: Inject flaws that require genuine debugging skills
5. **Validation**: Ensure mutations create meaningful learning opportunities

## 4. Execution Flow

### 4.1 Session Initialization
```
User submits code → AI analyzes structure → Selects appropriate mutations
                                        ↓
User receives "ghosted" code ← AI injects logical flaws ← Validates mutation impact
```

### 4.2 Interactive Debugging Loop
```
User identifies issue → Proposes fix → AI evaluates solution
        ↑                               ↓
Receives targeted hint ← AI provides guidance ← Solution incorrect/incomplete
        ↑                               ↓
Process repeats until ← User learns concept ← Solution correct
```

### 4.3 Progress Tracking
- **Skill Metrics**: Track debugging speed, accuracy, and pattern recognition
- **Adaptive Difficulty**: Automatically adjust mutation complexity
- **Learning Insights**: Identify knowledge gaps and recommend focus areas

## 5. Technical Feasibility

### 5.1 MVP Implementation (48 hours)
**Core Features**:
- Basic code editor with JavaScript support
- Simple mutation injection (syntax errors, logic flaws)
- Chat interface with OpenAI integration
- Local storage for session persistence

**Technology Stack**:
- Frontend: React + Monaco Editor
- Backend: Node.js + Express
- AI: OpenAI API for code analysis and hints
- Storage: Local storage (MVP) → PostgreSQL (production)


### Hackathon MVP Focus

For the hackathon, Symbiotic Sandbox focuses on demonstrating the core innovation rather than full platform breadth.

The MVP intentionally limits scope to:
- A single programming language (JavaScript)
- A small, curated set of Logical Ghost mutations
- One-on-one adversarial debugging sessions
- Local or lightweight persistence

This ensures technical feasibility while clearly showcasing the adversarial tutoring concept.


### 5.2 Technical Challenges & Solutions

**Challenge**: Real-time code analysis
**Solution**: Implement debounced AST parsing with Web Workers

**Challenge**: Secure code execution
**Solution**: Use Docker containers or web-based sandboxing (CodeMirror)

**Challenge**: Intelligent mutation selection
**Solution**: Rule-based system with predefined mutation patterns

### 5.3 Scalability Considerations
- **Caching**: Store common code patterns and mutation results
- **Load Balancing**: Distribute AI processing across multiple instances
- **Database Optimization**: Index user progress data for quick retrieval

## 6. Future Extensions

### 6.1 Enhanced AI Capabilities
- **Multi-language Support**: Extend beyond JavaScript to Python, Java, C++
- **Advanced Mutations**: Complex algorithmic flaws, performance issues
- **Personalized Learning**: ML-driven adaptation to individual learning styles

### 6.2 Collaborative Features
- **Peer Review**: Students debug each other's "ghosted" code
- **Instructor Dashboard**: Teachers can create custom challenges
- **Team Challenges**: Collaborative debugging exercises

### 6.3 Integration Opportunities
- **IDE Plugins**: VS Code extension for seamless workflow
- **LMS Integration**: Canvas, Blackboard compatibility
- **Assessment Tools**: Automated grading based on debugging performance

## 7. Success Metrics

### 7.1 User Engagement
- Session duration and frequency
- Challenge completion rates
- User retention over time

### 7.2 Learning Effectiveness
- Debugging skill improvement (pre/post assessment)
- Reduced time to identify common error patterns
- Increased confidence in code review

### 7.3 Technical Performance
- Response time for AI analysis (<2 seconds)
- System uptime and reliability (>99%)
- Successful mutation injection rate (>95%)

## 8. Risk Mitigation

**Risk**: AI generates unhelpful or confusing mutations
**Mitigation**: Curated mutation library with human validation

**Risk**: Users become frustrated with difficulty
**Mitigation**: Adaptive difficulty scaling and clear progress indicators

**Risk**: Technical complexity exceeds hackathon timeline
**Mitigation**: Prioritized feature list with clear MVP boundaries

---

*This design balances ambitious vision with practical execution, ensuring Symbiotic Sandbox can deliver meaningful value within hackathon constraints while establishing a foundation for future growth.*