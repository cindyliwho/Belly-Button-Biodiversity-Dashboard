# Belly Button Biodiversity Dashboard (Interactive Web Visualization)

## Overview
This project is a small **interactive dashboard** that lets you explore the *Belly Button Biodiversity* dataset. It’s a front-end web app built with **D3.js** and **Plotly** that:

- Lets users choose a **Test Subject ID** from a dropdown
- Displays that subject’s **demographic metadata**
- Plots the **Top 10 bacterial OTUs** found in the sample (bar chart)
- Plots **all OTUs** for the sample as a bubble chart (size = abundance, color = OTU id)

The page layout and UI containers are defined in `index.html` :contentReference[oaicite:0]{index=0}, while all interactive behavior (data loading + chart updates) is handled in `app.js` :contentReference[oaicite:1]{index=1}. The dataset structure includes `names`, `metadata`, and `samples` :contentReference[oaicite:2]{index=2}.

> Note: The HTML includes a container for a **gauge chart** (`<div id="gauge"></div>`) :contentReference[oaicite:3]{index=3}, but the provided `app.js` currently builds **only the bar + bubble + metadata** views :contentReference[oaicite:4]{index=4}.

---

## Features
### Dropdown Selection
On page load, the app fetches the dataset and populates the dropdown with subject IDs (`data.names`) :contentReference[oaicite:5]{index=5}.

### Demographic Info Panel
When you select a subject ID, the dashboard renders demographic details (age, location, ethnicity, wash frequency, etc.) from `data.metadata` .

### Top 10 OTUs Bar Chart
Creates a horizontal bar chart of the **top 10 OTUs** (operational taxonomic units) by sample value :contentReference[oaicite:7]{index=7}.

### OTU Bubble Chart
Creates a bubble chart showing **all OTUs** for the selected subject:
- x = OTU IDs
- y = sample values (abundance)
- marker size = sample values
- marker color = OTU ID :contentReference[oaicite:8]{index=8}

---

## Data Source
The JavaScript currently pulls the dataset from a hosted JSON URL :contentReference[oaicite:9]{index=9}.

The dataset format contains:
- `names`: list of subject IDs
- `metadata`: demographic info for each subject
- `samples`: OTU IDs, OTU labels, and sample values per subject :contentReference[oaicite:10]{index=10}

(There is also a `samples.json` file included in the repo that matches this structure.) :contentReference[oaicite:11]{index=11}

---

## Tech Stack
- **HTML + Bootstrap** (layout + styling) :contentReference[oaicite:12]{index=12}
- **JavaScript**
- **D3.js** (loading JSON + DOM updates) 
- **Plotly.js** (charts) 

---
