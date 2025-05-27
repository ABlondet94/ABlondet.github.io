# Distributed Denial of Service (DDoS) Attack - Sequence Diagram

```mermaid
sequenceDiagram
    participant Attacker
    participant Botnet
    participant Firewall
    participant TargetServer
    participant MonitoringSystem

    Attacker->>Botnet: Command bots to initiate DDoS
    loop Amplified Requests
        Botnet->>TargetServer: Flood with HTTP requests
    end

    TargetServer->>Firewall: Send traffic for filtering
    Firewall-->>TargetServer: Allow/Deny/report based on rules
    Firewall->>MonitoringSystem: Alert high traffic levels

    MonitoringSystem->>Firewall: Trigger mitigation (rate limiting, block IPs)
    Firewall->>Botnet: Block malicious IPs

    TargetServer-->>LegitimateUsers: Service degradation or denial

