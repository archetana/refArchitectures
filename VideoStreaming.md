flowchart TB

subgraph clientLayer[Client Layer]
    classDef person fill:#08427b
    A[User's Device]:::person
    B[Facebook App/Website]
    D[User Interface]
end

subgraph networkLayer[Network Infrastructure Layer]
    classDef internalContainer fill:#1168bd
    K[High-speed Internet]:::internalContainer
    L[Load Balancers]:::internalContainer
end

subgraph middlewareLayer[Middleware Layer]
    classDef internalContainer fill:#1168bd
    E[CDN]:::internalContainer
    F[Video Streaming Servers]:::internalContainer
end

subgraph backendLayer[Backend Layer]
    classDef internalContainer fill:#1168bd
    G[Video Encoding & Compression]:::internalContainer
    H[Video Database]:::internalContainer
    I[Recommendation Engine]:::internalContainer
    J[Auth & Authorization]:::internalContainer
end

subgraph monitoringLayer[Monitoring and Analytics Layer]
    classDef internalContainer fill:#1168bd
    M[Real-time Monitoring]:::internalContainer
    N[Data Analytics]:::internalContainer
end

subgraph securityLayer[Security Layer]
    classDef internalContainer fill:#1168bd
    O[Encryption]:::internalContainer
    P[User Data Protection]:::internalContainer
end

A -->|Requests| B
B -->|Internet| K
K -->|Balancing| F
F -->|Video Data| H
F -->|CDN| E
H -->|Store/Retrieve| F
F -->|Compression| G
F -->|Video Stream| E
E -->|Controls| F
D -->|Access Control| J
D -->|Recommendations| I
B -->|UI| D
N -->|Data| H
M -->|Performance| F
O -->|Data| H
P -->|User Privacy| D
