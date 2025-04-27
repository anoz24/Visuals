## 1. Error Detection
**Definition:**  
Identifies whether errors occurred during transmission *without* correcting them.

### Mechanisms in Convolutional Systems
- Convolutional codes primarily correct errors
- Detection typically requires supplemental methods:
  - **CRC (Cyclic Redundancy Check)**
  - **ARQ (Automatic Repeat Request)**
  - **Parity bits**

### Common Detection Techniques
| Technique       | How It Works                          | Use Case                          |
|-----------------|---------------------------------------|-----------------------------------|
| CRC             | Adds polynomial-based checksum        | LTE, Wi-Fi packet verification    |
| ARQ             | Requests retransmission on error      | TCP/IP networks                   |
| Parity Bits     | Simple even/odd bit counting          | Basic error checking              |

**Limitations:**
- Cannot fix errors, only detect
- Requires retransmission (increases latency)

## 2. Error Correction
**Definition:**  
Automatically identifies *and fixes* transmission errors.

### Convolutional Code Correction
```math
Example: Rate 1/2 Encoder
c_i^(1) = u_i ⊕ u_{i-1} ⊕ u_{i-2}
c_i^(2) = u_i ⊕ u_{i-2}
```

### Decoding Algorithms
1. **Viterbi Algorithm**
   - Maximum likelihood sequence estimation
   - Uses trellis diagram traversal
   - Complexity: O(2^K) where K=constraint length

2. **Fano Algorithm**
   - Sequential decoding approach
   - Lower complexity for long constraint lengths
   - Variable computation time

### Performance Factors
- **Code Rate (R):** Lower rate → better correction
- **Constraint Length (K):** Longer → better performance
- **Free Distance (d_free):** Larger → more robust


## 3. Comparison Table
| Feature          | Error Detection       | Error Correction      |
|------------------|-----------------------|-----------------------|
| Retransmission   | Required              | Not needed            |
| Latency          | Higher                | Lower                 |
| Complexity       | Low                   | High                  |
| Best For         | File transfers        | Real-time comms       |
