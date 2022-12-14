# School Eco-System (SES)
## An OBE-based System of Education Institutional

### A. Deployment Platform
A list of potential platforms (for production use), which you may consider them, is listed as follows.
1. [Cloud Foundry](https://www.cloudfoundry.org/)
2. [Kubernetes](https://kubernetes.io/)
3. [Heroku](https://www.heroku.com/)
4. [OpenShift](https://www.redhat.com/en/technologies/cloud-computing/openshift)
5. [Amazon Web Services (AWS)](https://aws.amazon.com/)
6. [CloudCaptain](https://cloudcaptain.sh/)
7. [Azure](https://azure.microsoft.com/en-us/)
8. [Google Cloud](https://cloud.google.com/)

Details of deployment into these platform are available at URL https://docs.spring.io/spring-boot/docs/current/reference/html/deployment.html . The standalone-use as well as development-use are tested, i.e. with Oracle J2SE 11.x with respective web browser) in the following operating system.
1. Microsoft Windows 10 - Microsoft Edge, Mozilla Firefox, Google Chrome
2. Linux: Ubuntu 22.x.x LTS - Mozilla Firefox, Google Chrome
3. Apple MacOS 12.5 - Apple Safari (Desktop and iOS version), Mozilla Firefox, Google Chrome
4. Oracle Solaris 11.4.x - Mozilla Firefox

![33265](https://user-images.githubusercontent.com/6356054/185901261-81af0a65-5527-4e2d-b464-93affbf665eb.png)

SES adopts the [Spring Framework](https://spring.io/projects/spring-framework) in its design and development. As such, SES inherites the support on working with SQL databases, specifically using the direct JDBC access with JdbcTemplate to complete 'object relational mapping' technologies, namely as [Hibernate](https://hibernate.org/). Note that SES is developed using an in-memory embedded database, namely as [H2](https://www.h2database.com). Obviously, in-memory databases do not provide persistent storage. **Therefore, you need to migrate the existing H2 database to your preferred database in the production enviroment. Remember to load it with your own initial data.**

[Spring Security](https://docs.spring.io/spring-security/reference/index.html) provides comprehensive support for Authentication. It offers the Servlet-based Authentication Architecture. There is a list of authentication mechanisms, which users can authenticate, for your consideration in SES as follows. 

1. Username and Password - how to authenticate with a username/password
2. OAuth 2.0 Login 
3. SAML 2.0 Login
4. [Central Authentication Service (CAS)](https://github.com/apereo/cas)
5. Remember Me - how to remember a user past session expiration
6. Java Authentication and Authorization Service (JAAS) Authentication
7. [OpenID](https://openid.net/) Authentication (not to be confused with OpenID Connect)
8. Pre-Authentication Scenarios - authenticate with an external mechanism such as SiteMinder or Java EE security but still use Spring Security for authorization and protection against common exploits.
9. X509 Authentication

**Read more on the todo security integration** at URL https://docs.spring.io/spring-security/reference/servlet/authentication/index.html

### B. Modules of SES

| No | Module                 | Linked Module | Remark                                | Status |
|----|------------------------|---------------|---------------------------------------|--------|
| 1a | Qualification          |               | Pre-loaded: Certificate, Diploma, Bachelor, Master, Doctoral  | Done   |
| 1b | Level (Engagement)     |               | Pre-loaded: University, State, National, International, Community, Industry (Private/NGO/Semi-GOV), Agency (Private/NGO/Semi-GOV), Professional Body (Private/NGO/Semi-GOV), Association (Private/NGO/Semi-GOV) | Done   |
| 1c | Type of Research (Work)        |       | Pre-loaded: Science, Non-Science      | Done   |
| 1d | Collabration (Agreement)       |       | Pre-loaded: MoA, MoU, LoA, RA         | Done   | 
| 1e | Position (Appointment)         |       | Pre-loaded: Chairman, Board Member, Committee Member, Member, Life Member    | Done   | 
| 1f | Type of Award (Recognition)    |       | Pre-loaded: Award, Recognition, Stewardship    | Done   |
| 1g | Type of Intellecture Property  |       | Pre-loaded: Copyright, Trademark, Industrial Design, Patent, Commercialized Product, Technology Know-how Licensed and Sold Outright, Spinoff Company of Commercialized Products    | Done   |
| 1h | Type of Publication            |       | Pre-loaded: Book, Book Chapter, Journal, Proceeding, Other    | Done   |
| 2  | MQA MQF's Domain       |               | Pre-loaded & Manipulable: 11 domains - Knowledge & Understanding, Cognitive Skills, Practical Skills, Interpersonal Skills, Communication Skills, Digital Skills, Numeracy Skills, Leadership, Autonomy & Responsibility, Personal Skills, Entrepreneurial Skills, Ethics & Professionalism  | Done   |
| 3  | Bloom's Taxonomy       |               | Pre-loaded & Manipulable: Cognitive (6 - Knowledge, Comprehension, Application, Analysis, Synthesis, Evaluation), Psychomotor (7 - Perception, Set, Guided Response, Mechanism, Complex Overt Response, Adaptation, Orgination), Affective (5 - Receiving, Responding, Valuing, Organising, Characterising)     | Done   |
| 4  | PEO of Institutional   |               | Manipulable                           | Done   |
| 4a | &#8594; PEO-PLO        |               | Viewable mapping                      |        |
| 5  | Schools of Institution |               | Manipulable                           | Done   |
| 5a | &#8594; School-Programme|               | Viewable mapping                      |        |
| 6  | Programme of School    | 1a            | Manipulable                           | Done   |
| 6a | &#8594; Programme-Course|               | Viewable mapping                      |        |
| 7  | Programme LO           | 6, 2          | Manipulable                           | Done   |
| 7a | &#8594; PLO-CLO        |               | Viewable mapping                      |        |
| 8  | Courses of Programme   | 5, 6          | Manipulable                           | Done   |
| 8a | &#8594; Course-Topic   |               | Viewable mapping                      |        |
| 9  | Course LO              | 8, 3, 7       | Manipulable                           | Done   |
| 10 | Course Coordinator (staff ID required) | 8 | Manipulable                       | Done   |
| 10a| &#8594; Course-Coordinator      |       | Viewable mapping (workload)           |        |
| 11 | Course Topic           | 8             | Manipulable                           | Done   |
| 12 | Course Prerequiste     | 8             | Manipulable                           | Done   |
| 13 | Course Reference       | 8             | Manipulable                           | Done   |
| 14 | Course Resource        | 8             | Manipulable                           | Done   |
| 15 | Course Development     | 8             | Manipulable                           | Done   |
| 16 | Course Revision        | 8             | Manipulable                           | Done   |
| 17 | Semester of Institutional      |       | Manipulable                           | Done   |
| 18 | Assessment Weight      | 8, 17         | Manipulable                           |        |
| 19 | Course Marks (std ID required) | 8, 17 | Uploadable                            |        |
| 20 | Course Presentation Survey     | 8, 17 | Uploadable                            |        |
| 21 | Course Presentation Comment    | 8, 17 | Manipulable                           |        |
| 22 | Grant and Fund         | 10, 1b, 1c    | Manipulable                           | Done   |
| 23 | Community Service      | 10, 1b        | Manipulable                           | Done   |
| 24 | Intellectual Property  | 10, 1b, 1g    | Manipulable                           | Done   |
| 25 | Membership             | 10, 1b, 1e    | Manipulable                           | Done   |
| 26 | Memorandum             | 10, 1b, 1d    | Manipulable                           | Done   |
| 27 | Award                  | 10, 1b, 1f    | Manipulable                           | Done   |
| 28 | Publication            | 10, 1h        | Manipulable                           | Done   |

### C. Operational use modules (in planning)
* Data import/upload/enter, i.e. (1) course-examination marks from Registry and (2) survey of courses, after each Examination Board meeting (before the end of semester)
* Comments enter and preview of course presentation report and its summary
* Preview the programme structure (listed by programme - for school, QA use).
* Preview the course structure (listed by programme - for QA use).
* Preview the Reference list (listed by programme and courses - for library, QA use). 
* Preview CC's workload, assuming CC is the lecturer & tutor of institution.

### D. Impactful modules: (in planning)
* Preview/manipulate the Academic profile including achievements, grants, projects and publications (listed by programme/CC - for QA, MyRA, Setara use).
* Preview individual course performance, measuring via the mapped CLO.
* Preview continous course performance, inheriting the past with the current individualcourse achievement.
* Preview individualprogramme performance, measuring via the mapped PLO-PEO.
* Preview continous programme performance, inheriting the past with the current individualcourse achievement.
* Preview individual student performance, measuring via the mapped CLO-PLO.


### Z. References
1. Adapted image: https://openclipart.org/detail/33265/liste-list
