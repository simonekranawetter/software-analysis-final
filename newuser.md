# New User Signup

## User story

**As a new user** on the site, **I want to** be able register an account, **so that I can** access the content availabe to standard users on the site.

## Activity Diagram

```mermaid
flowchart TD
    Start((Start)) ==> LogInView(Log In View)
    LogInView ==> If{Has an account}
    If --true--> SignIn(Sign in)
    SignIn --> End((X))
    If --false--> RegisterNewUserView(Register New User View)
    RegisterNewUserView --> Sync(This is just a placeholder for simultanious action)
    Sync --> Email(Fill in Email)
    Sync --> Password(Fill in Password)
    Email --> ValidateEmail(Validate Email)
    Password --> ValidatePassword(Validate Password)
    ValidateEmail -->SyncEnd(This is just a placeholder for simultanious action)
    ValidatePassword --> SyncEnd
    SyncEnd --> SubmitForm(Submit Form)
    SubmitForm -->EntriesValid{Input valid}
    EntriesValid --true--> CreateUser(CreateUser)
    EntriesValid --false --> ErrorMessage(ErrorMessage)
    ErrorMessage -->RegisterNewUserView
    CreateUser --> GenernateJWT(Generate JWT)
    GenernateJWT --> Sync2(This is just a placeholder for simultanious action)
    Sync2 --> LogInUser(LogInUser)
    Sync2 --> SendJWT(Send JWT)
    Sync2 --> StoreJWT(Store JWT)
    LogInUser --> SyncEnd2(This is just a placeholder for simultanious action)
    SendJWT --> SyncEnd2
    StoreJWT --> SyncEnd2
    SyncEnd2 --> EndProgram(( End ))

    style Start stroke:none, fill:#000
    style End stroke:#fff, stroke-width:1px, fill:#000

    style Email stroke:none
    style Password stroke:none
    style ValidateEmail stroke:none
    style ValidatePassword stroke:none
    style LogInUser stroke:none
    style SendJWT stroke:none
    style StoreJWT stroke:none

    style ErrorMessage stroke:#f44336


    style Sync fill:#000,stroke:#000,stroke-width:2px,color:#000
    style SyncEnd fill:#000,stroke:#000,stroke-width:2px,color:#000
    style Sync2 fill:#000,stroke:#000,stroke-width:2px,color:#000
    style SyncEnd2 fill:#000,stroke:#000,stroke-width:2px,color:#000
    style EndProgram fill:#000,stroke:#fff,stroke-width:4px
```

## Sequence Diagram

```mermaid
sequenceDiagram 
    actor U as User
    participant S as System
    participant A as WebAPI
    participant D as Database
    U->>S: Enter Email
    S-->>S: Validate Email
    U->>S: Enter Password
    S-->>S: Validate Password
    U->>S: Submit Form
    S->>A: HTTP Request
    A-->>A: Validate Email
    A->>A: Validate Password
    A->>D: Register user in DB
    D-->>A: User saved
    A-->>A: Generate JWT token
    A-->>A: Log in user
    A-->>D: Save JWT
    A-->>S: 200 OK JWT
```

## Use Case Diagram
<!--
@startuml 
left to right direction
skinparam packageStyle rectangle
actor user
actor webapi

rectangle SignUp {
 (user) -- (fill out form)
 (fill out form) .> (validate fields) : include
 (validate fields) <. (display error) : extends
 (fill out form) .> (existing user) : extends
 (user) -- (submit form)
 (submit form) .> (validate form) : include
 (validate form) <. (display error) : extends
 (submit form) -- (webapi)
}
@enduml
-->
![](images/newuser.svg)