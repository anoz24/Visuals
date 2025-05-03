   - Each node represents a **state** of the encoder, and each edge (or branch) represents a transition between states, labeled with the output codeword for that transition.

**1. What is Free Distance?**
   - The **free distance (\(d_{\text{free}}\))** of a convolutional code is the **minimum Hamming distance** between any two distinct paths in the trellis that start at the same state and diverge, then remerge later.
   - It is analogous to the **minimum distance** in block codes and determines the error-correcting capability of the code.

**2. How to Find Free Distance in a Trellis Diagram?**
   - **Step 1:** Identify the **all-zero codeword path** (usually the top path in the trellis).
   - **Step 2:** Find the **shortest path** that diverges from the all-zero path and later remerges to it.
   - **Step 3:** Calculate the Hamming distance between this path and the all-zero path.
   - The smallest such distance is the free distance.

**3. Example Calculation:**
   - Consider a simple convolutional code with trellis:
     - At time \(t_0\), the encoder is in state `00`.
     - A path diverges to state `10` and outputs `11` (distance = 2 from `00`).
     - Then, it remerges back to `00` after a few steps, with cumulative output `11 10 11` (total distance = 5).
   - The free distance is the minimum of all such possible paths (here, \(d_{\text{free}} = 5\)).

**4. Importance of Free Distance:**
   - A larger \(d_{\text{free}}\) means better error correction. For example:
     - The code can correct up to \(\left\lfloor \frac{d_{\text{free}} - 1}{2} \right\rfloor\) errors.
   - It is a key parameter in code design, influencing performance metrics like **coding gain**.
