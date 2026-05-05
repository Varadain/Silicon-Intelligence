## BRAINS IN SILICON 
Physical AI (PAI) systems interact with the real world using sensors, compute, and actuation.  
They operate as a closed loop:

Sensors → Perception → Cognition → Action → Feedback → Learning


This repo explains:
- Core intelligence layers
- AI models used in each layer
- Hardware mapping (RTL, FPGA, SoC)
- System-level design thinking

---

## Intelligence Stack

| Layer                  | Role                         | Output Type         |
|------------------------|------------------------------|---------------------|
| Perceptive Intelligence | Understand environment        | Features / Objects  |
| Cognitive Intelligence  | Decide what to do             | Decisions / Plans   |
| Sensorimotor Intelligence | Execute actions             | Control Signals     |
| Continuous Intelligence | Improve over time            | Updated Models      |

---

## 1. Cognitive Intelligence

### Simple Meaning
- Thinking and decision-making layer

### Everyday Example
- Choosing shortest route in traffic

### Technical Meaning
- Reasoning, planning, memory-based decisions
- Works under uncertainty

### AI Models
| Model Type | Purpose |
|------------|--------|
| LLM        | Planning, reasoning |
| RL         | Decision optimization |
| Symbolic AI| Rule-based logic |

### Hardware Mapping
| Component | Role |
|----------|------|
| CPU      | Control logic |
| GPU      | Parallel compute |
| NPU      | AI acceleration |

### Key Equations
- Optimal action:

a* = argmax_a Q(s, a)


- MDP:

(S, A, P, R, γ)


---

## 2. Perceptive Intelligence

### Simple Meaning
- Understanding surroundings from sensors

### Everyday Example
- Seeing red light and stopping

### Technical Meaning
- Converts raw sensor data → structured information

### AI Models
| Model | Use |
|------|-----|
| CNN  | Image processing |
| ViT  | Vision transformer |
| Fusion Models | Multi-sensor data |

### Data Pipeline

Sensor → ADC → Preprocessing → CNN → Feature Extraction


### Hardware Mapping
| Block | Function |
|------|----------|
| MAC Units | Multiply-accumulate |
| DSP Blocks | Signal processing |
| Memory | Feature storage |

### Key Equation
- Convolution:

y(i,j) = Σ x(m,n) * w(i-m, j-n)


---

## 3. Sensorimotor Intelligence

### Simple Meaning
- Acting based on input

### Everyday Example
- Touch hot object → remove hand instantly

### Technical Meaning
- Closed-loop control system

### Control Loop

Input → Controller → Output → Feedback → Correction


### Applications
- Robotics
- Drones
- Autonomous driving

### Hardware Mapping
| Element | Implementation |
|--------|----------------|
| Controller | FSM / RTL |
| Feedback | Sensors |
| Execution | Actuators |

### Key Equation (PID Controller)

u(t) = Kp e(t) + Ki ∫e(t)dt + Kd de/dt


---

## 4. Continuous Intelligence

### Simple Meaning
- Learning over time

### Everyday Example
- Getting better at driving daily

### Technical Meaning
- Online learning + streaming updates

### AI Models
| Model | Use |
|------|-----|
| Online RL | Adaptive systems |
| Streaming ML | Real-time updates |

### Hardware Mapping
| Platform | Role |
|---------|------|
| FPGA    | Adaptive logic |
| ASIC    | Efficient inference |

### Key Equations
- Gradient update:

θ = θ - η ∇L(θ)


- Power:

P = αCV²f


---

## Hardware Perspective (VLSI Focus)

| Layer        | Hardware Concern          |
|--------------|--------------------------|
| Perception   | Throughput, memory BW    |
| Cognition    | Compute, scheduling      |
| Control      | Latency, determinism     |
| Learning     | Power, adaptability      |

---

## Key Engineering Constraints

| Constraint | Description |
|-----------|------------|
| Latency   | Time to respond |
| Throughput| Data processed/sec |
| Power     | Energy efficiency |
| Area      | Silicon cost |

---

## Summary

- Perception → Understand  
- Cognition → Decide  
- Action → Execute  
- Continuous → Improve
