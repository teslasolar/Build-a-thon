# Build-a-thon 2025 Elimination Challenge Examples
## Based on Previous Years' Actual Challenges

### Historical Context
- **2024**: 26 teams, August 1st (Thursday) - Fantasy theme with kraken, magical tome, Sphinx riddles
- **2023**: 33 teams, July 18th (Tuesday) - 11 challenges covering MQTT, drivers, scripting
- **2022**: Multi-round format with puzzle/riddle focus
- **2025**: Expected August 7th (Thursday) - Following pattern of early August

### Confirmed Challenge Types from Past Events

#### 1. **Fantasy/Story Elements** (2023-2024)
- Navigate through "Lands of Ignition" map
- Evade mythical creatures (kraken)
- Interact with magical items (tome)
- Solve riddles from characters (Sphinx)
- Work with allies (flying dragon)

#### 2. **Code/Script Puzzles**
- **Ignition Logo Script** (2022): Code shaped like the Ignition logo
- **Hidden Messages**: Decode values stored in tags
- **Script Debugging**: Fix intentionally broken scripts
- **Pattern Recognition**: Identify patterns in code

#### 3. **Architecture & Design**
- **Hub & Spoke Question** (2022): Calculate server connections
- **System Design**: Design architecture for specific scenarios
- **Module Selection**: Choose appropriate modules for requirements

#### 4. **Technical Implementation**
- **HTTP Challenges** (2022): 
  - Given URL requiring POST instead of GET
  - Need tools like Postman or scripting
- **Database Queries**: Fix or optimize slow queries
- **Image Puzzles**: Unscramble images to reveal codes

#### 5. **Component Challenges**
- **Memory Game** (2022): Recreation in Ignition
- **Split Container**: Article/word highlighting
- **Trend Annotations**: Working with charts
- **Exchange Trading Post** (2024): Resource management

#### 6. **Knowledge Tests**
- **Ignition Trivia**: Historical facts, features
- **Module Expertise**: MQTT, drivers, scripting
- **Best Practices**: Performance, security

### Specific Examples to Practice

#### Challenge Type 1: Script Shape Puzzle
```python
# Practice: Create ASCII art that's also valid Python
#     I G N I T I O N
#    def get_code():
#   return "ANSWER"
# Hidden in shape!
```

#### Challenge Type 2: HTTP POST Challenge
```python
# You receive: "Please POST your team name to continue"
# Solution approach:
import system.net.httpClient
response = system.net.httpClient.post(
    "https://challenge-url.com",
    {"Content-Type": "application/json"},
    {"team": "YourTeamName"}
)
```

#### Challenge Type 3: Tag Decode Challenge
```
Tags created:
Tag1: 72
Tag2: 101
Tag3: 108
Tag4: 108
Tag5: 111

Hint: "ASCII speaks volumes"
Solution: Decode ASCII values = "Hello"
```

#### Challenge Type 4: Architecture Math
```
Question: "5 sites, hub-and-spoke, redundant connections"
- Each site connects to 2 hubs
- Hubs connect to each other
- Calculate total connections
```

#### Challenge Type 5: Database Performance
```sql
-- Slow query provided:
SELECT * FROM production_data 
WHERE timestamp > '2024-01-01' 
AND machine_id IN (
    SELECT id FROM machines 
    WHERE area = 'Building A'
)
-- Fix with indexes and joins
```

### Speed Optimization Strategies

#### For Puzzle Challenges
1. **Pattern Recognition Team**: One person looks for patterns
2. **Documentation Scanner**: Quick search through manuals
3. **Code Runner**: Tests solutions immediately
4. **Note Taker**: Tracks attempted solutions

#### For Technical Challenges
1. **Pre-load Tools**:
   - Postman or REST client
   - SQL query analyzer
   - Python IDE
   - ASCII/encoding tables
   - Ignition Designer

2. **Quick References**:
   - Common HTTP headers
   - SQL optimization tricks
   - Python string methods
   - Ignition scripting functions

### 2025 Preparation Recommendations

#### Technical Skills to Master
- HTTP methods (GET, POST, PUT, DELETE)
- ASCII/Unicode encoding
- Basic cryptography (Caesar cipher, etc.)
- SQL query optimization
- Python string manipulation
- Ignition component properties

#### Puzzle-Solving Skills
- Pattern recognition
- Code reading (even obfuscated)
- Lateral thinking
- Speed reading documentation
- Quick math calculations

#### Team Coordination
- Assign specialists:
  - Database expert
  - Scripting guru
  - Puzzle solver
  - Documentation searcher
- Practice handoffs between challenges

### Mock Challenge Set

Try this 90-minute practice session:

1. **The Encoded Gateway** (10 min)
   - Create 5 memory tags with values: 66, 117, 105, 108, 100
   - Decode the message

2. **The POST Portal** (15 min)
   - Set up endpoint that only accepts POST
   - Send team credentials

3. **Script Shape Shifter** (20 min)
   - Write Python that draws Ignition logo
   - Must also execute and return value

4. **Database Dungeon** (15 min)
   - Optimize query joining 5 tables
   - Must run in < 1 second

5. **Component Constellation** (20 min)
   - Arrange components to form pattern
   - Pattern reveals next clue

6. **The Final Calculation** (10 min)
   - Architecture math problem
   - Sites, redundancy, connections

### Remember for 2025
- Fantasy theme likely continues
- Expect 11 challenges
- First 2 teams to finish win
- **August 7th, 2025** (likely date - first Thursday)
- Mix of puzzles and technical skills
- Speed is EVERYTHING

Good luck with your 2025 Build-a-thon preparation!