# docs-flowcharts-ecoleone-system-flowchart.png
Ecoleone-system-flowchart
flowchart TD
    A([START]) --> B[Open EcoLeone System]
    B --> C{Select User Role}

    C -->|Citizen| D[Enter Location / Community]
    D --> E[Describe Waste Problem]
    E --> F[Upload Photo if Available]
    F --> G[Select Urgency Level]

    G --> H{Is Urgency Valid?}
    H -->|No| G
    H -->|Yes| I[Generate Unique Tracking ID]

    I --> J[Save Report to Database]
    J --> K[Display Submission Confirmation]
    K --> L[Citizen Receives Tracking ID]
    L --> M([END])

    C -->|Administrator| N[Login and Verify Credentials]
    N --> O{Login Successful?}
    O -->|No| N
    O -->|Yes| P[Open Admin Dashboard]

    P --> Q[Retrieve Unresolved Reports]
    Q --> R{Are There Pending Reports?}

    R -->|No| S[Display No Pending Reports]
    S --> M

    R -->|Yes| T[Display All Pending Reports]
    T --> U[Calculate / Review Report Priority]
    U --> V[Select Report for Action]
    V --> W[Assign Sanitation Crew]
    W --> X[Dispatch Crew]
    X --> Y[Update Report Status to In Progress]
    Y --> Z[Notify Citizen of Progress]

    Z --> AA{Has Waste Problem Been Resolved?}
    AA -->|No| AB[Continue Monitoring]
    AB --> AA

    AA -->|Yes| AC[Update Status to Resolved]
    AC --> AD[Notify Citizen of Resolution]
    AD --> M
