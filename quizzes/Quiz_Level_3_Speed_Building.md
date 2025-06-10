# Build-a-thon Actual Challenge Quiz - Level 3: Integration & Speed Building
## Based on Real Past Challenges

### Complex Integration Scenarios (Build-a-thon Finals Style)

1. **Multi-System Dashboard** (Like 2024 Finals)
   Build a convenience store monitoring system with:
   - Gas pump status from OPC
   - Car wash availability from REST API  
   - Food mart inventory from database
   - Weather data affecting sales
   
   **Question**: What's the optimal data flow architecture?
   **Answer**: 
   - Gateway Timer Scripts for REST/Weather (cache in tags)
   - Direct OPC tags for real-time pump status
   - Query tags for inventory (5-min refresh)
   - Perspective dashboard with role-based views

2. **Cross-Site Data Aggregation**
   5 sites, each with local Ignition, need corporate dashboard
   
   **Question**: Best approach for real-time KPIs?
   **Answer**: Gateway Network with Remote Tag Providers

3. **Mobile + Desktop Unified Experience**
   Operators need desktop HMI, managers need mobile dashboards
   
   **Question**: Single project or multiple?
   **Answer**: Single Perspective project with responsive breakpoints

### Speed Building Techniques

4. **UDT Speed Creation**
   Create UDT for 50 identical pumps in 2 minutes
   
   **Question**: Fastest method?
   **Answer**: 
   1. Create one UDT definition
   2. Use CSV import or scripting to create instances
   3. Or copy/paste in designer with find/replace

5. **Bulk Tag Creation via Script**
   ```python
   # Create 100 memory tags named Tank_001 to Tank_100
   ```
   **Question**: Complete the script
   **Answer**:
   ```python
   basePath = "[default]Tanks"
   for i in range(1, 101):
       tagPath = f"{basePath}/Tank_{i:03d}"
       system.tag.configure(tagPath, {
           "valueSource": "memory",
           "dataType": "Float8",
           "value": 0.0
       })
   ```

6. **Rapid View Duplication**
   Need 10 similar Perspective views with slight variations
   
   **Question**: Fastest approach?
   **Answer**: Create base view with parameters, use embedded views

### Fantasy Challenge Integration (2024 Style)

7. **Dragon Flight Path Optimizer**
   Dragon must visit 5 locations, minimize distance
   Given coordinates array: [(0,0), (3,4), (6,0), (3,-4), (0,0)]
   
   **Question**: Calculate shortest path distance
   **Answer**: 20 units (traveling salesman problem)

8. **Kraken Attack Predictor**
   Kraken appears when: wave_height > 10 AND wind_speed > 25
   
   **Question**: Write the expression tag
   **Answer**: `{[.]wave_height} > 10 && {[.]wind_speed} > 25`

9. **Magical Tome Page Sequencer**
   Pages must be read in order based on clues
   Page clues: "After BEGIN", "Before END", "After MIDDLE"
   
   **Question**: Correct sequence?
   **Answer**: BEGIN → MIDDLE → "After MIDDLE" → END

### Performance Under Pressure

10. **15-Second Alarm Display**
    Show all active alarms with acknowledge button
    
    **Question**: Quickest component setup?
    **Answer**: Alarm Status Table with default ack column enabled

11. **30-Second Trend Setup**
    Display last hour of data for 5 tags
    
    **Question**: Fastest configuration?
    **Answer**: Easy Chart in Historical mode, drag tags directly

12. **1-Minute Login Screen**
    Username, password, login button, error display
    
    **Question**: Minimum components needed?
    **Answer**: 2 text fields, 1 button, 1 label, script on button

### Architecture Decisions (Finals-Level)

13. **Store & Forward Setup**
    Plant has intermittent internet, need to ensure no data loss
    
    **Question**: Critical settings?
    **Answer**: 
    - Enable S&F on history providers
    - Set appropriate buffer size
    - Configure retry intervals

14. **Load Balancing Strategy**
    10,000 clients expected, single gateway struggling
    
    **Question**: Best architecture?
    **Answer**: Frontend/Backend split with multiple frontend gateways

15. **Redundancy Planning**
    Zero-downtime requirement for critical process
    
    **Question**: Minimum setup needed?
    **Answer**: 
    - Redundant gateway pair
    - Redundant database
    - Multiple OPC connections
    - Client failover configured

### Rapid Problem Solving

16. **Emergency Debug**: Views show "Error_Configuration"
    **Question**: First thing to check?
    **Answer**: Gateway logs and browser console

17. **Quick Performance Fix**: Tags updating slowly
    **Question**: Check scan class or?
    **Answer**: Leased scan class with no subscribers

18. **Security Crisis**: Need to lock down project NOW
    **Question**: Fastest method?
    **Answer**: Disable all user sources except admin

19. **Data Recovery**: Accidentally deleted tags
    **Question**: Recovery option?
    **Answer**: Gateway backup or audit logs

20. **Integration Failed**: REST endpoint returns 403
    **Question**: Likely cause?
    **Answer**: Authentication token expired or missing

### Boss Battle Scenarios

21. **The 5-Minute Challenge**
    Build complete tank monitoring with:
    - Level display (0-100%)
    - High/Low alarms
    - Trend of last hour
    - Fill/Drain buttons
    
    **Question**: Component priority order?
    **Answer**: 
    1. Create tank level tag
    2. Add cylindrical tank component
    3. Configure alarms on tag
    4. Add trend
    5. Add buttons with scripts

22. **The Integration Gauntlet**
    Connect to:
    - Modbus device (address 40001)
    - REST API (needs auth)
    - SQL database (stored procedure)
    - MQTT broker (topic: sensors/+/temp)
    
    **Question**: Parallel or sequential setup?
    **Answer**: Parallel - assign team members to each