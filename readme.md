# Final Project for the Software Analysis Course of EC Utbildning

In this project you have to do a breakdown of requirements for an education center in Sweden. Based on that you should design different diagrams and user stories.
Of course you don't have to build the actual system.
Requirements are quite loosely written so you can't read in detail what the system does and how it is supposed to work.
That is knowledge the customer doesn't have, but it's your job as a developer to break down the requirements and specify how a certain functionality is supposed to be implemented.

## Requirements

You are contracted to build a system to handle courses.

+ A user should be able to register and log in with email and password.
+ In the system there's even administrators. Those administrators are added by a system-administrator or by other administrators with the right administrative roles.
+ Sys-admin has an account from the start and is a non-removable role without first assigning system admin to another admin.

---

+ Admins should be able to add lecturers to the system and add users and admin users.
+ A user should be able to express interest in a course in the system.
+ Only admins can allow users to attend courses

---

+ A lecturer should be able to see all of the courses added to them and should be able to structure the course content.
+ There should be the possibility for a lecturer to schedule meetings and there should be the possibility to upload course material on the course site.
+ On the course site a lecturer should have the ability to post course criteria so both lecturer and the attendees can read what the course is about.
+ Only lecturers and admins should be able to edit the info about the course and course files etc.

---

+ A user should be able to see the course description, schedule and be able to join a meeting.
+ Users should be able to write a comment in a forum site on the course site.
+ Users should even be able to watch lectures after the fact.

## For the passing grade

+ Write one user story
+ Make one case diagram for this story
+ Make one activity diagram for this story
+ Make one sequence diagram for this story

## For the good grade

+ Write at least 3 user stories
+ Make case diagrams for all stories
+ Make activity diagrams for all stories
+ Make sequence diagrams for all stories
+ Make one class diagram (including one or more association, aggregation, composition, implementation, inherritance)

### Additional features added

Decided to learn [Mermaid](https://mermaid-js.github.io/mermaid/#/) for this to be able to post this to github instead of uploading a pdf file for my teacher to grade.

### Known issues (due to missing features in mermaid)

+ Database symbol is not available in mermaid sequence diagrams at this point, so the database is just added as a regular square

+ Sync actions are marked by black bars and in the diagrams since there was no way to display that in mermaid, could not prevent them from looking a bit off in certain diagrams

+ Right now there is no use case diagram available in mermaid, so those are added as images with the [plantUML](https://plantuml.com/) code commented into the markdown file.
