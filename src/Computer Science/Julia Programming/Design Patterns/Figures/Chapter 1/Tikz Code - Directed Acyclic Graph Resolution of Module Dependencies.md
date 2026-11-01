---
dg-publish: true
---
```tikz
\begin{tikzpicture}
    % Color definitions adhering to repository palette
    \definecolor{noirvoid}{HTML}{090A0C}
    \definecolor{neoncyan}{HTML}{00FFFF}
    \definecolor{darkcyan}{HTML}{005D5D}
    \definecolor{neonorange}{HTML}{E69401}
    \definecolor{darkorange}{HTML}{6F3D00}
    \definecolor{neongreen}{HTML}{34D399}
    \definecolor{darkgreen}{HTML}{042B1D}
    \definecolor{neonred}{HTML}{FF073A}
    \definecolor{darkred}{HTML}{630404}
    \definecolor{neongrey}{HTML}{D3D3D3}

    % Background canvas
    \fill[noirvoid] (-8.5, -7.2) rectangle (8.5, 4.4);

    % Main Title
    \node[text=white, font=\bfseries\large] at (0, 3.8) {Figure: Directed Acyclic Graph Resolution of Module Dependencies};

    % Styles
    \tikzset{
        modbox/.style={
            rectangle,
            rounded corners=4pt,
            line width=1.2pt,
            inner sep=8pt,
            align=center,
            font=\bfseries
        },
        abstractbox/.style={
            rectangle,
            rounded corners=2pt,
            line width=1.4pt,
            inner sep=9pt,
            align=center,
            font=\bfseries,
            draw=neoncyan,
            fill=darkcyan,
            text=neoncyan
        },
        errarrow/.style={
            draw=neonred,
            line width=1.3pt,
            ->,
            >=stealth
        },
        graphline/.style={
            draw=neongrey,
            line width=1.3pt
        }
    }

    % -------------------------------------------------------------
    % TOP PANEL: CYCLIC DEPENDENCY (ILLEGAL)
    % -------------------------------------------------------------
    \node[text=neonred, font=\bfseries\normalsize, anchor=west] at (-6.5, 2.7) {Cyclic Dependency (Illegal)};

    \node[modbox, draw=neonorange, fill=darkorange, text=neonorange] (ModA_cyc) at (-3.2, 1.2) {ModuleA};
    \node[modbox, draw=neongreen, fill=darkgreen, text=neongreen] (ModB_cyc) at (3.2, 1.2) {ModuleB};

    % Direct forward dependency: ModuleA -> ModuleB
    \draw[errarrow] (ModA_cyc.east) -- (ModB_cyc.west);

    % Cycle feedback: ModuleB -> ModuleA
    \draw[errarrow] (ModB_cyc.north) -- ++(0, 0.7) -| (ModA_cyc.north);

    % -------------------------------------------------------------
    % BOTTOM PANEL: ACYCLIC RESOLUTION VIA SHARED ABSTRACTION
    % -------------------------------------------------------------
    \node[text=neongreen, font=\bfseries\normalsize, anchor=west] at (-6.5, -0.6) {Acyclic Resolution via Shared Abstraction (Compliant)};

    \node[abstractbox] (Common) at (0, -2.5) {
        Common\\
        Abstract\\
        Types
    };

    \node[modbox, draw=neonorange, fill=darkorange, text=neonorange] (ModA_dag) at (-3.2, -5.5) {ModuleA};
    \node[modbox, draw=neongreen, fill=darkgreen, text=neongreen] (ModB_dag) at (3.2, -5.5) {ModuleB};

    % Routing from dependent modules up to common abstraction junction
    \draw[graphline] (ModA_dag.north) -- (-3.2, -4.3);
    \draw[graphline] (ModB_dag.north) -- (3.2, -4.3);
    \draw[graphline] (-3.2, -4.3) -- (3.2, -4.3);

    % Central vertical stem terminating at abstraction interface
    \draw[graphline] (0, -4.3) -- ([yshift=-0.30cm]Common.south);

    % Upward abstraction triangle pointer
    \fill[neoncyan] (Common.south) -- ++(-0.24, -0.30) -- ++(0.48, 0) -- cycle;

\end{tikzpicture}
```