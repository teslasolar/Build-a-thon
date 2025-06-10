# Tag Temple Quiz Questions
## Realm 3: Tag Types, UDTs, and Tag Scripts

### Beginner Level (100 points each)

1. **Question**: What are the main tag types in Ignition?
   - A) OPC, Memory, Expression, Query
   - B) Integer, Float, String, Boolean
   - C) Input, Output, Memory, System
   - D) Read, Write, ReadWrite, Subscribe
   **Answer**: A) OPC, Memory, Expression, Query

2. **Question**: What does UDT stand for?
   - A) Universal Data Type
   - B) User Defined Type
   - C) Unified Data Template
   - D) User Data Tag
   **Answer**: B) User Defined Type

3. **Question**: Which tag type automatically updates based on a schedule?
   - A) OPC Tag
   - B) Query Tag
   - C) Memory Tag
   - D) Reference Tag
   **Answer**: B) Query Tag

4. **Question**: What is a tag's "deadband"?
   - A) The range where the tag is inactive
   - B) The amount a value must change before updating
   - C) The time between updates
   - D) The error margin
   **Answer**: B) The amount a value must change before updating

5. **Question**: What are the three components of a Qualified Value?
   - A) Name, Value, Type
   - B) Value, Quality, Timestamp
   - C) Tag, Data, Time
   - D) Current, Previous, Change
   **Answer**: B) Value, Quality, Timestamp

### Intermediate Level (250 points each)

6. **Question**: What's the purpose of tag history deadband modes?
   - A) Absolute: Fixed value change, Percent: Percentage of range
   - B) To reduce database storage
   - C) To improve query performance
   - D) All of the above
   **Answer**: D) All of the above

7. **Question**: In a UDT, what's the difference between a parameter and a tag?
   - A) Parameters are configuration values, tags are runtime values
   - B) Parameters can't change after creation
   - C) Tags are always OPC, parameters are always memory
   - D) No difference, just naming convention
   **Answer**: A) Parameters are configuration values, tags are runtime values

8. **Question**: What happens when you edit a UDT definition?
   - A) Nothing until you manually update instances
   - B) All instances update immediately
   - C) Instances update on next Gateway restart
   - D) Only new instances use the new definition
   **Answer**: B) All instances update immediately

9. **Question**: Which scan class mode is most efficient for tags that change infrequently?
   - A) Direct
   - B) Driven
   - C) Leased
   - D) Polled
   **Answer**: C) Leased

10. **Question**: How do you reference a UDT parameter in an expression?
    - A) {ParameterName}
    - B) [ParameterName]
    - C) ${ParameterName}
    - D) @ParameterName
    **Answer**: A) {ParameterName}

### Advanced Level (500 points each)

11. **Question**: What's the execution context difference between Tag Event Scripts and Gateway Tag Change Scripts?
    - A) Tag Event Scripts run per-tag, Gateway Tag Change monitors multiple
    - B) Gateway scripts are faster
    - C) Tag Event Scripts support more events
    - D) Both A and C
    **Answer**: D) Both A and C

12. **Question**: When using indirect tag binding with UDT parameters, what's the correct syntax?
    - A) [default]{InstanceName}/{TagName}
    - B) {PathParameter}/{TagName}
    - C) tag({InstanceName}/{TagName})
    - D) {1}/{2} with parameters
    **Answer**: B) {PathParameter}/{TagName}

13. **Question**: What's the most efficient way to read 1000 UDT instance values?
    - A) Loop with system.tag.read()
    - B) system.tag.readBlocking() with all paths
    - C) system.tag.browse() with recursive option
    - D) Create expression tags
    **Answer**: B) system.tag.readBlocking() with all paths

14. **Question**: In tag history, what's the difference between "analog" and "discrete" compression?
    - A) Analog uses deadband, discrete records all changes
    - B) Analog is for numbers, discrete for booleans
    - C) Analog compresses more aggressively
    - D) Discrete only stores 0 and 1
    **Answer**: A) Analog uses deadband, discrete records all changes

15. **Question**: What happens to tag history when you change a tag's data type?
    - A) History is deleted
    - B) History is preserved but may not query correctly
    - C) Automatic conversion occurs
    - D) New partition is created
    **Answer**: B) History is preserved but may not query correctly

### Boss Battle Questions (1000 points)

16. **Design Challenge**: You have 10,000 similar devices to monitor. What's the optimal tag structure?
    - A) Flat structure with naming convention
    - B) UDT with instances in folders by area
    - C) Individual tags with tag groups
    - D) Dynamic tags created by script
    **Answer**: B) UDT with instances in folders by area

17. **Troubleshooting**: Tags are updating slowly despite 1-second scan class. What's the likely cause?
    - A) OPC server is overloaded
    - B) Scan class is set to "Leased" with no subscribers
    - C) Database is slow
    - D) Both A and B are possible
    **Answer**: D) Both A and B are possible

### Lightning Round (50 points, 20-second timer)

18. What's the default tag history provider name?
    **Answer**: default (or your configured name)

19. True/False: Expression tags can write to other tags
    **Answer**: False (they're read-only)

20. Maximum nested UDT depth?
    **Answer**: No hard limit (practical considerations)

21. Tag quality code for "Good"?
    **Answer**: 192

22. Can reference tags point to tags on other Gateways?
    **Answer**: Yes (with Gateway Network)

### Practical Challenges

23. **UDT Creation** (5 minutes): Design a Motor UDT with:
    - Status (Running/Stopped)
    - Speed (RPM)
    - Temperature
    - Alarm limits as parameters
    - Auto-calculated power based on speed

    **Solution Structure**:
    ```
    Motor_UDT
    ├── Parameters
    │   ├── MaxSpeed
    │   ├── TempAlarmLimit
    │   └── PowerFactor
    ├── Status (OPC Tag)
    ├── Speed (OPC Tag)
    ├── Temperature (OPC Tag)
    ├── Power (Expression Tag: {Speed} * {PowerFactor})
    └── OverTemp (Expression Tag: {Temperature} > {TempAlarmLimit})
    ```

24. **Performance Quiz**: Order these from best to worst performance:
    - A) 1000 individual OPC tags
    - B) 1000 tags in a single UDT instance
    - C) 100 UDT instances with 10 tags each
    - D) 1000 expression tags referencing OPC tags
    
    **Answer**: C, B, A, D

### Team Collaboration Bonus

25. **Team Design**: Create a complete UDT structure for a production line with:
    - Multiple stations
    - Product tracking
    - Quality metrics
    - Downtime monitoring
    
    (Each team member adds one component)

### Discussion Questions

1. When would you use Query tags vs Expression tags for calculations?
2. Explain the pros and cons of nested UDTs
3. How do you handle versioning when updating UDT definitions in production?
4. What's the impact of tag security on performance?

### Bonus Round: Tag Scripting Scenarios

26. **Script Fix**: This tag event script causes errors. Why?
    ```python
    def valueChanged(tag, tagPath, previousValue, currentValue, initialChange, missedEvents):
        if currentValue.value > 100:
            system.tag.write(tagPath, 100)
    ```
    **Answer**: Using tagPath string instead of full path, should use system.tag.writeBlocking(["[default]" + tagPath], [100])

27. **Best Practice**: You need to monitor 50 tags for any change. What's better?
    - A) 50 individual tag event scripts
    - B) One Gateway tag change script with 50 paths
    - C) Expression tag that concatenates all values
    - D) Transaction group
    
    **Answer**: B) One Gateway tag change script with 50 paths