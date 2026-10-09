
# qiskit-art-sandbox

Learning and prototyping repository for quantum computing applied to interactive XR art.  
Part of my PhD research proposal: **"Collapse as Interaction – Quantum computation as a material for immersive and participatory art"**  

---

## About

This repository documents my self-study of Qiskit and quantum computing fundamentals, with a focus on using **quantum measurement as an interaction event** in embodied XR environments. All code is written from a learner's perspective – I am a beginner in quantum computing, and this sandbox reflects my progress.

The long-term goal is to build an open-source bridge (`xr-quantum-bridge`) that connects Qiskit backends to Unity/Unreal, enabling real-time quantum-driven spatial and sonic experiences.

---

## Repository Structure


qiskit-art-sandbox/
├── qrng_compare/            # Quantum vs pseudo-random number generation
│   ├── run.py               # Compare Hadamard-based QRNG with numpy seeded RNG
│   └── plots/               # Histograms and statistical comparisons
├── bell_sound_mapping/      # Bell pair → stereo/sound mapping prototype
│   ├── bell_to_stereo.py    # Map Bell measurement outcomes to left/right panning
│   └── bell_to_tone.py      # Generate tones based on correlation strength
├── collapse_demo/           # Prepare-gate → measure → export JSON for XR
│   ├── run_collapse.py      # Build a circuit, measure, output counts + shot list
│   └── export_shots.json    # Example output consumable by Unity/Unreal
├── notebooks/               # Jupyter notebooks for visual explanations
│   └── superposition_basics.ipynb
├── requirements.txt         # Python dependencies
├── config_example.env       # Environment variable template for IBMQ token
└── README.md                # This file


---

## Getting Started

### Prerequisites
- Python 3.9+
- pip

### Install
bash
git clone https://github.com/fnightj/qiskit-art-sandbox.git
cd qiskit-art-sandbox
pip install -r requirements.txt


### Run Examples
bash
QRNG comparison

python qrng_compare/run.py

Bell pair sound mapping

python bell_sound_mapping/bell_to_stereo.py

Collapse demo – generate JSON for XR

python collapse_demo/run_collapse.py


### Optional: Use Real Quantum Hardware
To run circuits on IBM Quantum backends:
1. Copy `config_example.env` to `.env`
2. Fill in your IBM Quantum API token (get one free at [quantum-computing.ibm.com](https://quantum-computing.ibm.com))
3. Set `USE_REAL_BACKEND=True` in the script or pass `--backend ibm_qpu`

> ⚠️ Never commit your token. The `.env` file is excluded via `.gitignore`.

---

## Relation to My Research Proposal

This sandbox directly supports the technical foundation of my proposed PhD:

| RP Component | Sandbox Module |
|--------------|----------------|
| Shot pool (pre-run batch + buffer) | `collapse_demo` exports shot lists as JSON, simulating the buffer architecture |
| Spatial-sonic mapping grammar | `bell_sound_mapping` explores qubit → pan/volume/timbre mapping |
| Perceptual study design | `qrng_compare` provides the quantum vs classical comparison logic |

The full proposal is available upon request.

---

## Learning Path

- [x] Superposition & measurement basics (Qiskit textbook)
- [x] Single-qubit gates, Bloch sphere visualization
- [x] Multi-qubit circuits, Bell states, entanglement
- [ ] Quantum noise models and mitigation (planned Year 1)
- [ ] Integration with Unity WebSocket client (see `xr-quantum-bridge` repo)
- [ ] Real hardware execution with error mitigation

---

## Disclaimer

I am a quantum computing **beginner**. This repository represents my active learning process. Code is provided as-is for educational and demonstrative purposes. Circuit designs for actual artworks will be reviewed by a collaborating physicist.

---

## License

MIT – feel free to use, adapt, and share.

---

## Contact

Jing Fu – [fu2en1@icloud.com](mailto:fu2en1@icloud.com)  
GitHub: [github.com/fnightj](https://github.com/fnightj)
