# Solution Architecture

Combining AWS services together to solve a problem.

## Problem Methodology

1. solve architecture
2. Apply Well architected FrameWork via 5 pillars of operational excellence

### 1. (C)ost Optimisation

### 2. (R)eliability (Availability)

### 3. (O)perational Excellence

Run and monitor systems and continuously improve.

### 4. (P)erformance Efficiency (Scalability)

### 5. (S)ecurity

### Well Architected Tool

Asks a whole bunch of questions for each of the 5 pillars.

## Reference Architectures

https://aws.amazon.com/architecture/  
https://aws.amazon.com/solutions/

## Definitions

### Stateless Application

Does **not** save client data generated in one session for use in the next session with that client.

For example a REST API is a stateless serverside application architecture because all the inforamtion required by the server to generate a response is specified in the request.

### Stateful Application

**Does** save client data between sessions.
