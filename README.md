# easyVVUQ-PROCESS: Feasibility Uncertainty Quantification (UQ)

A feasibility study using the PROCESS nuclear fusion power plant systems code and the easyVVUQ framework. It aims to assess the feasibility of two different power plant concepts under epistemic uncertainty.

A DEMO-like design is optimised using PROCESS for maximum net electric output, and a second design optimised for minimum major radius. UQ studies are then performed on these two design points to assess their comparative feasibilities under uncertainty.

## Installation

It is recommended to use a virtual environment. Firstly, Process needs to be installed. Clone Process

```bash
git clone https://github.com/ukaea/PROCESS/process-uq.git
```

Then install Process:

```bash
cd process-uq
cmake -S . -B build
cmake --build build
```

Secondly, clone this repository and install the `infeas` package:

```bash
cd ..
git clone https://github.com/jonmaddock/process-uq.git
cd process-uq
pip install .
```

Whether installed locally or on HPC, this should allow any of the notebooks in this repository to run.

## Using easyVVUQ to parallelise runs of PROCESS

To summarise the process, you need to create:

1. A job script which sumbits the job and creates the worker nodes.
2. A notebook which designs the campaign.
3. PROCESS inputs and outputs (create an IN.DAT, IN.DAT.template (copy of IN.DAT but with the uncertainties commented in $apsect format))
