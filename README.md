# Templates

These are some templates for various university(/vocational school) papers, with different structures and varying additional functions. 

##### Setting up LaTeX in VSCode (optional)
- Using LaTeX seperately or using OverLeaf is also possible. 
- for setting LaTeX up in VSCode this [video](https://www.youtube.com/watch?v=4lyHIQl4VM8) was used.
    - for that setup you will need to install:
        1. VSCode
        2. LaTeX Workshop extension in VSCode
        3. MiKTeX
        4. Strawberry PERL (probably need higher privileges to install this on work computer)

### Folder structure (meant for VSCode + git)
- .vscode/settings.json 
    - output will be generated in the "out" subfolder if present
    - pdf viewing will add a tab (usually split code view into two columns with pdf on the right side)
- "out" folder
    - contains all the build files AND the pdf version that is viewed
- .gitignore
    - the LaTeX build files in any "out" folder that is a subfolder will be ignored 
    - the .pdf in the "out" folder will be kept 
- Images folder has to be referenced in image filepaths in LaTeX
    - vector graphics (for best quality) in pdf format can be used, otherwise png files are recommended
- add a settings.json in a .vscode folder

---
settings.json
```
{
    "latex-workshop.latex.outDir": "./out",
    "latex-workshop.synctex.afterBuild.enabled": true,
    "latex-workshop.view.pdf.viewer": "tab",

    "latex-workshop.latex.tools": [
        {
            "name": "latexmk-shell-escape",
            "command": "latexmk",
            "args": [
                "-pdf",
                "-shell-escape",
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-outdir=%OUTDIR%",
                "%DOC%"
            ]
        }
    ],

    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk-shell-escape",
            "tools": [
                "latexmk-shell-escape"
            ]
        }
    ]
}
```
---

### Quellen.bib
- bibtex for the sources 
- can be used with e.g. Zotero, just export the sources as bibtex file

## Tempaltes
- either clone this repository if you don't mind cloning the history
    - or make a robocopy for a clean version

### VorlageArbeiten.tex 
- This one is the basis for all other ones, so it is the most basic and may lack additions made to other templates 
- general structure
- basic and useful LaTeX functions with explanations 
- Harvard "author-year" citation style (agsm) 

### VorlageBachelorArbeit.tex
- different spacing and requirements were given
    - partial use of [Springer conference proceeding guidelines](https://www.springer.com/gp/computer-science/lncs/conference-proceedings-guidelines) (as required by BHH)
- IEEE citation (ieeetr)

### VorlageCapstone.tex 
- general Capstone Project documentation structure
    - example tables for project team organisation and 
- section authors 

### VorlageProjektdoku.tex
- general AP2 Projektdokumentation structure
    - example tables for Timemanagement etc.
- "Arial" LaTeX font, optional (as far as I know the IHK takes regular LaTeX font as well) 