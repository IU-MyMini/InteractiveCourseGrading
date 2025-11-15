# Interview script

### 1. Review Action Points from Last Meeting
* "Last week, your main feedback was on the professor/TA view."
* "You mentioned you wanted to see the list of **groups first**, not individual students."

### 2. Show Prototype & Address Feedback
* "We have updated the Figma prototype based on that feedback."
* "As you can see, the main view is now a list of groups with their overall grades."
* "We also added the functionality to click on a group to expand it and see all the individual team members and their specific component grades."

### 3. Show Deployed Version
* "We have successfully deployed the first version of our module to the university's staging (test) server."
* "Right now, it's just the container, and the API endpoints are not live, but the service is running."

### 4. Discuss Product Backlog & Strategic Plan
* **Technical Progress:** "We have also refined our domain model and have a UML diagram. The main components are 'Assignments,' 'Components' (sub-tasks), 'Groups,' and 'Submissions,' which link students to both individual and group grades."
* **Key Blocker (Moodle API):** "We have an update on the Moodle API access. We discussed it with our manager, who contacted Alexey Potemkin."
    * "Currently, he is not willing to provide API access."
    * "His concern is that he doesn't want professors to leave Moodle for a different platform."
    * "Our argument is that this *keeps* professors on Moodle by providing a better UI, and all data would sync back. If we don't get access, professors will just keep using Google Sheets, which is worse for the university."

### 5. Agree on Further Steps
* "Given the Moodle API issue, we may need to rely on a manual import/export feature for the MVP."
* "Our main goal for the next sprint is to get the deployed version functional so you can start using it."
* "The next course assignment is about 'Testing,' and the one after that is about 'Usage Feedback,' so we need to get you access as soon as possible to start gathering that data."
