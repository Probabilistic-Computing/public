# Glossary of Probabilistic & Stochastic Computing

Concise definitions for core ideas used across this portal. For paper-level browsing, use the [PC Paper Map](https://probabilistic-computing.github.io/.github/).

---

### **Bipolar encoding**
Maps a real value $x \in [-1, 1]$ to a bitstream whose fraction of 1s equals $(x+1)/2$. Useful when products and signed weights appear together (e.g. neural layers).

### **Bitstream / Stochastic number**
A finite sequence of random bits whose **empirical mean** approximates a real value in $[0,1]$ (unipolar) or $[-1,1]$ (bipolar). Longer streams reduce variance.

### **Correlation (SC)**
Statistical dependence between two bitstreams. Multipliers implemented as `AND` (unipolar) or `XNOR` (bipolar) assume **independent** streams; shared RNG seeds create correlation that bias products.

### **Deterministic SC / Low-discrepancy streams**
Uses carefully constructed bit patterns (e.g. Sobol, Halton, clock-division) so that short stream lengths achieve low error without relying on pure randomness.

### **Invertible logic**
Networks of probabilistic devices whose Boltzmann-like steady state encodes solutions to combinatorial constraints; “invertible” in the sense that outputs can be clamped to solve for inputs.

### **LFSR (Linear Feedback Shift Register)**
Cheap pseudo-random bit generator used as an RNG or SNG seed source. Period and pairwise independence depend on polynomial choice and seeding.

### **p-bit (probabilistic bit)**
A tunable random bit whose $P(1)$ is a sigmoid of a real-valued input (often built from stochastic MTJ / CMOS circuits). Building block for Ising / Boltzmann machines in hardware.

### **RNG / SNG**
**Random Number Generator** produces bits or integers; **Stochastic Number Generator** converts a binary value $x$ into a bitstream with mean $\approx x$ (commonly via comparator + RNG).

### **SC (Stochastic Computing)**
Arithmetic style introduced in the 1960s where values are probabilities (bitstream densities) and gates implement multiply / add / divide with tiny area.

### **SEU / Soft error resilience**
Because information is distributed across many bits of a stream, flipping a few bits often changes the decoded value only slightly — a classic reliability argument for SC.

### **Unary computing**
Related rate-coded style that may use thermometer or pulse-density codes; overlaps with SC in edge-AI literature when MACs become AND-popcount style units.

### **Unipolar encoding**
Maps $x \in [0,1]$ directly to $P(\text{bit}=1)=x$. Unipolar multiply is a bitwise `AND` under independence.

---

## Symbols used in this portal

| Symbol | Meaning |
| :--- | :--- |
| $N$ | Bitstream length (clock cycles) |
| $\hat{x}$ | Estimate of value $x$ from $N$ bits |
| $\sigma^2$ | Variance of the estimator (scales $\sim 1/N$ for i.i.d. Bernoulli) |
| $\rho$ | Pairwise correlation between streams |
