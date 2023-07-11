Here is a simple flow chart:

```mermaid
flowchart TD
    A[Robot.py] ---> B
    A ---> C
    A ---> D
    subgraph Missions
    B[Mission1.py] 
    C[Mission2.py]
    D[Mission3.py]
    end
    subgraph Actions
    H[PathActions]
    I[MechinismActions]
    J[HubActions]
    end
    subgraph Subsystems
    L[DriveBaseSubsystems]
    M[MotorSubsystems]
    N[SensorSubsystems]
    end
    B & C & D -.- Q(are made of)
    Q -.- H & I & J
    H & I & J -.- P(are made of)
    P -.- L & M & N 

    E[MissionBase.py] -.-> Missions  
    F[PortMap.py] --> A
    G[PortMapPlus.py] --> F
    K[Actions.py] -.-> Actions
    R[Subsystems.py] --> Subsystems
    S[Kinimatics] -.- Subsystems
    T[Looper] -.- S
    T -..- Missions
    S -.-> H
```
