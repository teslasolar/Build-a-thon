# Perspective Peak Quiz Questions
## Realm 5: Perspective Layouts and Mobile Features

### Beginner Level (100 points each)

1. **Question**: What technology stack does Perspective use?
   - A) Java Swing
   - B) HTML5, CSS, JavaScript
   - C) .NET Framework
   - D) Adobe Flash
   **Answer**: B) HTML5, CSS, JavaScript

2. **Question**: Which container type automatically arranges components in rows and columns?
   - A) Coordinate Container
   - B) Flex Container
   - C) Column Container
   - D) Tab Container
   **Answer**: B) Flex Container

3. **Question**: What is a Perspective "View"?
   - A) A window in the Designer
   - B) A reusable component container
   - C) A database view
   - D) A client instance
   **Answer**: B) A reusable component container

4. **Question**: How do you pass data into a Perspective View?
   - A) Global variables
   - B) View parameters
   - C) Session tags
   - D) URL encoding
   **Answer**: B) View parameters

5. **Question**: What file format does Perspective use for icons?
   - A) JPG
   - B) BMP
   - C) SVG
   - D) ICO
   **Answer**: C) SVG

### Intermediate Level (250 points each)

6. **Question**: What's the difference between view.params and view.custom?
   - A) params are input only, custom is internal state
   - B) params are faster than custom
   - C) custom can only store strings
   - D) No difference
   **Answer**: A) params are input only, custom is internal state

7. **Question**: Which component is best for mobile barcode scanning?
   - A) Camera component
   - B) Barcode Scanner component
   - C) Image component with script
   - D) Text Field with camera input
   **Answer**: B) Barcode Scanner component

8. **Question**: What are Perspective breakpoints used for?
   - A) Debugging views
   - B) Creating responsive layouts for different screen sizes
   - C) Breaking component bindings
   - D) Performance monitoring
   **Answer**: B) Creating responsive layouts for different screen sizes

9. **Question**: How do you style components in Perspective?
   - A) Style classes and inline styles
   - B) Only inline styles
   - C) External CSS files
   - D) Java Swing properties
   **Answer**: A) Style classes and inline styles

10. **Question**: What's the purpose of the Perspective Workstation?
    - A) Design Perspective views
    - B) Run Perspective sessions as desktop applications
    - C) Convert Vision to Perspective
    - D) Mobile app development
    **Answer**: B) Run Perspective sessions as desktop applications

### Advanced Level (500 points each)

11. **Question**: How do you implement deep linking in Perspective?
    - A) URL parameters and page configuration
    - B) Session properties only
    - C) Not supported
    - D) External JavaScript
    **Answer**: A) URL parameters and page configuration

12. **Question**: What's the most efficient way to update multiple component properties?
    - A) Individual property writes
    - B) system.perspective.alterProperty()
    - C) Refresh the view
    - D) Use a style class
    **Answer**: B) system.perspective.alterProperty()

13. **Question**: When using the Map component, what's required for geolocation?
    - A) GPS hardware
    - B) HTTPS connection and user permission
    - C) Google Maps API key
    - D) Special licensing
    **Answer**: B) HTTPS connection and user permission

14. **Question**: How do you optimize Perspective performance for slow networks?
    - A) Reduce view complexity and use loading states
    - B) Increase Gateway memory
    - C) Use more embedded views
    - D) Disable animations
    **Answer**: A) Reduce view complexity and use loading states

15. **Question**: What's the correct way to handle component message handlers?
    - A) Direct component method calls
    - B) system.perspective.sendMessage()
    - C) Event bus pattern
    - D) Global message queue
    **Answer**: B) system.perspective.sendMessage()

### Boss Battle Questions (1000 points)

16. **Design Challenge**: You need a dashboard that works on phone (portrait), tablet, and desktop. What's your approach?
    - A) Three separate views with navigation
    - B) One view with breakpoint containers and responsive design
    - C) Desktop view with zoom for mobile
    - D) Native apps for each platform
    **Answer**: B) One view with breakpoint containers and responsive design

17. **Performance Issue**: A Perspective view with 100 components loads slowly. Best optimization?
    - A) Split into multiple embedded views with lazy loading
    - B) Remove all bindings
    - C) Convert to Vision
    - D) Increase client memory
    **Answer**: A) Split into multiple embedded views with lazy loading

### Lightning Round (50 points, 20-second timer)

18. Default Perspective port?
    **Answer**: 8088 (same as Gateway)

19. Maximum number of breakpoints per container?
    **Answer**: Unlimited (practical limit ~5-6)

20. True/False: Perspective supports multi-touch gestures
    **Answer**: True

21. Component for PDF display?
    **Answer**: PDF Viewer component

22. Session property for user locale?
    **Answer**: session.props.locale

### Practical Challenges

23. **Responsive Design** (5 minutes): Create container structure for:
    - Mobile: Single column
    - Tablet: Two columns
    - Desktop: Three columns with sidebar

    **Solution**:
    ```
    Breakpoint Container
    ├── Small (< 768px): Column Container
    ├── Medium (768-1024px): Flex Container (2 columns)
    └── Large (> 1024px): Flex Container
        ├── Sidebar (fixed width)
        └── Main Content (3 columns)
    ```

24. **Mobile Features Match**: Match feature to component:
    - A) GPS location → ?
    - B) Camera access → ?
    - C) Accelerometer → ?
    - D) File upload → ?
    
    **Answers**:
    - A) Map component
    - B) Barcode Scanner / Camera
    - C) Not directly supported (custom development)
    - D) File Upload component

### Team Collaboration Bonus

25. **Team Project**: Design a mobile inspection app with:
    - Equipment barcode scanning
    - Photo capture
    - GPS location tracking
    - Offline capability planning
    
    Each member designs one feature.

### CSS and Styling Round

26. **Style Challenge**: Create CSS for a button that:
    - Changes color on hover
    - Has rounded corners
    - Shows pressed state
    ```css
    .custom-button {
        background-color: #3498db;
        border-radius: 8px;
        transition: all 0.3s;
    }
    .custom-button:hover {
        background-color: #2980b9;
    }
    .custom-button:active {
        transform: scale(0.95);
    }
    ```

27. **Flex Layout**: What flex properties achieve equal-width columns?
    **Answer**: flex-grow: 1, flex-basis: 0

### Advanced Concepts

28. **Question**: How do you implement session-persistent storage in Perspective?
    - A) localStorage (not recommended)
    - B) Session custom properties
    - C) Database with session ID
    - D) Both B and C
    **Answer**: D) Both B and C

29. **Security**: What's the best practice for component visibility based on roles?
    - A) Binding to session.props.auth.authenticated
    - B) Using component security settings
    - C) Scripted visibility
    - D) Separate views per role
    **Answer**: B) Using component security settings

30. **Integration**: How do you embed Perspective views in external websites?
    - A) iframe with authentication
    - B) Not supported
    - C) Export as HTML
    - D) REST API only
    **Answer**: A) iframe with authentication

### Discussion Questions

1. When would you choose Coordinate Container over Flex Container?
2. Explain the Perspective session lifecycle
3. How do you handle offline scenarios in mobile Perspective apps?
4. What are the security implications of deep linking?

### Bonus: Common Pitfalls

31. **Debug This**: View parameters aren't updating. Common causes?
    - Input/Output configuration
    - Binding direction
    - Parameter persistence settings
    - All of the above
    **Answer**: All of the above

32. **Best Practice**: Large data tables in Perspective should use:
    - A) Table component with pagination
    - B) Power Table (not available)
    - C) Virtualized table with lazy loading
    - D) Multiple small tables
    **Answer**: C) Virtualized table with lazy loading