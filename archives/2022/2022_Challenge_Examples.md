# Build-a-thon 2022 Elimination Challenge Examples

## Challenge Format
- Multi-round format with puzzle/riddle focus
- Heavy emphasis on code puzzles and architecture questions

## Specific Challenges

### 1. Ignition Logo Script
- **Challenge**: Code shaped like the Ignition logo
- **Type**: Visual code puzzle
- **Solution**: The code must be arranged to visually represent the Ignition logo while still being executable Python

### 2. Hub & Spoke Architecture Question
- **Challenge**: Calculate server connections in a hub-and-spoke architecture
- **Details**: Given a specific number of sites and redundancy requirements, calculate total connections
- **Key Skill**: Understanding Ignition architecture patterns

### 3. HTTP Challenge
- **Challenge**: Given URL requiring POST instead of GET
- **Tools Needed**: Postman or scripting knowledge
- **Example Solution**:
```python
import system.net.httpClient
response = system.net.httpClient.post(
    "https://challenge-url.com",
    {"Content-Type": "application/json"},
    {"team": "YourTeamName"}
)
```

### 4. Memory Game
- **Challenge**: Recreation of a memory game in Ignition
- **Skills**: Component manipulation, scripting
- **Focus**: Quick implementation of interactive components

## Key Takeaways from 2022
- Strong focus on puzzle-solving and lateral thinking
- HTTP/REST knowledge was crucial
- Architecture understanding tested heavily
- Visual/spatial puzzles were common
