# MSET: Multimodal Semantic-Enhanced Real-World Beam Prediction via Temporal Modeling with Visual Foundation Models

---

### Framework Architecture

MSET is a lightweight, efficient multimodal beam prediction framework tailored for real-world scenarios. It combines visual semantics, temporal modeling, and positional priors to achieve robust performance in complex and dynamic V2I environments.

<p align="center">
  <img src="photos/MSETframework.png" alt="Detailed Framework Overview" width="720"><br>
  <em>Figure: Overview of the proposed MSET framework.</em>
</p>

<p align="center">
  <img src="photos/TACA.png" alt="Detailed Framework Overview" width="720"><br>
  <em>Figure: The TACA fusion module.</em>
</p>

---

### Setup

Experiments are conducted on the DeepSense 6G dataset.

| Experimental Setup | Dataset Scenarios |
| :---: | :---: |
| ![Experimental Setup](photos/Scene.png) | ![Dataset Scenarios](photos/Scene1-8.png) |
| *Figure: Data collection platform.* | *Figure: Sample V2I scenarios.* |


---

## Experimental Results

### Task-Specific Performance

The model shows state-of-the-art performance when scenarios are grouped into more challenging, specific tasks.

| Single-Target Task | Multi-Target Task |
| :---: | :---: |
| ![Single-Target Task Results](photos/T1.png) | ![Multi-Target Task Results](photos/T2.png) |
| *Figure: Top-k accuracy (Scenarios 5-8).* | *Figure: Top-k accuracy (Scenarios 1-4).* |

| Nighttime Task | Daytime Task |
| :---: | :---: |
| ![Nighttime Task Results](photos/T3.png) | ![Daytime Task Results](photos/T4.png) |
| *Figure: Top-k accuracy (Scenarios 2, 4, 5).* | *Figure: Top-k accuracy (Scenarios 1, 3, 6, 7, 8).* |

### Error Analysis

Confusion matrices show that prediction errors are overwhelmingly concentrated on beams adjacent to the ground truth, indicating high reliability.

![Confusion Matrices](photos/CONFUSE.png)
*Figure: Row-normalized confusion matrices for beam prediction across the four tasks.*

### Protocol

We embed MSET into the 5G-Advanced beam management procedure. At each decision step, MSET predicts class probabilities and outputs a ranked Top-K list of candidate beams. The base station then probes only these K beams instead of sweeping the entire beam codebook.

<p align="center">
  <img src="photos/Protocols.png" alt="Protocol." width="720"><br>
  <em>*Figure: MSET-Assisted Beam Search and Tracking Protocol.*</em>
</p>

---

