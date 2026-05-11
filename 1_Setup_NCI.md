# Intro to Nextflow on NCI (Gadi) — Setup

This workshop uses the National Computational Infrastructure (NCI) Gadi supercomputer to run Nextflow workflows without requiring local software installation.

---

# Prerequisites

Before the workshop you should have:

- An active NCI account
- Access to Gadi via SSH
- Access to a project allocation (we will use ad30 for this workshop)
- Basic command-line familiarity

You should be able to log in successfully:

```bash
ssh <username>@gadi.nci.org.au
```

---

# Clone the Workshop Repository

Choose a suitable working location such as:

- `/g/data/ad30/<username>/`

Example:

```bash
cd /g/data/ad30/joecop
git clone https://github.com/<ORG>/nextflow-intro-nci.git
cd nextflow-intro-nci
```

---
# Start a persistent session

This step is recommended for longer running jobs. Running nextflow on the login node will likely be killed by the system. 

```bash
persistent-sessions start -p ad30 <sessionname>
ssh <sessionname>.<username>.ad30.ps.gadi.nci.org.au
```

example:
```bash
jxc569@gadi-login-07: ~$ persistent-sessions start -p ad30 joe 
session a98ffc77-7fbf-f1a1-8d16-9617d2924cfd running - connect using
  ssh joe.jxc569.ad30.ps.gadi.nci.org.au
```

# Load Required Modules

Load the software modules required for the workshop.

```bash
module load nextflow
module load singularity
module load fastqc
```

Verify installation:

```bash
nextflow -version
singularity --version
fastqc --version
```

---

# Test Your Environment

Run a quick test:

```bash
nextflow run hello
```

You should see output similar to:

```text
N E X T F L O W  ~  version ...
Launching `https://github.com/nextflow-io/hello`
```

If this works, your environment is ready.

---

# During the Workshop

We will work through:

1. Running a simple Hello World workflow
2. Understanding processes and channels
3. Running a small bioinformatics workflow
4. Using Nextflow resume and caching

---

# Useful References

- [Nextflow Documentation](https://www.nextflow.io/docs/latest/index.html?utm_source=chatgpt.com)
- [NCI Gadi User Guide](https://opus.nci.org.au/display/Help/Gadi+User+Guide?utm_source=chatgpt.com)
- [nf-core](https://nf-co.re?utm_source=chatgpt.com)

---