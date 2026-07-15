# Homelab Oracle 26ai RAC Project

## Network Topology

graph TD
    %% Define styles for distinct cabling colors
    classDef publicCable stroke:#0066cc,stroke-width:2px,stroke-dasharray: 0;
    classDef privateCable stroke:#009933,stroke-width:2px,stroke-dasharray: 0;
    classDef storageCable stroke:#cc0000,stroke-width:2px,stroke-dasharray: 0;
    
    classDef router fill:#f9f9f9,stroke:#333,stroke-width:2px;
    classDef switch fill:#e1f5fe,stroke:#0288d1,stroke-width:2px;
    classDef node fill:#fff3e0,stroke:#f57c00,stroke-width:2px;
    classDef nas fill:#eceff1,stroke:#455a64,stroke-width:2px;

    %% Hardware Layers
    Router[YOUR EXISTING HOME ROUTER<br/>Subnet: 192.168.1.X]:::router
    
    Switch1[SWITCH 1: PRIVATE INTERCONNECT<br/>TP-Link TL-SG105<br/>Subnet: 10.10.10.X]:::switch
    Switch2[SWITCH 2: iSCSI STORAGE<br/>TP-Link TL-SG105<br/>Subnet: 172.16.10.X]:::switch

    subnetwork1[Dell Node 1]:::node
    subnetwork2[Dell Node 2]:::node
    subnetwork3[Dell Node 3]:::node
    NAS[Synology NAS]:::nas

    %% Public Network Connections (Blue Cables)
    Router -->|Blue Cable| N1_Pub(Node 1: Built-in NIC<br/>192.168.1.101)
    Router -->|Blue Cable| N2_Pub(Node 2: Built-in NIC<br/>192.168.1.102)
    Router -->|Blue Cable| N3_Pub(Node 3: Built-in NIC<br/>192.168.1.103)
    Router -->|Blue Cable| NAS_P1(NAS: LAN Port 1<br/>192.168.1.50)

    %% Private Interconnect Connections (Green Cables)
    N1_Priv(Node 1: USB NIC 1<br/>10.10.10.101) -->|Green Cable| Switch1
    N2_Priv(Node 2: USB NIC 1<br/>10.10.10.102) -->|Green Cable| Switch1
    N3_Priv(Node 3: USB NIC 1<br/>10.10.10.103) -->|Green Cable| Switch1

    %% iSCSI Storage Connections (Red Cables)
    N1_Stor(Node 1: USB NIC 2<br/>172.16.10.101) -->|Red Cable| Switch2
    N2_Stor(Node 2: USB NIC 2<br/>172.16.10.102) -->|Red Cable| Switch2
    N3_Stor(Node 3: USB NIC 2<br/>172.16.10.103) -->|Red Cable| Switch2
    NAS_P2(NAS: LAN Port 2<br/>172.16.10.50) -->|Red Cable| Switch2

    %% Subgraph groupings to tie physical NICs to their hardware units
    subgraph subnetwork1 [Dell Micro Node 1]
        N1_Pub
        N1_Priv
        N1_Stor
    end

    subgraph subnetwork2 [Dell Micro Node 2]
        N2_Pub
        N2_Priv
        N2_Stor
    end

    subgraph subnetwork3 [Dell Micro Node 3]
        N3_Pub
        N3_Priv
        N3_Stor
    end

    subgraph NAS_Unit [Synology Storage unit]
        NAS_P1
        NAS_P2
    end

    %% Apply cable styling rules to line classes
    linkStyle 0,1,2,3 class:publicCable;
    linkStyle 4,5,6 class:privateCable;
    linkStyle 7,8,9,10 class:storageCable;


