# Build-a-thon Game Mechanics Guide
## Running Effective Gamified Training Sessions

### Pre-Session Setup

#### Materials Needed
- Quiz platform (Kahoot, Teams, or custom Ignition project)
- Timer (for lightning rounds)
- Scoreboard (digital or whiteboard)
- Prize inventory (badges, certificates, small rewards)
- Session theme music (optional but fun!)

#### Room Setup
- Main display for questions
- Team seating arrangements
- "Phone parking" area for focus
- Refreshments station

### Session Structure (45 minutes)

#### 1. Opening Ceremony (5 minutes)
- Welcome adventurers to today's realm
- Recap previous session's champions
- Announce today's special challenges
- Review rules and scoring

#### 2. Warm-up Round (5 minutes)
- 5 quick-fire questions from previous realms
- Individual answers
- No penalties for wrong answers
- Gets everyone engaged

#### 3. Main Quest (20 minutes)

**Round 1: Individual Glory (10 min)**
- 10 questions from current realm
- Increasing difficulty
- Individual scoring
- Show leaderboard after every 3 questions

**Round 2: Team Alliance (10 min)**
- 5 complex scenarios
- Teams collaborate
- Bonus points for explanation quality
- Encourage discussion

#### 4. Boss Battle (10 minutes)
- One complex, multi-part challenge
- Teams compete
- Can use "lifelines":
  - Ask the Instructor (once per session)
  - Poll the Room (once per session)
  - 50/50 (twice per session)

#### 5. Victory Lap (5 minutes)
- Announce winners
- Award badges/achievements
- Preview next session
- Collect feedback

### Scoring System Details

#### Base Points
- Beginner: 100 points
- Intermediate: 250 points
- Advanced: 500 points
- Boss Battle: 1000 points

#### Multipliers
- Speed Bonus: Answer in <30 seconds = 1.5x
- Perfect Streak: 3 correct in a row = 2x on next question
- Comeback Kid: From last to first place = 500 bonus points

#### Penalties
- Wrong answer: -50 points (optional)
- Using lifeline: -25 points
- Phone use during round: -100 points

### Achievement System

#### Individual Badges
- **First Blood**: First correct answer of the session
- **Speed Demon**: 5 questions answered in <20 seconds
- **Perfectionist**: 100% accuracy in a session
- **Comeback Kid**: Biggest score improvement
- **Helper**: Assisted teammates 3+ times

#### Team Achievements
- **Synergy**: All team members contribute to Boss Battle
- **Flawless Victory**: Perfect score on team round
- **Creative Solution**: Unique approach to problem
- **Realm Master**: Complete all questions in a realm

#### Legendary Achievements (Multi-session)
- **Grand Master**: Top scorer for 5 consecutive sessions
- **Realm Walker**: Completed all 8 realms
- **The Mentor**: Helped others achieve 10 badges
- **Speed Lord**: 50 total speed bonuses
- **Lore Keeper**: Perfect attendance

### Facilitation Tips

#### Keep Energy High
- Use countdown timers with sound
- Celebrate correct answers enthusiastically
- Play theme music during thinking time
- Stand and move around the room

#### Encourage Participation
- Call on quiet team members
- Rotate who answers for teams
- Bonus points for good questions
- Celebrate creative wrong answers

#### Handle Challenges
- **Disputes**: Have documentation ready
- **Technical issues**: Have backup questions
- **Dominant players**: Use team rotation rules
- **Struggling players**: Pair with mentors

### Platform-Specific Instructions

#### Using Kahoot
1. Create quiz with images for visual interest
2. Set appropriate time limits (30-60 seconds)
3. Enable "Show questions on player devices"
4. Use team mode for collaboration rounds
5. Export results for tracking

#### Using Microsoft Forms
1. Create sections for each difficulty level
2. Use branching for adaptive difficulty
3. Enable "Show results after submission"
4. Set up automatic grading
5. Use Forms analytics for insights

#### Building in Ignition
```python
# Sample quiz component structure
def loadQuestion(questionNum):
    question = getQuestion(questionNum)
    self.custom.currentQuestion = question.text
    self.custom.answers = question.answers
    self.custom.correctAnswer = question.correct
    self.custom.points = question.points
    self.custom.timeLimit = question.timeLimit
    startTimer()

def checkAnswer(selectedAnswer):
    if selectedAnswer == self.custom.correctAnswer:
        addPoints(self.custom.points * getSpeedMultiplier())
        showCorrectAnimation()
    else:
        showIncorrectAnimation()
    loadNextQuestion()
```

### Data Tracking

#### Individual Metrics
- Questions attempted/correct
- Average answer time
- Favorite categories
- Achievement progress
- Skill gaps identified

#### Team Metrics
- Collaboration effectiveness
- Combined knowledge areas
- Team chemistry score
- Progress velocity

#### Session Analytics
- Most missed questions
- Average engagement score
- Difficulty progression
- Time management

### Reward Store

#### Point Redemption
- 1000 points: Ignition sticker
- 2500 points: Coffee mug
- 5000 points: Ignition T-shirt
- 10000 points: Lunch with CTO
- 25000 points: ICC ticket discount

### Special Event Ideas

#### Monthly Tournaments
- All-realm challenge
- Elimination brackets
- Live streaming option
- Grand prizes

#### Theme Days
- Retro Gaming Style
- Superhero Powers (special abilities)
- Time Attack Mode
- Reverse Quiz (give answer, guess question)

#### Guest Challenges
- Vendor representatives
- Customer success stories
- Build-a-thon alumni
- Executive participation

### Virtual Session Adaptations

#### Tools
- Breakout rooms for team rounds
- Poll functionality for answers
- Screen annotation for explanations
- Virtual backgrounds for realm themes

#### Engagement Tactics
- Cameras on for lightning rounds
- Emoji reactions for answers
- Chat for team communication
- Virtual hand raises for help

### Success Metrics

#### Short-term (Weekly)
- Attendance rate >90%
- Average score improvement >10%
- Engagement score >4/5
- Questions submitted by players

#### Long-term (Monthly)
- Skill assessment improvements
- Real project application stories
- Team collaboration increase
- Build-a-thon readiness score

### Continuous Improvement

#### Feedback Collection
- Post-session quick survey
- Monthly detailed feedback
- Question difficulty ratings
- New topic suggestions

#### Content Updates
- Add new questions weekly
- Rotate question sets
- Update with latest Ignition features
- Include real-world scenarios

Remember: The goal is learning through fun. If players are engaged and improving, you're succeeding!