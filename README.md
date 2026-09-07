# Resume

CV professionnel LaTeX (mono-page, A4, français) construit autour de deux fichiers :

- `resume.tex` — mise en page, macros et style (à ne pas modifier au quotidien).
- `resume-data.tex` — contenu du CV (identité, expériences, projets, compétences…).

Le PDF final est généré dans `resume.pdf`.

## Prérequis

- TeX Live (ou MiKTeX) avec `pdflatex`
- `latexmk` (recommandé pour la compilation incrémentale et le nettoyage)

Sur Debian / Ubuntu :

```bash
sudo apt install texlive-latex-extra texlive-fonts-extra texlive-lang-french latexmk
```

## Compilation

### Option 1 — `latexmk` (recommandé)

Gère automatiquement les passes multiples (références, table des matières, etc.).

```bash
latexmk -pdf resume.tex
```

### Option 2 — `pdflatex` brut

Deux passes pour stabiliser les références et la mise en page.

```bash
pdflatex -interaction=nonstopmode resume.tex && pdflatex -interaction=nonstopmode resume.tex
```

## Mode watch (recompilation automatique)

Recompile à chaque sauvegarde de `resume.tex` ou `resume-data.tex`.

```bash
latexmk -pdf -pvc resume.tex
```

## Nettoyage

Supprime les fichiers auxiliaires (`.aux`, `.log`, `.out`…) en gardant le PDF.

```bash
latexmk -c
```

Pour tout supprimer, **y compris le PDF** :

```bash
latexmk -C
```

## Structure

```
.
├── resume.tex        # Template LaTeX (macros, styles, mise en page)
├── resume-data.tex   # Contenu du CV (à éditer)
├── resume.pdf        # Sortie compilée
└── README.md
```
# resume
