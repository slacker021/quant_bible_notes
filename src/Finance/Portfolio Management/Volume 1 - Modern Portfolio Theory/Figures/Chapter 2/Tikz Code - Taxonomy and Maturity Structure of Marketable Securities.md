---
dg-publish: true
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
    \fill[noirvoid] (-8.8, -4.2) rectangle (8.8, 4.4);

    % Figure Title
    \node[text=axeswhite, font=\bfseries\Large] at (0, 3.7) {Figure: Taxonomy and Maturity Structure of Marketable Securities};

    % Root Node: Marketable Securities
    \node (root) at (0, 2.5) [
        rectangle,
        draw=rootborder,
        fill=rootfill,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=8pt,
        text=axeswhite,
        font=\bfseries\large,
        align=center
    ] {Marketable Securities};

    % Level 1 Nodes: Primary Tenor Classification
    \node (money) at (-4.2, 0.85) [
        rectangle,
        draw=lightgrey,
        fill=rootfill,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=7pt,
        text=axeswhite,
        align=center,
        text width=4.4cm
    ] {
        \large Money Market\\[1.5mm]
        \footnotesize (Maturity $\le$ 1 Year)
    };

    \node (capital) at (4.2, 0.85) [
        rectangle,
        draw=lightgrey,
        fill=rootfill,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=7pt,
        text=axeswhite,
        align=center,
        text width=4.4cm
    ] {
        \large Capital Market\\[1.5mm]
        \footnotesize (Maturity > 1 Year)
    };

    % Level 2 Nodes: Category Sub-Classes
    % Money Market Sub-Classes
    \node (tbills) at (-6.3, -1.25) [
        rectangle,
        draw=neoncyan,
        fill=darkcyan,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=6pt,
        text=neoncyan,
        align=center,
        text width=3.3cm
    ] {
        \normalsize Treasury Bills
    };

    \node (cp) at (-2.1, -1.25) [
        rectangle,
        draw=neonorange,
        fill=darkorange,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=6pt,
        text=neonorange,
        align=center,
        text width=3.3cm
    ] {
        \normalsize Commercial Paper
    };

    % Capital Market Sub-Classes
    \node (fixedinc) at (2.1, -1.25) [
        rectangle,
        draw=neongreen,
        fill=darkgreen,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=6pt,
        text=neongreen,
        align=center,
        text width=3.3cm
    ] {
        \normalsize Fixed Income
    };

    \node (equity) at (6.3, -1.25) [
        rectangle,
        draw=neonred,
        fill=darkred,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=6pt,
        text=neonred,
        align=center,
        text width=3.3cm
    ] {
        \normalsize Equity Securities
    };

    % Level 3 Nodes: Underlying Specific Instruments
    \node (repos) at (-6.3, -2.95) [
        rectangle,
        draw=neoncyan!70!white,
        fill=darkcyan!60!black,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=6pt,
        text=neoncyan,
        align=center,
        text width=3.3cm
    ] {
        \small CDs / Repos
    };

    \node (ba) at (-2.1, -2.95) [
        rectangle,
        draw=neonorange!70!white,
        fill=darkorange!60!black,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=6pt,
        text=neonorange,
        align=center,
        text width=3.3cm
    ] {
        \small Bankers' Acceptances
    };

    \node (bonds) at (2.1, -2.95) [
        rectangle,
        draw=neongreen!70!white,
        fill=darkgreen!60!black,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=6pt,
        text=neongreen,
        align=center,
        text width=3.3cm
    ] {
        \small Treasury / Corporate /\\Municipals
    };

    \node (stock) at (6.3, -2.95) [
        rectangle,
        draw=neonred!70!white,
        fill=darkred!60!black,
        line width=1.2pt,
        rounded corners=4pt,
        inner sep=6pt,
        text=neonred,
        align=center,
        text width=3.3cm
    ] {
        \small Common / Preferred\\Stock
    };

    % Primary Distribution Bus (Root to Level 1)
    \draw[axeswhite, line width=1.2pt] (root.south) -- (0, 1.85);
    \draw[axeswhite, line width=1.2pt] (-4.2, 1.85) -- (4.2, 1.85);
    \draw[axeswhite, line width=1.2pt] (-4.2, 1.85) -- (money.north);
    \draw[axeswhite, line width=1.2pt] (4.2, 1.85)  -- (capital.north);

    % Level 1 Junction Markers
    \fill[axeswhite] (0, 1.85)    circle (2pt);
    \fill[axeswhite] (-4.2, 1.85) circle (2pt);
    \fill[axeswhite] (4.2, 1.85)  circle (2pt);

    % Secondary Distribution Bus: Money Market (Level 1 to Level 2)
    \draw[axeswhite, line width=1.2pt] (money.south) -- (-4.2, -0.35);
    \draw[axeswhite, line width=1.2pt] (-6.3, -0.35) -- (-2.1, -0.35);
    \draw[axeswhite, line width=1.2pt] (-6.3, -0.35) -- (tbills.north);
    \draw[axeswhite, line width=1.2pt] (-2.1, -0.35) -- (cp.north);

    % Money Market Sub-bus Junction Markers
    \fill[axeswhite] (-4.2, -0.35) circle (2pt);
    \fill[axeswhite] (-6.3, -0.35) circle (2pt);
    \fill[axeswhite] (-2.1, -0.35) circle (2pt);

    % Secondary Distribution Bus: Capital Market (Level 1 to Level 2)
    \draw[axeswhite, line width=1.2pt] (capital.south) -- (4.2, -0.35);
    \draw[axeswhite, line width=1.2pt] (2.1, -0.35)    -- (6.3, -0.35);
    \draw[axeswhite, line width=1.2pt] (2.1, -0.35)    -- (fixedinc.north);
    \draw[axeswhite, line width=1.2pt] (6.3, -0.35)    -- (equity.north);

    % Capital Market Sub-bus Junction Markers
    \fill[axeswhite] (4.2, -0.35) circle (2pt);
    \fill[axeswhite] (2.1, -0.35) circle (2pt);
    \fill[axeswhite] (6.3, -0.35) circle (2pt);

    % Level 2 to Level 3 Vertical Ties
    \draw[axeswhite, line width=1.2pt] (tbills.south)   -- (repos.north);
    \draw[axeswhite, line width=1.2pt] (cp.south)       -- (ba.north);
    \draw[axeswhite, line width=1.2pt] (fixedinc.south) -- (bonds.north);
    \draw[axeswhite, line width=1.2pt] (equity.south)   -- (stock.north);

\end{tikzpicture}
\end{document}
```