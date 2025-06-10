# Script Sorcery Valley Quiz Questions
## Realm 2: Python Scripting and Event Handling

### Beginner Level (100 points each)

1. **Question**: Which Python version does Ignition use?
   - A) Python 3.9
   - B) Python 2.7 (Jython)
   - C) Python 3.6
   - D) IronPython
   **Answer**: B) Python 2.7 (Jython)

2. **Question**: How do you print to the console in a Gateway script?
   - A) print("message")
   - B) system.util.print("message")
   - C) system.util.getLogger().info("message")
   - D) console.log("message")
   **Answer**: C) system.util.getLogger().info("message")

3. **Question**: What variable is automatically available in Tag Event Scripts?
   - A) tag
   - B) self
   - C) event
   - D) value
   **Answer**: A) tag

4. **Question**: Which function reads a tag value in a script?
   - A) tag.read()
   - B) system.tag.read()
   - C) system.tag.readBlocking()
   - D) system.tag.getValue()
   **Answer**: C) system.tag.readBlocking()

5. **Question**: How do you import a project script library function?
   - A) import project.scriptName
   - B) from project import scriptName
   - C) project.scriptName.functionName()
   - D) Both B and C are correct
   **Answer**: D) Both B and C are correct

### Intermediate Level (250 points each)

6. **Question**: What's the difference between system.tag.writeBlocking() and system.tag.writeAsync()?
   - A) writeAsync is faster
   - B) writeBlocking waits for confirmation, writeAsync returns immediately
   - C) writeAsync only works in Gateway scope
   - D) There is no difference
   **Answer**: B) writeBlocking waits for confirmation, writeAsync returns immediately

7. **Question**: In a Tag Change Script, what does initialChange indicate?
   - A) The tag was just created
   - B) First execution after subscribing to the tag
   - C) The tag value is at its initial setting
   - D) The quality changed to Good
   **Answer**: B) First execution after subscribing to the tag

8. **Question**: Which event object properties are available in a Gateway Tag Change Script?
   - A) tag, tagPath, previousValue, currentValue, initialChange
   - B) event, initialChange, newValue
   - C) tagPath, oldValue, newValue, quality
   - D) tag, value, quality, timestamp
   **Answer**: A) tag, tagPath, previousValue, currentValue, initialChange

9. **Question**: How do you properly handle exceptions in Ignition scripts?
   ```python
   # Which is correct?
   ```
   - A) try/except/finally blocks
   - B) if error: handle_error()
   - C) system.util.catchError()
   - D) on error resume next
   **Answer**: A) try/except/finally blocks

10. **Question**: What's the correct way to create a dataset in scripting?
    - A) dataset = []
    - B) system.dataset.toDataSet(headers, data)
    - C) new Dataset(headers, data)
    - D) system.data.create(headers, data)
    **Answer**: B) system.dataset.toDataSet(headers, data)

### Advanced Level (500 points each)

11. **Question**: What happens to long-running scripts in Gateway Event Scripts?
    - A) They block all other Gateway scripts
    - B) They run in separate threads and can be terminated
    - C) They automatically timeout after 60 seconds
    - D) They cause the Gateway to restart
    **Answer**: B) They run in separate threads and can be terminated

12. **Code Analysis**: What's wrong with this Gateway Timer Script?
    ```python
    tags = system.tag.browse("[default]", {"recursive": True})
    for tag in tags:
        value = system.tag.read(tag['fullPath'])
        if value.value > 100:
            system.tag.write(tag['fullPath'], 100)
    ```
    - A) Should use readBlocking/writeBlocking
    - B) Browse doesn't return fullPath
    - C) Can't iterate browse results directly
    - D) All of the above
    **Answer**: D) All of the above

13. **Question**: How do you pass parameters to a Message Handler?
    - A) As function arguments
    - B) Through the payload dictionary
    - C) Using global variables
    - D) Through system.util.setProperty()
    **Answer**: B) Through the payload dictionary

14. **Question**: What's the difference between shared.* and project.* scripts?
    - A) shared is deprecated, use project
    - B) shared was for global scripts in 7.9, project is for 8.0+
    - C) shared is faster than project
    - D) No difference, they're aliases
    **Answer**: B) shared was for global scripts in 7.9, project is for 8.0+

15. **Question**: When using system.util.invokeAsynchronous(), what must you remember?
    - A) It only works in Gateway scope
    - B) You cannot interact with UI components from the async thread
    - C) It requires special permissions
    - D) It blocks until complete
    **Answer**: B) You cannot interact with UI components from the async thread

### Boss Battle Questions (1000 points)

16. **Debug Challenge**: This script causes high CPU usage. What's the issue?
    ```python
    def checkTags():
        while True:
            tags = system.tag.readBlocking(["[default]Tag1", "[default]Tag2"])
            if tags[0].value > tags[1].value:
                system.tag.writeBlocking(["[default]Tag3"], [True])
    
    system.util.invokeAsynchronous(checkTags)
    ```
    - A) Missing sleep/delay in the while loop
    - B) Should use tag change scripts instead
    - C) Infinite loop without exit condition
    - D) All of the above
    **Answer**: D) All of the above

17. **Scenario**: You need to aggregate data from 1000 tags every minute and write to a database. What's the best approach?
    - A) Gateway Timer Script with readBlocking all tags at once
    - B) Individual tag change scripts writing to database
    - C) Transaction groups
    - D) Client timer script
    **Answer**: A) Gateway Timer Script with readBlocking all tags at once

### Lightning Round (50 points, 20-second timer)

18. What method adds a row to a dataset?
    **Answer**: system.dataset.addRow()

19. True/False: print() works the same in all script scopes
    **Answer**: False

20. What's the syntax to get current time in milliseconds?
    **Answer**: system.date.now() or System.currentTimeMillis()

21. How do you convert a Document tag to JSON string?
    **Answer**: system.util.jsonEncode()

22. What's the maximum recursion depth in Jython?
    **Answer**: 1000 (default)

### Code Writing Challenges (Timed)

23. **Quick Script** (2 minutes): Write a function to read 10 tags and return their average
    ```python
    def getAverage(tagPaths):
        values = system.tag.readBlocking(tagPaths)
        total = sum([v.value for v in values if v.quality.isGood()])
        count = len([v for v in values if v.quality.isGood()])
        return total / count if count > 0 else 0
    ```

24. **Pattern Recognition**: What design pattern is this?
    ```python
    def singleton(cls):
        instances = {}
        def get_instance(*args, **kwargs):
            if cls not in instances:
                instances[cls] = cls(*args, **kwargs)
            return instances[cls]
        return get_instance
    ```
    **Answer**: Singleton pattern using decorator

### Team Collaboration Bonus

25. **Team Challenge**: Each team member writes one line to create a complete script that:
    - Reads a tag
    - Checks if value > 50
    - Writes to another tag
    - Logs the action
    - Handles errors

### Discussion Questions

1. When should you use system.util.invokeAsynchronous() vs system.util.invokeLater()?
2. Explain the difference between Client and Gateway script scopes
3. What are the performance implications of using try/except blocks?
4. How do you debug scripts that only fail intermittently?