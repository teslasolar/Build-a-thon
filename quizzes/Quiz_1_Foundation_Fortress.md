# Foundation Fortress Quiz Questions
## Realm 1: Core Ignition Concepts

### Beginner Level (100 points each)

1. **Question**: What are the three main components of the Ignition platform?
   - A) Client, Server, Database
   - B) Designer, Gateway, Client
   - C) Vision, Perspective, Edge
   - D) SCADA, HMI, MES
   **Answer**: B) Designer, Gateway, Client

2. **Question**: Which component of Ignition runs as a web server?
   - A) Designer
   - B) Client
   - C) Gateway
   - D) Database
   **Answer**: C) Gateway

3. **Question**: What language is used for scripting in Ignition?
   - A) JavaScript
   - B) Java
   - C) Python (Jython)
   - D) C#
   **Answer**: C) Python (Jython)

4. **Question**: What does "unlimited licensing" in Ignition mean?
   - A) Unlimited tags
   - B) Unlimited clients
   - C) Unlimited projects
   - D) All of the above
   **Answer**: D) All of the above

5. **Question**: Which port does Ignition Gateway typically use?
   - A) 80
   - B) 8088
   - C) 443
   - D) 3306
   **Answer**: B) 8088

### Intermediate Level (250 points each)

6. **Question**: What is the difference between a Standard and Edge edition of Ignition?
   - A) Edge has limited tags and clients
   - B) Edge can only run on Linux
   - C) Edge doesn't support scripting
   - D) Edge only works with Modbus
   **Answer**: A) Edge has limited tags and clients

7. **Question**: In which scope do Gateway Event Scripts execute?
   - A) Client Scope
   - B) Designer Scope
   - C) Gateway Scope
   - D) Database Scope
   **Answer**: C) Gateway Scope

8. **Question**: What happens to Client Tags when the client closes?
   - A) They persist in the Gateway
   - B) They are destroyed
   - C) They move to Gateway tags
   - D) They are saved to database
   **Answer**: B) They are destroyed

9. **Question**: Which module would you use for building mobile-responsive applications?
   - A) Vision
   - B) Perspective
   - C) Reporting
   - D) Alarm Notification
   **Answer**: B) Perspective

10. **Question**: What is a "Named Query" in Ignition?
    - A) A SQL query stored in the database
    - B) A query with parameters stored in the project
    - C) A query that runs automatically
    - D) A query that only returns names
    **Answer**: B) A query with parameters stored in the project

### Advanced Level (500 points each)

11. **Question**: What is the primary difference between polling and subscription modes for OPC tags?
    - A) Polling is faster
    - B) Subscription uses less bandwidth for frequently changing values
    - C) Polling supports more data types
    - D) Subscription requires special licensing
    **Answer**: B) Subscription uses less bandwidth for frequently changing values

12. **Question**: In a redundant Gateway setup, what happens when the master fails?
    - A) All clients disconnect permanently
    - B) The backup becomes active and clients auto-reconnect
    - C) The system stops until manual intervention
    - D) Data collection stops but clients stay connected
    **Answer**: B) The backup becomes active and clients auto-reconnect

13. **Question**: What is the execution order for multiple Tag Event Scripts on the same tag?
    - A) Alphabetical by script name
    - B) Random order
    - C) Creation date order
    - D) Separate threads, no guaranteed order
    **Answer**: D) Separate threads, no guaranteed order

14. **Question**: When using system.util.retarget() in a Client Event Script, what happens?
    - A) The client switches to a different project
    - B) The client changes its Gateway connection
    - C) The client restarts
    - D) Both A and B are possible
    **Answer**: D) Both A and B are possible

15. **Question**: What is the purpose of the Store and Forward system?
    - A) To cache client data
    - B) To ensure data integrity during connection loss
    - C) To speed up queries
    - D) To compress historical data
    **Answer**: B) To ensure data integrity during connection loss

### Boss Battle Questions (1000 points)

16. **Scenario**: Your Ignition Gateway is consuming excessive memory. What is the correct troubleshooting order?
    - A) Increase heap size → Check running scripts → Review tag history settings → Analyze thread dumps
    - B) Check running scripts → Review tag history settings → Analyze thread dumps → Increase heap size
    - C) Restart Gateway → Increase heap size → Disable modules → Check scripts
    - D) Analyze thread dumps → Check database connections → Review scripts → Clear cache
    **Answer**: B) Check running scripts → Review tag history settings → Analyze thread dumps → Increase heap size

17. **Scenario**: You need a UI that works on both industrial panels and mobile devices with different layouts. What's the best approach?
    - A) Create two Vision projects
    - B) Use Perspective with responsive containers and breakpoints
    - C) Use Vision with mobile module
    - D) Create one Vision and one Perspective project
    **Answer**: B) Use Perspective with responsive containers and breakpoints

### Lightning Round (50 points, 20-second timer)

18. What file extension do Ignition project exports use?
    **Answer**: .proj (or .zip for project export)

19. True/False: Gateway scripts continue running when no clients are connected.
    **Answer**: True

20. What is the default scan class rate?
    **Answer**: 1000ms (1 second)

21. Which module enables SMS and voice notifications?
    **Answer**: Alarm Notification module

22. What does "OPC" stand for?
    **Answer**: OLE for Process Control

### Team Collaboration Bonus Questions

23. **Team Challenge**: List 5 differences between Vision and Perspective (100 points per correct answer)
    **Answers**: 
    - Technology: Java Swing vs HTML5/CSS/JavaScript
    - Deployment: Requires Java client vs Web browser
    - Mobile: Limited mobile support vs Native mobile responsive
    - Components: Different component sets
    - Styling: Style customizer vs CSS styling

### Discussion Questions (No points, learning focus)

1. When would you choose Vision over Perspective for a new project?
2. Explain the concept of "Gateway Network" and its use cases
3. What are the security implications of using Client tags vs Gateway tags?
4. How does Ignition's historian compare to traditional historians?