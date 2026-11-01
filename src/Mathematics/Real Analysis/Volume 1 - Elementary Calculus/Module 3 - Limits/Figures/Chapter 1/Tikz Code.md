---
dg-publish: true
---
```tikz
\documentclass[tikz,border=10pt]{standalone}
\usepackage{amsmath,amssymb}
\usepackage{tikz}
\usetikzlibrary{arrows.meta,calc,angles,quotes}

% Define custom color palette per Quant's Bible conventions
\definecolor{noirvoid}{HTML}{090A0C}
\definecolor{neoncyan}{HTML}{00FFFF}
\definecolor{neonorange}{HTML}{E69401}
\definecolor{neonyellow}{HTML}{FFFF00}
\definecolor{axisgray}{HTML}{9CA3AF}
\definecolor{lightgray}{HTML}{D3D3D3}
\definecolor{tealgray}{HTML}{2A4349}
\definecolor{olivegray}{HTML}{4D5A46}

\begin{document}
\begin{tikzpicture}[
    scale=6,
    line cap=round,
    line join=round,
    font=\bfseries\small
]
    % Background canvas
    \fill[noirvoid] (-0.35, -0.42) rectangle (1.45, 1.45);

    % Title
    \node[anchor=north, text=white] at (0.5, 1.38) {\Large\textbf{Figure: Unit Circle}};

    % Geometric parameters
    \def\ang{36.87} % angle x in degrees (3-4-5 right triangle for clean proportions)
    \def\rad{1.0}
    \def\rsq{0.045} % size of right-angle square marker

    % Coordinate definitions
    \coordinate (O) at (0, 0);
    \coordinate (A) at (\rad, 0);
    \coordinate (C) at ({\rad*cos(\ang)}, 0);
    \coordinate (P) at ({\rad*cos(\ang)}, {\rad*sin(\ang)});
    \coordinate (T) at (\rad, {\rad*tan(\ang)});

    % Shaded Region 1: Triangle OCP (Olive-tinted translucent fill)
    \fill[olivegray, fill opacity=0.75] (O) -- (C) -- (P) -- cycle;

    % Shaded Region 2: Area between CP, arc PA, and segment AC (Dark cyan/slate fill)
    \fill[tealgray, fill opacity=0.85] 
        (C) -- (P) 
        arc[start angle=\ang, end angle=0, radius=\rad] 
        -- cycle;

    % Right-angle markers at C and A
    \filldraw[draw=lightgray, fill=lightgray!35, fill opacity=0.4, line width=0.6pt] 
        ($(C) + (-\rsq, 0)$) -- ($(C) + (-\rsq, \rsq)$) -- ($(C) + (0, \rsq)$) -- (C) -- cycle;
    \filldraw[draw=lightgray, fill=lightgray!35, fill opacity=0.4, line width=0.6pt] 
        ($(A) + (-\rsq, 0)$) -- ($(A) + (-\rsq, \rsq)$) -- ($(A) + (0, \rsq)$) -- (A) -- cycle;

    % Unit Circle Arc: from 80 deg down to 0 deg
    \draw[neoncyan, line width=1.8pt] 
        (80:\rad) arc[start angle=80, end angle=0, radius=\rad];

    % Line Segments
    \draw[neonyellow, line width=1.5pt] (O) -- (P); % OP (hypotenuse of OCP)
    \draw[white, line width=1.2pt] (P) -- (T);       % PT (extension to vertical tangent)
    \draw[neoncyan!80!white, line width=1.0pt] (C) -- (P); % CP (sine vertical altitude)
    \draw[neonorange, line width=1.5pt] (A) -- (T); % AT (tangent segment)

    % Coordinate Axes (u and v)
    \draw[axisgray, line width=1.0pt, -{Latex[length=3mm, width=2mm]}] 
        (-0.18, 0) -- (1.35, 0) node[right, text=white] {$u$};
    \draw[axisgray, line width=1.0pt, -{Latex[length=3mm, width=2mm]}] 
        (0, -0.18) -- (0, 1.25) node[above, text=white] {$v$};

    % Angle arc and label x
    \draw[neonyellow, line width=1.0pt, -{Latex[length=2.2mm, width=1.6mm]}] 
        (0.22, 0) arc[start angle=0, end angle=\ang, radius=0.22];
    \node[text=neonyellow] at (18.5:0.29) {$x$};

    % Circle Equation Label
    \node[anchor=south, text=neoncyan] at (0.25, 1.02) {$u^2 + v^2 = 1$};

    % Vertical sin(x) dimension arrow (inside region CA)
    \draw[neoncyan, line width=0.9pt, {Latex[length=2mm, width=1.3mm]}-{Latex[length=2mm, width=1.3mm]}] 
        ($(C) + (0.05, 0)$) -- ($(C) + (0.05, {\rad*sin(\ang)})$);
    \node[anchor=west, text=neoncyan] at ($(C) + (0.06, {0.5*\rad*sin(\ang)})$) {$\sin x$};

    % Vertical tan(x) dimension arrow (right of AT)
    \draw[neonorange, line width=0.9pt, {Latex[length=2mm, width=1.3mm]}-{Latex[length=2mm, width=1.3mm]}] 
        ($(A) + (0.05, 0)$) -- ($(A) + (0.05, {\rad*tan(\ang)})$);
    \node[anchor=west, text=neonorange] at ($(A) + (0.07, {0.5*\rad*tan(\ang)})$) {$\tan x$};

    % Horizontal cos(x) dimension brackets and arrow (below u-axis)
    \draw[axisgray, line width=0.8pt] (0, -0.02) -- (0, -0.14);
    \draw[axisgray, line width=0.8pt] ({cos(\ang)}, -0.02) -- ({cos(\ang)}, -0.14);
    \draw[neonyellow, line width=0.9pt, {Latex[length=2mm, width=1.3mm]}-{Latex[length=2mm, width=1.3mm]}] 
        (0, -0.11) -- ({cos(\ang)}, -0.11);
    \node[anchor=north, text=neonyellow] at ({0.5*cos(\ang)}, -0.12) {$\cos x$};

    % Boundary Points (filled circles)
    \filldraw[fill=white, draw=white] (O) circle (0.015);
    \filldraw[fill=white, draw=white] (C) circle (0.015);
    \filldraw[fill=white, draw=white] (A) circle (0.015);
    \filldraw[fill=neonyellow, draw=neonyellow] (P) circle (0.015);
    \filldraw[fill=neonorange, draw=neonorange] (T) circle (0.015);

    % Point Labels
    \node[anchor=north east, text=white] at ($(O) + (-0.01, -0.02)$) {$O(0, 0)$};
    \node[anchor=north, text=white] at ($(C) + (0, -0.02)$) {$C(\cos x, 0)$};
    \node[anchor=north west, text=white] at ($(A) + (0.01, -0.02)$) {$A(1, 0)$};
    \node[anchor=east, text=neonyellow] at ($(P) + (-0.02, 0.03)$) {$P(\cos x, \sin x)$};
    \node[anchor=south west, text=neonorange] at ($(T) + (0.02, 0.02)$) {$T(1, \tan x)$};

\end{tikzpicture}
\end{document}
```