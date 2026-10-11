# Imaging, DSP & Coding

Bitstream arithmetic shines when the **output quality metric** is perceptual (PSNR / SSIM) or algorithmic (BER after iterations), not bit-exact equality.

---

## Imaging & DSP

Classic SC case studies encode pixels or filter coefficients as densities, then implement:

- Local thresholding and morphological-style ops
- FIR-like filtering with scaled MUX adds
- Edge / texture features where small density errors vanish after quantization to display bits

```mermaid
graph LR
    Img[Pixels] --> SNG[SNG / B2S]
    SNG --> Kern[SC kernel: AND / MUX / counter]
    Kern --> Dec[Decode / binary out]
    Dec --> Metric[PSNR · SSIM · task score]
```

**Design tip:** compare energy at **iso-PSNR** (or iso-task), not iso-$N$. A longer stream that wastes energy is not a win.

---

## Coding & communications

Iterative soft decoders (LDPC, turbo-like BP, MIMO detection) already pass **messages that are probabilities**. Mapping those messages to stochastic wires can shrink check-node / variable-node logic, especially in fully parallel layouts.

Challenges unique to this domain:

| Issue | Why it matters |
| :--- | :--- |
| BER cliffs | Small message bias can raise error floors |
| Throughput | Frame latency vs stream length $N$ |
| Mixed signal / CIM | New MS-SCIM style datapaths need careful SNR budgeting |

---

## Shared lesson across both bridges

Applications succeed when designers treat SC as a **noise channel with a known model**, then allocate $N$, parallelism, and hybrid binary stages the way a communications engineer allocates SNR.

Continue with taxonomies:

- [DSP-oriented arithmetic](../taxonomy/stochastic-arithmetic.md)
- [Coding & Communications](../taxonomy/coding-communications.md)

---

## 📚 DOI starting points

- Stochastic Phansalkar thresholding architecture: [DOI 10.1109/TVLSI.2023.3348809](https://doi.org/10.1109/TVLSI.2023.3348809)
- Parallel stochastic multiplier for signal processing: [DOI 10.1109/TVLSI.2026.3722919](https://doi.org/10.1109/TVLSI.2026.3722919)
- Fully parallel stochastic LDPC decoder: [DOI 10.1109/TVLSI.2024.3488716](https://doi.org/10.1109/TVLSI.2024.3488716)
- Stochastic BP iterative detection & decoding: [DOI 10.1109/TVLSI.2024.3477963](https://doi.org/10.1109/TVLSI.2024.3477963)
