```mermaid
graph TD
    A[Landing & ULPIN Search View] -->|Valid ULPIN Entered| B[Plot Overview State]
    B -->|Selects Building| C[Multi-Storey View State]
    C -->|Selects Specific Floor/Unit| D[Room Breakdown View State]
    D -->|Click Reset / New Search| A
