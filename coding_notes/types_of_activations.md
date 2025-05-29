### **1. ReLU (Rectified Linear Unit)**  
**Function:** `f(x) = max(0, x)`  
**Pros:**  
- Computationally efficient (no exponential operations).  
- Avoids the vanishing gradient problem (for positive inputs).  
- Sparsifies activations (can lead to more efficient representations).  

**Cons:**  
- "Dying ReLU" problem (neurons can get stuck in negative region and stop learning).  
- Not zero-centered.  

**Best Used For:**  
- Hidden layers in most deep learning models (CNNs, MLPs).  
- Default choice for many architectures unless a specific need arises.  

---

### **2. Sigmoid (Logistic)**  
**Function:** `f(x) = 1 / (1 + exp(-x))`  
**Output Range:** `(0, 1)`  

**Pros:**  
- Smooth gradient.  
- Interpretable as a probability.  

**Cons:**  
- Suffers from vanishing gradients (saturates for very large/small inputs).  
- Not zero-centered (can slow down training).  

**Best Used For:**  
- Binary classification output layers (predicting probabilities).  
- Not recommended for hidden layers in deep networks.  

---

### **3. Softmax**  
**Function:** `f(x_i) = exp(x_i) / sum(exp(x_j))` (normalizes to probability distribution)  
**Output Range:** `(0, 1)` (sums to 1)  

**Pros:**  
- Directly outputs probabilities for multi-class problems.  

**Cons:**  
- Sensitive to large input values (can cause numerical instability).  

**Best Used For:**  
- Multi-class classification output layers.  

---

### **4. TanH (Hyperbolic Tangent)**  
**Function:** `f(x) = (exp(x) - exp(-x)) / (exp(x) + exp(-x))`  
**Output Range:** `(-1, 1)`  

**Pros:**  
- Zero-centered (helps with optimization).  
- Stronger gradients than sigmoid.  

**Cons:**  
- Still suffers from vanishing gradients at extremes.  

**Best Used For:**  
- Hidden layers in some cases (e.g., RNNs, where zero-centering helps).  
- Less common than ReLU in modern deep learning.  

---

### **5. Leaky ReLU**  
**Function:** `f(x) = x if x > 0 else αx` (α is a small slope, e.g., 0.01)  

**Pros:**  
- Fixes the "dying ReLU" problem by allowing a small gradient for negative inputs.  

**Cons:**  
- Requires tuning α in some cases (though often set to 0.01 by default).  

**Best Used For:**  
- Hidden layers where dying neurons are a concern.  
- Alternative to ReLU in deep networks.  

---

### **6. PReLU (Parametric ReLU)**  
**Function:** Like Leaky ReLU, but α is learned during training.  

**Pros:**  
- Adapts the negative slope for better performance.  

**Cons:**  
- Slightly more computationally expensive than ReLU.  

**Best Used For:**  
- Deep networks where learning the slope improves performance.  

---

### **7. ELU (Exponential Linear Unit)**  
**Function:** `f(x) = x if x > 0 else α(exp(x) - 1)`  

**Pros:**  
- Avoids dying ReLU problem.  
- Smoother than ReLU for negative values (can improve convergence).  

**Cons:**  
- More computationally expensive due to exponential.  

**Best Used For:**  
- Deep networks where robustness to dying neurons is critical.  

---

### **8. SELU (Scaled Exponential Linear Unit)**  
**Function:** `λ * ELU(x, α)` (with specific λ and α values for self-normalization)  

**Pros:**  
- Enables self-normalizing networks (avoids need for BatchNorm).  

**Cons:**  
- Requires careful weight initialization (lecun_normal).  

**Best Used For:**  
- Deep feedforward networks without BatchNorm.  

---

### **9. Softplus**  
**Function:** `f(x) = log(1 + exp(x))`  

**Pros:**  
- Smooth approximation of ReLU.  

**Cons:**  
- Computationally expensive.  

**Best Used For:**  
- Rarely used in practice; sometimes in regression tasks.  

---

### **10. Softsign**  
**Function:** `f(x) = x / (1 + |x|)`  

**Pros:**  
- Smoother alternative to TanH.  

**Cons:**  
- Rarely outperforms ReLU-based activations.  

**Best Used For:**  
- Occasionally in recurrent networks.  

---

### **11. Swish**  
**Function:** `f(x) = x * sigmoid(x)`  

**Pros:**  
- Outperforms ReLU in some deep networks.  
- Smooth gradient (helps optimization).  

**Cons:**  
- Slightly more expensive than ReLU.  

**Best Used For:**  
- Deep networks where ReLU underperforms (e.g., some Transformer models).  

---

### **12. Gaussian Error Linear Unit (GELU)**  
**Function:** `f(x) = x * Φ(x)` (where Φ is the Gaussian CDF)  

**Pros:**  
- Used in state-of-the-art models like GPT and BERT.  
- Smooth approximation of ReLU.  

**Cons:**  
- More expensive to compute.  

**Best Used For:**  
- Transformer-based models (e.g., BERT, GPT).  

---

### **Summary of Recommendations**  
| Activation Function  | Best Use Case                                       |
| -------------------- | --------------------------------------------------- |
| **ReLU**             | Default for hidden layers (CNNs, MLPs)              |
| **Leaky ReLU/PReLU** | If dying neurons are a concern                      |
| **SELU**             | Deep FFNs without BatchNorm                         |
| **Sigmoid**          | Binary classification output                        |
| **Softmax**          | Multi-class classification output                   |
| **TanH**             | RNNs (less common now)                              |
| **Swish/GELU**       | High-performance deep networks (e.g., Transformers) |
