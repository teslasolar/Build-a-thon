# Build-a-thon Actual Challenge Quiz - Level 2: Technical Implementation
## Based on Real Past Challenges

### HTTP/Web Challenges (From 2022)

1. **POST Request Challenge** (Actual 2022)
   You navigate to a URL and see: "Please POST your team name to continue"
   
   **Question**: Which Ignition script function would work?
   ```python
   A) system.net.httpGet(url, params)
   B) system.net.httpPost(url, data)
   C) system.net.httpClient.post(url, headers, data)
   D) system.web.post(url, data)
   ```
   **Answer**: C) system.net.httpClient.post(url, headers, data)

2. **REST API Authentication**
   Challenge URL requires: Bearer token in header
   
   **Question**: How do you add the authorization header?
   ```python
   headers = {
       "Authorization": "Bearer YOUR_TOKEN",
       "Content-Type": "application/json"
   }
   ```
   **Answer**: Include in headers parameter of httpClient

3. **URL Parameter Extraction**
   Given: `http://challenge.com/api?code=IGN2024&team=5`
   
   **Question**: Extract the code parameter value
   **Answer**: IGN2024

### Database Optimization (From Multiple Years)

4. **Slow Query Fix** (Common Challenge Type)
   ```sql
   SELECT * FROM production_data p
   WHERE p.timestamp > '2024-01-01'
   AND p.machine_id IN (
       SELECT id FROM machines WHERE area = 'A'
   )
   ```
   
   **Question**: What's the optimization?
   **Answer**: Use JOIN instead of subquery:
   ```sql
   SELECT p.* FROM production_data p
   JOIN machines m ON p.machine_id = m.id
   WHERE p.timestamp > '2024-01-01' AND m.area = 'A'
   ```

5. **Index Strategy**
   Table: 1 million rows, queries filter by timestamp and status
   
   **Question**: What index would help most?
   **Answer**: Composite index on (timestamp, status)

### Script Debugging (From 2022-2023)

6. **Fix the Script** (Common Challenge)
   ```python
   def calculate_efficiency(good, total):
       efficiency = good / totl * 100  # Bug 1
       if efficiency > 100  # Bug 2
           return 100
       return round(efficency, 2)  # Bug 3
   ```
   
   **Question**: Identify all 3 bugs
   **Answer**: 
   - Bug 1: 'totl' should be 'total'
   - Bug 2: Missing colon after if statement
   - Bug 3: 'efficency' should be 'efficiency'

7. **Gateway vs Client Scope Error**
   ```python
   # This runs in Gateway scope
   def updateDisplay():
       window = system.gui.getWindow('Main')
       window.rootContainer.label.text = "Updated"
   ```
   
   **Question**: Why does this fail?
   **Answer**: system.gui functions don't work in Gateway scope

### Component Challenges (From 2022)

8. **Memory Game Logic**
   Create a 4x4 grid of buttons that reveal pairs
   
   **Question**: What property tracks if a button is revealed?
   **Answer**: Use custom property on each button (e.g., button.custom.revealed)

9. **Trend Annotation** (2022 Challenge)
   Add marker at highest value on trend
   
   **Question**: Which scripting function finds max value in dataset?
   **Answer**: max() on column data or system.dataset functions

10. **Split Container Dynamics**
    Container should resize based on window width
    
    **Question**: What property controls split position?
    **Answer**: dividerLocation property (pixels or percentage)

### Integration Challenges

11. **MQTT Topic Parse** (2023 Reference)
    Topic: `plant/area/machine/sensor/temperature`
    
    **Question**: Extract machine identifier
    **Answer**: Split by '/' and get index 2

12. **Modbus Address Calculation**
    Holding Register 40001, need to read 10 consecutive
    
    **Question**: What's the address range?
    **Answer**: 40001-40010 (or 0-9 in Modbus addressing)

### Performance Optimization

13. **Tag Read Optimization**
    Need to read 100 tags every second
    
    **Question**: Best approach?
    ```python
    A) Loop with system.tag.read() 100 times
    B) system.tag.readBlocking() with all paths
    C) Create expression tags
    D) Use transaction group
    ```
    **Answer**: B) system.tag.readBlocking() with all paths

14. **View Loading Speed**
    Perspective view with 50 bindings loads slowly
    
    **Question**: Best optimization?
    **Answer**: Use indirect bindings or load data via script on startup

15. **Query Cache Strategy**
    Same query runs every 5 seconds from 10 clients
    
    **Question**: How to reduce database load?
    **Answer**: Use Gateway timer script to query once, store in tags

### Rapid Fire Technical

16. Default Perspective session timeout?
    **Answer**: 900 seconds (15 minutes)

17. Max WebSocket message size?
    **Answer**: 64KB default

18. Tag history partition period default?
    **Answer**: Monthly

19. Maximum concurrent designers?
    **Answer**: Unlimited (by default)

20. OPC DA vs OPC UA main difference?
    **Answer**: UA is platform-independent, DA is Windows-only