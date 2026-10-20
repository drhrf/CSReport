# Your paper needs a buddy: using companion statistical reports

Class materials · NTS School 2026, Montevideo · Hércules Rezende Freitas (LabInfoS / NEC, UERJ)

## For students

**Slides (run in your browser):** https://drhrf.github.io/CSReport/NTS_School_2026/

The page has links to the slides and to every file below. The R code on the slides runs inside
your browser (webR): wait for the yellow "Downloading webR" badge to disappear (10–30 s), then
press **Run Code** on any code box. You can edit the code and run it again.

| File | What it is |
|---|---|
| `materials/CSR_Template_Word.docx` | Blank CSR in Word, with guidance in grey (exercise, track A) |
| `materials/CSR_Example_WaterMaze.docx` | The template filled in for the water-maze example |
| `materials/csr_demo.qmd` | Executable CSR in Quarto, base R only (exercise, track B) |
| `materials/maze.csv` | Simulated data: 12 mice × 4 trials |
| `materials/csr_demo.html`, `.docx` | `csr_demo.qmd` after rendering |
| `NTS_School_2026_materials.zip` | All of the above in one download |

**Track B without installing R:** create a free account at [posit.cloud](https://posit.cloud),
start an RStudio project, upload `csr_demo.qmd` and `maze.csv`, open the `.qmd` and click **Render**.

## Folder layout

```
NTS_School_2026/
├── index.html                      landing page (GitHub Pages)
├── NTS_School_2026_materials.zip   student materials in one file
├── materials/                      Word template, example, Quarto demo, data
└── slides/
    ├── csr_slides.html             rendered slides (open this)
    ├── csr_slides_files/           slide libraries (required)
    ├── img/, maze.csv              images and data used by the slides
    ├── csr_slides.qmd              slide source
    ├── csr-theme.scss, timer.html  theme and countdown timer
    └── _extensions/r-wasm/live/    quarto-live extension (needed to re-render)
```

## Re-rendering the slides

```bash
cd NTS_School_2026/slides
quarto render csr_slides.qmd      # needs Quarto ≥ 1.4 and R with knitr
```

## Citation

Salgado Ramos MC, da Câmara AO, Freitas HR. From pipettes to p-values: a framework for companion
statistical reporting in experimental neuroscience. *Standards* 2026;6(2):13.
https://doi.org/10.3390/standards6020013
