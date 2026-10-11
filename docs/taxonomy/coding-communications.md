# Coding & Communications

Stochastic representations fit iterative soft inference: LDPC decoding, belief propagation, and MIMO detection where messages are probabilities.

---

## Why SC appears in decoders

```mermaid
graph LR
    CH[Channel LLRs] --> MSG[Soft messages]
    MSG --> SC[Bitstream / hybrid SC nodes]
    SC --> IT[BP / turbo-like iterations]
    IT --> DEC[Hard decisions]
    DEC --> BER[BER / FER]
```

- Check / variable node updates become **tiny logic** on wires that already mean probabilities.
- Fully parallel maps trade wires and SNGs for high throughput at low energy per bit when BER targets allow.

---

## Design tensions

| Tension | Comment |
| :--- | :--- |
| BER vs energy | Aggressive approximation can lift error floors |
| Bit-width accumulation | Hybrid recoding schemes manage growing precision |
| Mixed-signal CIM | MS-SCIM blends analog entropy with digital control |

Background: [Imaging, DSP & Coding](../bridge/imaging-dsp-coding.md).

---

## 📚 Primary literature (DOI only)

- Fully parallel stochastic LDPC decoder: [DOI 10.1109/TVLSI.2024.3488716](https://doi.org/10.1109/TVLSI.2024.3488716)
- Stochastic BP iterative detection & decoding: [DOI 10.1109/TVLSI.2024.3477963](https://doi.org/10.1109/TVLSI.2024.3477963)
- Mixed-signal SC-in-memory paradigm (MS-SCIM): [DOI 10.1109/TCSI.2024.3501383](https://doi.org/10.1109/TCSI.2024.3501383)
- Recoding hybrid stochastic numbers: [DOI 10.1109/TCSI.2024.3492054](https://doi.org/10.1109/TCSI.2024.3492054)

Domain browse: [Paper Map → Coding & Communications](https://probabilistic-computing.github.io/.github/).
