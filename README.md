# RAID DPS Simulator for LOTRO on Legendary Server Angmar

## Table of Contents

1. [Project Planning and Scope](#1-project-planning-and-scope)
2. [Understanding Game Mechanics and Data Requirements](#2-understanding-game-mechanics-and-data-requirements)
3. [Choosing the Technology Stack](#3-choosing-the-technology-stack)
4. [Designing the Simulator Architecture](#4-designing-the-simulator-architecture)
5. [Implementing Import/Export Functionality](#5-implementing-importexport-functionality)
6. [Developing the Frontend](#6-developing-the-frontend)
7. [Setting Up GitHub Repository](#7-setting-up-github-repository)
8. [Hosting the Website](#8-hosting-the-website)
9. [Testing and Validation](#9-testing-and-validation)
10. [Deployment and Maintenance](#10-deployment-and-maintenance)
11. [Additional Considerations](#11-additional-considerations)
12. [Resources and Tools](#12-resources-and-tools)

---

## 1. Project Planning and Scope

### Define Objectives

- **Purpose:** Develop a tool that allows players to simulate RAID DPS based on their character’s gear, talents, and traits.
- **Features:**
  - Input system for gear, talents, and traits.
  - Calculation engine to simulate DPS based on LOTRO mechanics.
  - Import/export functionality for sharing configurations.
  - User-friendly interface.
  - Hosted on GitHub with a live website.

### Scope Management

- **Minimum Viable Product (MVP):** Focus on core features like gear input, basic DPS calculation, and import/export.
- **Future Enhancements:** Advanced simulations, real-time updates, community features, etc.

### Timeline and Milestones

- **Phase 1:** Research and Planning
- **Phase 2:** Data Collection and Modeling
- **Phase 3:** Development (Backend & Frontend)
- **Phase 4:** Testing
- **Phase 5:** Deployment
- **Phase 6:** Maintenance and Updates

---

## 2. Understanding Game Mechanics and Data Requirements

### Deep Dive into LOTRO RAID Mechanics

- **Damage Calculation:** Understand how DPS is calculated in LOTRO, including factors like gear stats, talents, traits, buffs, and debuffs.
- **Class and Race Specifics:** Different classes and races may have unique mechanics affecting DPS.
- **Skills and Abilities:** How different skills contribute to overall damage.

### Data Requirements

- **Gear Stats:** Attributes like Strength, Dexterity, Vitality, etc.
- **Talents and Traits:** How these modify or enhance abilities.
- **Cooldowns and Buffs:** Timings and effects that influence DPS.
- **Enemy Mechanics:** Consideration of raid boss abilities that might affect damage output.

### Data Sources

- **Official Resources:** LOTRO official website, forums, and patch notes.
- **Community Databases:** Websites like Lotro-Wiki, community forums, or fan sites.
- **In-Game Data Extraction:** If available and permissible, extract data directly from the game.

---

## 3. Choosing the Technology Stack

### Frontend

- **Frameworks/Libraries:** React.js, Vue.js, or Angular for a dynamic and responsive UI.
- **Styling:** CSS3, Sass, Tailwind CSS, or Bootstrap for styling components.

### Backend

- **Language and Framework:** Node.js with Express, Python with Django or Flask, or Ruby on Rails.
- **Database:** PostgreSQL, MongoDB, or MySQL for storing user configurations and data.

### Import/Export Functionality

- **Data Formats:** JSON or custom string encoding for gear/talents/traits.
- **Serialization Libraries:** Utilize libraries for parsing and generating import/export strings.

### Hosting and Deployment

- **Frontend Hosting:** GitHub Pages, Netlify, Vercel.
- **Backend Hosting:** Heroku, AWS, DigitalOcean, or Azure.
- **Version Control:** Git, managed via GitHub.

### Additional Tools

- **State Management:** Redux or Vuex for managing application state.
- **Testing:** Jest, Mocha, or Cypress for automated testing.
- **CI/CD:** GitHub Actions for continuous integration and deployment.

---

## 4. Designing the Simulator Architecture

### High-Level Architecture

1. **Frontend:** User interface for inputting gear, talents, traits, and viewing DPS results.
2. **Backend:** Handles data processing, DPS calculations, and manages import/export functionalities.
3. **Database:** Stores user configurations, data models, and possibly historical simulation data.
4. **API Layer:** Facilitates communication between frontend and backend.

### Detailed Components

#### Frontend

- **Input Forms:** For users to input gear, select talents, and choose traits.
- **DPS Display:** Visual representation of calculated DPS.
- **Import/Export Controls:** Buttons or fields for handling configuration strings.
- **Responsive Design:** Ensures usability across devices.

#### Backend

- **Calculation Engine:** Core logic that processes inputs and computes DPS.
- **API Endpoints:**
  - **/simulate:** Accepts user data and returns DPS results.
  - **/import:** Processes import strings into usable data.
  - **/export:** Generates import strings from user data.
- **Data Management:** Handles retrieval and storage of necessary game data.

#### Database

- **Schema Design:**
  - **Users (optional):** If user accounts are needed.
  - **Configurations:** Stores gear, talents, and traits configurations.
  - **Game Data:** Static data related to gear, talents, traits, etc.

---

## 5. Implementing Import/Export Functionality

### Data Serialization

- **Format Selection:** JSON is human-readable and widely supported, but if the community prefers a compact string format, consider Base64 or a custom encoding scheme.
- **Structure:** Define a consistent structure that encapsulates gear, talents, and traits.

### Import Functionality

1. **Input Parsing:** Accept a string or file containing the configuration data.
2. **Validation:** Ensure the data is valid and corresponds to existing game elements.
3. **Data Mapping:** Translate the imported data into the simulator's internal format.
4. **Error Handling:** Provide meaningful feedback if the import fails.

### Export Functionality

1. **Data Extraction:** Collect the current configuration from the simulator.
2. **Serialization:** Convert the data into the chosen format.
3. **Download/Copy Mechanism:** Allow users to download the string or copy it to the clipboard.
4. **Security Considerations:** Ensure that exported data does not expose sensitive information.

### Libraries and Tools

- **Serialization:** Use libraries like `JSON.stringify`/`JSON.parse` for JSON handling.
- **Compression (optional):** To shorten import/export strings, consider compressing the data using libraries like `lz-string`.

---

## 6. Developing the Frontend

### User Interface Design

- **Wireframing:** Create wireframes to outline the layout and user flow.
- **UI/UX Principles:** Ensure the interface is intuitive, accessible, and responsive.

### Key Components

1. **Header:** Project title, navigation links.
2. **Configuration Panel:**
   - **Gear Input:** Dropdowns, sliders, or selection grids for gear pieces.
   - **Talent Selector:** Tree view or multi-select for talents.
   - **Trait Selector:** Checkboxes or similar controls for traits.
3. **Simulation Controls:**
   - **Simulate Button:** Initiates the DPS calculation.
   - **Import/Export Buttons:** For handling configuration strings.
4. **Results Display:**
   - **DPS Output:** Numerical display and possibly graphical representations (charts, graphs).
   - **Detailed Breakdown:** Optionally show how each component contributes to DPS.
5. **Footer:** Additional links, credits, etc.

### Responsive Design

- Utilize CSS frameworks like Bootstrap or Tailwind CSS to ensure the simulator is usable on various devices.

### Accessibility

- Follow accessibility standards (WCAG) to make the simulator usable for all players.

### State Management

- Use state management libraries (e.g., Redux for React) to handle complex state across components.

---

## 7. Setting Up GitHub Repository

### Repository Initialization

1. **Create Repository:**
   - Go to GitHub and create a new repository, e.g., `lotro-raid-dps-simulator`.
2. **Initialize with README:**
   - Provide an overview, installation instructions, and contribution guidelines.
3. **License:**
   - Choose an appropriate license (e.g., MIT, GPL) to define usage rights.

### Version Control Best Practices

- **Branching Strategy:**
  - Use `main` for stable releases.
  - `develop` for ongoing development.
  - Feature branches for new features.
- **Commit Messages:**
  - Write clear, concise commit messages.
- **Pull Requests:**
  - Use pull requests for code reviews and merging.

### Documentation

- **Wiki:** Utilize GitHub Wiki for detailed documentation.
- **Inline Documentation:** Comment code for clarity.
- **API Documentation:** If applicable, document API endpoints using tools like Swagger.

### Collaboration

- **Issues:** Track bugs, feature requests, and tasks using GitHub Issues.
- **Project Boards:** Organize tasks using Kanban-style boards.
- **Contributors:** Encourage community contributions by providing clear guidelines.

---

## 8. Hosting the Website

### Frontend Hosting Options

- **GitHub Pages:**
  - Ideal for static sites.
  - Free and integrates seamlessly with GitHub repositories.
- **Netlify or Vercel:**
  - Support both static and dynamic sites.
  - Offer features like continuous deployment, custom domains, and SSL.

### Backend Hosting Options

- **Heroku:**
  - Easy deployment for Node.js applications.
  - Free tier available for testing.
- **AWS/Azure/DigitalOcean:**
  - More control and scalability.
  - Consider using Docker for containerized deployment.

### Domain Name

- **Custom Domain:** Consider purchasing a domain for a professional touch.
- **SSL Certificates:** Ensure the site is secure with HTTPS.

### Continuous Deployment

- Set up CI/CD pipelines using GitHub Actions to automate testing and deployment on changes.

---

## 9. Testing and Validation

### Testing Strategy

- **Unit Testing:** Test individual components and functions.
- **Integration Testing:** Ensure that different modules work together as expected.
- **User Acceptance Testing:** Gather feedback from users to validate the simulator’s functionality and usability.

### Tools

- **Frontend Testing:** Jest, React Testing Library, or Cypress for end-to-end testing.
- **Backend Testing:** Mocha, Chai, or Supertest for API testing.

### Performance Testing

- Test the simulator’s performance under different loads.
- Optimize code to ensure quick responses for calculations.

---

## 10. Deployment and Maintenance

### Deployment Process

1. **Pre-Deployment Checks:**
   - Ensure all tests pass.
   - Review code for any outstanding issues.
2. **Deployment Steps:**
   - Deploy frontend and backend to chosen platforms.
   - Configure environment variables and settings.

### Maintenance Plan

- **Regular Updates:** Keep libraries and dependencies up to date.
- **Monitor Performance:** Use tools like Google Analytics for frontend and server monitoring.
- **User Feedback:** Regularly collect user feedback for improvements.

---

## 11. Additional Considerations

### Community Engagement

- Foster a community around the tool by encouraging feedback, feature requests, and contributions.

### Documentation

- Maintain thorough documentation for users and developers.
- Update documentation regularly to reflect changes.

### Accessibility and Inclusivity

- Consider accessibility features to ensure all players can use the tool.
- Foster an inclusive environment for players from diverse backgrounds.

---

## 12. Resources and Tools

### Documentation and Guides

- **Official LOTRO Documentation:** For game mechanics and updates.
- **Web Development Tutorials:** W3Schools, MDN Web Docs, and CSS-Tricks for frontend development.
- **Backend Framework Documentation:** Express, Django, or Ruby on Rails docs.

### Libraries and Tools

- **Frontend Libraries:** React, Vue, Angular.
- **Backend Libraries:** Express, Django, Flask.
- **Testing Libraries:** Jest, Mocha, Cypress.

### Community and Support

- **Forums:** LOTRO forums, Reddit, and other community sites for gathering feedback.
- **Developer Communities:** Stack Overflow, Discord, or Slack groups for troubleshooting and advice.

---

