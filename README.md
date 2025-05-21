This flowchart visualizes the research plan, outlining the different phases, their respective tasks, and timelines. 

```mermaid
graph TD
    %% Define Phases
    P1["<strong>Phase 1: Foundational Research & Problem Formalization</strong><br/>(Months 1-9)"]
    P2["<strong>Phase 2: KGML Model Design & Development</strong><br/>(Months 10-24)<br/><em>Overlaps with Phase 3 (M19-24)</em>"]
    P3["<strong>Phase 3: Experimentation & Evaluation</strong><br/>(Months 19-30)<br/><em>Overlaps with Phase 2 (M19-24) & Phase 4 (M28-30)</em>"]
    P4["<strong>Phase 4: Refinement, Thesis Compilation, & Dissemination</strong><br/>(Months 28-36)"]

    %% Connect Phases
    P1 --> P2
    P2 --> P3
    P3 --> P4

    %% Phase 1 Tasks
    subgraph Phase 1 Tasks
        direction LR
        T1_1["Conduct extensive literature review (KGML, ML for CO, Pointer Networks, Transformers, Knowledge Representation)"]
        T1_2["Formally define optimization problems & identify specific domain knowledge"]
        T1_3["Develop strong theoretical understanding of ML architectures & potential knowledge infusion points"]
    end
    P1 --> T1_1
    T1_1 --> T1_2
    T1_2 --> T1_3

    %% Phase 2 Tasks
    subgraph Phase 2 Tasks
        direction TB
        T2_1["Baseline Model Implementation (Standard Pointer Network & Transformer models)"]
        T2_2["Knowledge Integration Strategies"]
        T2_2_1["- Knowledge-Infused Architectures (Modify input/network components)"]
        T2_2_2["- Knowledge-Regularized Loss Functions (Penalize constraint violations)"]
        T2_2_3["- Knowledge-Guided Pre-training/Initialization"]
        T2_3["Implementation (Python, PyTorch/TensorFlow)"]
    end
    P2 --> T2_1
    T2_1 --> T2_2
    T2_2 --> T2_2_1
    T2_2 --> T2_2_2
    T2_2 --> T2_2_3
    T2_2_1 --> T2_3
    T2_2_2 --> T2_3
    T2_2_3 --> T2_3

    %% Phase 3 Tasks
    subgraph Phase 3 Tasks
        direction TB
        T3_1["Datasets: Utilize well-established benchmark datasets (TSPLIB, etc.)"]
        T3_2["Evaluation Metrics: Solution Quality, Computational Efficiency, Scalability, Generalization"]
        T3_3["Comparative Analysis: KGML models vs. baselines"]
        T3_4["Interpretability Analysis (Attention viz, SHAP values, etc.)"]
    end
    P3 --> T3_1
    T3_1 --> T3_2
    T3_2 --> T3_3
    T3_3 --> T3_4

    %% Phase 4 Tasks
    subgraph Phase 4 Tasks
        direction LR
        T4_1["Iteratively refine KGML models based on experimental results"]
        T4_2["Analyze results, draw conclusions, identify limitations & future research"]
        T4_3["Write PhD thesis"]
        T4_4["Disseminate findings (Publications, Conferences)"]
    end
    P4 --> T4_1
    T4_1 --> T4_2
    T4_2 --> T4_3
    T4_3 --> T4_4

    %% Styling (optional, might not render in all markdown viewers)
    classDef phase fill:#E1BEE7,stroke:#6A1B9A,stroke-width:2px,color:#4A148C,font-weight:bold,rx:5,ry:5
    classDef task fill:#C5CAE9,stroke:#303F9F,stroke-width:1px,color:#1A237E,rx:5,ry:5
    class P1,P2,P3,P4 phase
    class T1_1,T1_2,T1_3,T2_1,T2_2,T2_2_1,T2_2_2,T2_2_3,T2_3,T3_1,T3_2,T3_3,T3_4,T4_1,T4_2,T4_3,T4_4 task
