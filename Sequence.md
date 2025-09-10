:::mermaid

sequenceDiagram 
    actor User as 'End User'
    participant App as 'Application'
    participant Server as 'Server'
    participant DB as 'Database'


    User->>App: Request Data
    activate App

    App->>Server: Fetch Data
    activate Server

    alt Data Exist ?
        Server->>DB: Query Datatabase
        activate DB
        DB->>Server: Return Data
        deactivate DB
        Server->>App: Data Return
    else Data Not Exists ?
        Server->>App: Terminate (Data Not Found)
    end
    deactivate Server

    App->>User: Data display

    deactivate App