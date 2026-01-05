# Evaluation Criteria for Git Training Exercises

This document provides the assessment criteria for evaluating students who have completed the Git training exercises at Universidad de Granada (UGR).

---

## 📋 Overall Assessment Framework

Each student/group will be evaluated based on five core competencies:

1. **Completion of Exercises** (20%)
2. **Understanding of Concepts** (25%)
3. **Practical Application** (25%)
4. **Problem-Solving Skills** (20%)
5. **Security Practices** (10% - Master of the Universe level only)

---

## 🎯 Detailed Evaluation Criteria

### 1. Completion of Exercises (20 points)

**Excellent (18-20 points)**
- Exercise completed successfully with all parts documented
- All required artifacts submitted (commands, outputs, reflections)
- Outcome branch properly created and pushed to remote
- Clear documentation of all steps taken

**Good (14-17 points)**
- Exercise mostly completed (80-99% of parts)
- Minor missing documentation or artifacts
- Outcome branch created with minor formatting issues
- Generally clear documentation

**Satisfactory (10-13 points)**
- Majority of exercise completed (60-79% of parts)
- Some missing documentation or incomplete outputs
- Outcome branch may have organizational issues
- Documentation needs improvement

**Needs Improvement (0-9 points)**
- Less than 60% of exercise completed
- Significant missing documentation
- Outcome branch incomplete or improperly structured
- Poor documentation quality

---

### 2. Understanding of Concepts (25 points)

**Excellent (22-25 points)**
- Demonstrates deep understanding of Git internals (commits, staging area, references)
- Can explain the "why" behind commands, not just the "how"
- Reflection shows clear comprehension of concepts
- Makes connections between different Git features
- Uses correct Git terminology consistently

**Good (17-21 points)**
- Shows solid understanding of key concepts
- Can explain most concepts clearly
- Reflection demonstrates learning
- Minor terminology or conceptual gaps
- Good grasp of fundamental principles

**Satisfactory (12-16 points)**
- Basic understanding of concepts
- Some confusion about key features
- Reflection is superficial
- Inconsistent use of terminology
- Needs more depth in explanations

**Needs Improvement (0-11 points)**
- Limited understanding of Git concepts
- Cannot explain commands or their effects
- Minimal or no reflection
- Incorrect use of terminology
- Fundamental misunderstandings evident

**Key Concepts by Level**:

**Newbie** (1 comprehensive exercise):
- Working directory, staging area, repository
- Commit history and references
- Local vs. remote repositories
- Branch concept and HEAD pointer
- Basic remote operations (push, pull)

**Intermediate** (1 comprehensive exercise):
- Merge strategies and conflict resolution
- Fast-forward vs. three-way merge
- Conflict markers and resolution techniques
- Tags (lightweight vs. annotated)
- Tag management and pushing tags to remote

**Master** (1 comprehensive exercise):
- Rebase vs. merge (use cases and implications)
- Interactive rebase operations (fixup, squash, reword)
- Commit amending
- History rewriting best practices and dangers
- Git object model and commit SHAs

**Master of the Universe** (1 comprehensive exercise):
- Branch protection policies and rules
- GPG signing and verification
- Git security model
- History rewriting dangers and remediation
- Secret management strategies
- Security auditing

---

### 3. Practical Application (25 points)

**Excellent (22-25 points)**
- Commands used correctly and efficiently
- Demonstrates best practices throughout
- Appropriate command choices for each situation
- Clean, well-organized commit history
- Professional-quality git log and commit messages
- Efficient workflow demonstrated

**Good (17-21 points)**
- Most commands used correctly
- Generally follows best practices
- Appropriate command choices
- Mostly clean commit history
- Good commit messages with minor issues
- Functional workflow

**Satisfactory (12-16 points)**
- Basic commands used correctly
- Some best practices followed
- Some inefficient command choices
- Commit history has organizational issues
- Commit messages need improvement
- Workflow is functional but could be optimized

**Needs Improvement (0-11 points)**
- Frequent command errors
- Poor or no best practices followed
- Inappropriate command choices
- Messy or confusing commit history
- Poor or missing commit messages
- Inefficient or incorrect workflow

**Practical Skills by Level**:

**Newbie** (1 comprehensive exercise):
- Proper use of add, commit, status, log
- Creating and switching branches
- Push and pull operations
- Basic navigation of Git history
- Working with feature branches
- Understanding local vs. remote branches

**Intermediate** (1 comprehensive exercise):
- Effective merge conflict resolution
- Proper tag creation and management
- Understanding different tag types
- Pushing tags to remote
- Reading conflict markers
- Clean merge commit creation

**Master** (1 comprehensive exercise):
- Safe history rewriting (amend, rebase)
- Interactive rebase proficiency
- Understanding commit SHA changes
- Choosing between rebase and merge
- Using --force-with-lease safely
- Creating clean, professional commit histories

**Master of the Universe** (1 comprehensive exercise):
- Configuring branch protection rules
- Setting up GPG signing
- Creating verified commits
- Identifying sensitive data patterns
- Understanding secret remediation approaches
- Implementing security workflows
- Conducting security audits

---

### 4. Problem-Solving Skills (20 points)

**Excellent (18-20 points)**
- Independently resolved all challenges
- Creative and efficient solutions
- Clear documentation of problem-solving process
- Learned from mistakes and adapted approach
- Demonstrates critical thinking
- Researched solutions when needed

**Good (14-17 points)**
- Resolved most challenges with minimal help
- Functional solutions implemented
- Good documentation of problem-solving
- Showed learning from challenges
- Used available resources effectively

**Satisfactory (10-13 points)**
- Resolved basic challenges
- Solutions work but may not be optimal
- Some documentation of problem-solving
- Limited adaptation when facing difficulties
- Basic use of available resources

**Needs Improvement (0-9 points)**
- Struggled with most challenges
- Could not resolve problems independently
- Poor or no documentation of problem-solving
- Did not learn from mistakes
- Did not utilize available resources

**Common Challenges by Level**:

**Newbie** (1 comprehensive exercise):
- Understanding the staging area
- Recovering from mistakes (detached HEAD, wrong commit)
- SSH key configuration issues
- Understanding local vs. remote branches
- Managing feature branches and remote operations

**Intermediate** (1 comprehensive exercise):
- Merge conflicts (especially complex ones)
- Understanding merge commit history
- Identifying and resolving conflict markers
- Understanding different tag types
- Knowing when to use annotated vs. lightweight tags

**Master** (1 comprehensive exercise):
- Rebase conflicts and resolution
- Understanding the implications of history rewriting
- Interactive rebase operations and mistakes
- Choosing between rebase and merge appropriately
- Understanding when force push is safe
- Recovery from bad rebases

**Master of the Universe** (1 comprehensive exercise):
- Configuring GPG properly across platforms
- Understanding branch protection trade-offs
- Identifying sensitive patterns in repository history
- Understanding credential rotation strategies
- Balancing security with usability
- Configuring signed commits in various tools/IDEs
- Hook debugging and execution issues
- Choosing the right branching strategy

**Master of the Universe** (1 comprehensive exercise):
- Configuring GPG properly across platforms
- Understanding branch protection trade-offs
- Identifying sensitive patterns in repository history
- Understanding credential rotation strategies
- Balancing security with usability
- Configuring signed commits in various tools/IDEs

---

### 5. Security Practices (10 points - Master of the Universe only)

**Excellent (9-10 points)**
- Successfully configured GPG signing
- All commits properly signed and verified
- Comprehensive `.gitignore` created
- Understands secret management best practices
- Can identify and remediate security issues
- Demonstrates security-first mindset

**Good (7-8 points)**
- GPG signing configured and working
- Most commits signed
- Good `.gitignore` practices
- Solid understanding of security concepts
- Can identify common security issues

**Satisfactory (5-6 points)**
- Basic GPG setup completed
- Some commits signed
- Basic `.gitignore` present
- Basic understanding of security
- Limited security awareness

**Needs Improvement (0-4 points)**
- GPG signing not working or incomplete
- Few or no signed commits
- Missing or inadequate `.gitignore`
- Poor understanding of security practices
- No demonstrated security awareness

---

## 📊 Grading Scale

| Total Points | Grade | Assessment |
|--------------|-------|------------|
| 90-100 | A (Outstanding) | Exceptional mastery of Git |
| 80-89 | B (Excellent) | Strong competency demonstrated |
| 70-79 | C (Good) | Solid understanding and skills |
| 60-69 | D (Satisfactory) | Basic competency achieved |
| 0-59 | F (Needs Improvement) | Additional practice required |

---

## 📝 Evaluation Process

### Step 1: Review Outcome Branch
1. Checkout the student's outcome branch: `group-X-outcomes/<level>`
2. Review the `OUTCOMES.md` file for completeness
3. Verify the exercise has been documented with all its parts

### Step 2: Verify Technical Execution
1. Review git log to verify commands and workflow:
   ```bash
   git log --all --graph --decorate --oneline
   git log --show-signature  # For Master of the Universe level
   ```
2. Check commit messages for quality and adherence to conventions
3. Verify branch structure and organization
4. Review any artifacts created (hooks, scripts, configuration files)

### Step 3: Assess Understanding
1. Read the reflection section carefully
2. Evaluate the depth of explanations
3. Check for correct use of terminology
4. Assess understanding of concepts vs. rote memorization

### Step 4: Evaluate Problem-Solving
1. Review the challenges section
2. Assess the solutions provided
3. Evaluate the learning demonstrated from challenges
4. Check for independent problem-solving vs. copying solutions

### Step 5: Provide Feedback
1. Complete the evaluation rubric
2. Provide specific, actionable feedback
3. Highlight strengths and areas for improvement
4. Suggest next steps for continued learning

---

## 💬 Feedback Template

```markdown
## Evaluation Feedback for [Student/Group Name]

**Level**: [Level completed]
**Date**: [Evaluation date]
**Evaluator**: [Instructor name]

### Overall Score: [X/100] - Grade: [Letter Grade]

---

### Strengths:
- [Specific strength 1]
- [Specific strength 2]
- [Specific strength 3]

### Areas for Improvement:
- [Specific area 1 with actionable advice]
- [Specific area 2 with actionable advice]
- [Specific area 3 with actionable advice]

### Detailed Scores:

| Criterion | Score | Comments |
|-----------|-------|----------|
| Completion of Exercises | [X/20] | [Specific comments] |
| Understanding of Concepts | [X/25] | [Specific comments] |
| Practical Application | [X/25] | [Specific comments] |
| Problem-Solving Skills | [X/20] | [Specific comments] |
| Security Practices | [X/10] | [Specific comments - Master of Universe only] |
| **Total** | **[X/100]** | |

### Recommendations:
- [Recommendation 1]
- [Recommendation 2]
- [Suggestion for next level or additional practice]

### Next Steps:
- [Suggested next level or additional challenges]
- [Resources for further learning]

---

**Approved for**: ✅ Next Level / 🔄 Additional Practice Recommended / ❌ Needs Redo
```

---

## 🎓 Level Progression Guidelines

Students should achieve the following minimum scores to progress:

- **To advance to Intermediate**: Minimum 70/100 on Newbie level
- **To advance to Master**: Minimum 75/100 on Intermediate level
- **To advance to Master of Universe**: Minimum 80/100 on Master level
- **To complete training**: Minimum 85/100 on Master of Universe level

---

## 📚 Additional Notes for Evaluators

1. **Be Constructive**: Focus on growth and learning, not just errors
2. **Be Specific**: Provide concrete examples in feedback
3. **Be Fair**: Apply criteria consistently across all students
4. **Be Encouraging**: Recognize effort and improvement
5. **Be Educational**: Use evaluation as a teaching opportunity

---

**Last Updated**: November 29, 2025
