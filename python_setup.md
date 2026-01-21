# Python setup for CNET 5442

This course uses a shared **conda environment** so that everyone can run the same notebooks with minimal friction.

---

## Step 0 — Install conda

If you do not already have conda installed:

- **Recommended:** Miniconda (lightweight)  
- **Also good:** Mambaforge (includes `mamba`, a faster dependency solver)

---

## Step 1 — Clone the class repo

```bash
git clone https://github.com/<ORG_OR_USER>/<REPO_NAME>.git
cd <REPO_NAME>
```

---

## Step 2 — Create the environment

### Option A: conda
```bash
conda env create -f environment.yml
conda activate cnet5442
```

### Option B: mamba (faster; recommended if conda solve is slow)
Install mamba once:
```bash
conda install -n base -c conda-forge mamba
```

Then create the environment:
```bash
mamba env create -f environment.yml
mamba activate cnet5442
```

---

## Step 3 — Add the environment to Jupyter (recommended)

```bash
python -m ipykernel install --user --name cnet5442 --display-name "Python (cnet5442)"
```

Now, when you open Jupyter Lab, you can pick the kernel **Python (cnet5442)**.

---

## Step 4 — Launch Jupyter

```bash
jupyter lab
```

---

## Updating the environment (later in the semester)

If the environment changes during the semester, run:

```bash
conda env update -f environment.yml --prune
conda activate cnet5442
```

(or replace `conda` with `mamba`)

---

## Troubleshooting

### “Solving environment…” takes forever
Use `mamba` (see above). It is dramatically faster for most students.

### Jupyter can’t find the kernel
Re-run:

```bash
conda activate cnet5442
python -m ipykernel install --user --name cnet5442 --display-name "Python (cnet5442)"
```

### Apple Silicon notes
If you are on Apple Silicon (M1/M2/M3), prefer conda-forge (this environment.yml already does). If you still run into issues, reach out on Canvas or during office hours with:
- your OS version
- the command you ran
- the full error message (copy/paste)
