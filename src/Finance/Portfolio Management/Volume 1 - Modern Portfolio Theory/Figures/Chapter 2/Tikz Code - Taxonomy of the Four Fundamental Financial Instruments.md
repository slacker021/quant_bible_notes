---
dg-publish:
---

```tikz
\documentclass[tikz,border=10pt]{standalone}
\usepackage{tikz}
\usetikzlibrary{positioning,shapes.geometric,arrows.meta}

% Repository Color Palette Definitions
\definecolor{noirvoid}{HTML}{090A0C}
\definecolor{axeswhite}{HTML}{FFFFFF}
\definecolor{lightgrey}{HTML}{D3D3D3}

% Functional Node Palette (Bright Foreground / Dark Background)
\definecolor{neoncyan}{HTML}{00FFFF}
\definecolor{darkcyan}{HTML}{005D5D}

\definecolor{neonorange}{HTML}{E69401}
\definecolor{darkorange}{HTML}{6F3D00}

\definecolor{neongreen}{HTML}{34D399}
\definecolor{darkgreen}{HTML}{042B1D}

\definecolor{neonred}{HTML}{FF073A}
\definecolor{darkred}{HTML}{630404}

\definecolor{rootborder}{HTML}{D3D3D3}
\definecolor{rootfill}{HTML}{161922}

\begin{document}
\begin{tikzpicture}[
    font=\bfseries,
    line cap=round,
    line join=round
]

    % Canvas Background
    \fill[noirvoid] (-8.0, -2.6) rectangle (8.0, 4.6);

    % Figure Title
    \node[text=axeswhite, font=\bfseries\large] at (0, 3.8) {Figure: Taxonomy of the Four Fundamental Financial Instruments};

    % Root Node: Financial Instruments
    \node (root) at (0, 2.3) [
        rectangle,
        draw=rootborder,
        fill=rootfill,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=8pt,
        text=axeswhite,
        font=\bfseries\large,
        align=center
    ] {Financial Instruments};

    % Level 1 Nodes: Four Fundamental Instruments
    \node (cash) at (-5.75, -0.8) [
        rectangle,
        draw=neoncyan,
        fill=darkcyan,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=7pt,
        text=neoncyan,
        align=center,
        text width=85.8110238pt
    ] {
        \large Cash\\[2mm]
        \footnotesize (Spot Liquidity\\\& Numeraire)
    };

    \node (credit) at (-2.05, -0.82) [
        rectangle,
        draw=neonorange,
        fill=darkorange,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=7pt,
        text=neonorange,
        align=center,
        text width=3.2cm
    ] {
        \large Credit\\[2mm]
        \footnotesize (Senior Debt\\\& Fixed Income)
    };

    \node (equity) at (1.8, -0.8) [
        rectangle,
        draw=neongreen,
        fill=darkgreen,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=7pt,
        text=neongreen,
        align=center,
        text width=3.2cm
    ] {
        \large Equity\\[2mm]
        \footnotesize (Subordinated\\Residual Claim)
    };

    \node (derivative) at (5.65, -0.8) [
        rectangle,
        draw=neonred,
        fill=darkred,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=7pt,
        text=neonred,
        align=center,
        text width=3.2cm
    ] {
        \large Derivative\\[2mm]
        \footnotesize (Contingent Claim\\\& Risk Transfer)
    };

    % Orthogonal Distribution Bus
    % Vertical drop from root
    \draw[axeswhite, line width=1.2pt] (root.south) -- (0, 0.9);

    % Horizontal bus line connecting the four trunks
    \draw[axeswhite, line width=1.2pt] (-5.95, 0.9) -- (5.64, 0.9);

    % Vertical drops into child category nodes
    \draw[axeswhite, line width=1.2pt] (-5.75, 0.9) -- (cash.north);
    \draw[axeswhite, line width=1.2pt] (-2.05, 0.9) -- (credit.north);
    \draw[axeswhite, line width=1.2pt] (1.8, 0.9)  -- (equity.north);
    \draw[axeswhite, line width=1.2pt] (5.65, 0.9)  -- (derivative.north);

    % Junction Markers corresponding to the ASCII grid intersections
    \fill[axeswhite] (0, 0.9)    circle (2pt);
    \fill[axeswhite] (-5.75, 0.9) circle (2pt);
    \fill[axeswhite] (-2.05, 0.9) circle (2pt);
    \fill[axeswhite] (1.8, 0.9)  circle (2pt);
    \fill[axeswhite] (5.65, 0.9)  circle (2pt);

\end{tikzpicture}
\end{document}
```