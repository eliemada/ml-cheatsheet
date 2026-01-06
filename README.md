# ML Cheatsheet Template

A LaTeX template optimized for creating dense, 2-sided A4 cheatsheets for Machine Learning exams.

## Compilation

```bash
xelatex -shell-escape "ml-cheatsheet.tex"
xelatex -shell-escape "ml-cheatsheet.tex"  # Run twice for references
```

## Project Structure

```
.
├── ml-cheatsheet.tex    # Main document
├── parts/
│   ├── lib.tex          # Macros and styling
│   └── content.tex      # Your content goes here
└── latex-img/           # Images folder
```

---

## Available Commands

### Colors

| Command | Description |
|---------|-------------|
| `\blue{text}` | Blue text |
| `\red{text}` | Red text |
| `\orange{text}` | Orange text |
| `\green{text}` | Green text |
| `\gray{text}` | Gray text |

### ML Operators

| Command | Output | Description |
|---------|--------|-------------|
| `\argmax` | arg max | With subscript: `\argmax_\theta` |
| `\argmin` | arg min | With subscript: `\argmin_x` |
| `\sign` | sign | Sign function |
| `\softmax` | softmax | Softmax function |
| `\sigmoid` | σ | Sigmoid function |

### Probability & Statistics

| Command | Output | Example |
|---------|--------|---------|
| `\E` | 𝔼 | `\E[X]` → 𝔼[X] |
| `\Var` | Var | `\Var(X)` |
| `\Cov` | Cov | `\Cov(X,Y)` |
| `\Prob` | ℙ | `\Prob(A)` |

### Vectors & Matrices

| Command | Output | Example |
|---------|--------|---------|
| `\vec{x}` | **x** | Bold vector |
| `\mat{X}` | **X** | Bold matrix |
| `\tp` | ᵀ | Transpose: `\mat{X}\tp` → **X**ᵀ |

### Common Sets

| Command | Output |
|---------|--------|
| `\R` | ℝ |
| `\N` | ℕ |

### ML Symbols

| Command | Output | Usage |
|---------|--------|-------|
| `\Loss` | ℒ | Loss function |
| `\Data` | 𝒟 | Dataset |

### From `physics` Package

| Command | Output | Example |
|---------|--------|---------|
| `\norm{x}` | ‖x‖ | Norm |
| `\abs{x}` | \|x\| | Absolute value |
| `\grad` | ∇ | Gradient |
| `\pdv{f}{x}` | ∂f/∂x | Partial derivative |
| `\dv{f}{x}` | df/dx | Derivative |

---

## Boxed Environments

### Definition Box (blue border)
```latex
\begin{defbox}
\textbf{Gradient Descent:} Update rule for parameters.
\end{defbox}
```

### Important Formula Box (blue background)
```latex
\begin{impbox}
$\vec{w}^* = (\mat{X}\tp\mat{X})^{-1}\mat{X}\tp\vec{y}$
\end{impbox}
```

---

## Example Content

```latex
\section{Linear Regression}

\begin{defbox}
\textbf{OLS:} Minimize $\Loss(\vec{w}) = \norm{\vec{y} - \mat{X}\vec{w}}^2$
\end{defbox}

\textbf{Closed-form solution:}
\begin{impbox}
$\vec{w}^* = (\mat{X}\tp\mat{X})^{-1}\mat{X}\tp\vec{y}$
\end{impbox}

\textbf{Gradient:} $\nabla\Loss = -2\mat{X}\tp(\vec{y} - \mat{X}\vec{w})$

\textbf{Update:} $\vec{w}_{t+1} = \vec{w}_t - \eta \nabla\Loss$

\subsection{Regularization}
\begin{itemize}
    \item Ridge (L2): $\Loss + \lambda\norm{\vec{w}}^2$
    \item Lasso (L1): $\Loss + \lambda\norm{\vec{w}}_1$
\end{itemize}
```

---

## Code Snippets (Python)

```latex
\begin{minted}{python}
import numpy as np
w = np.linalg.inv(X.T @ X) @ X.T @ y
\end{minted}
```

---

## Tips for Dense Cheatsheets

1. **Use `\scriptsize`** (default) or `\tiny` for maximum density
2. **Minimize whitespace:** The template already has tight spacing
3. **Use abbreviations:** Define shortcuts for common terms
4. **Boxed formulas:** Reserve `impbox` for must-know formulas
5. **Color coding:** Use colors sparingly for key terms
6. **Lists:** Use `itemize` with tight spacing (already configured)

## Customization

- **Font size:** Edit `lib.tex` line ~116 (`\scriptsize` → `\tiny`)
- **Columns:** Edit main file (`\begin{multicols*}{5}` → 4 or 6)
- **Colors:** Edit `lib.tex` lines 11-14 (HTML color codes)
