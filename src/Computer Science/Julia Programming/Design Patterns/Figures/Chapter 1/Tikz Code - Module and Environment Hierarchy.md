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
    \fill[noirvoid] (-7.5, -5.5) rectangle (7.5, 2.5);

    % Title
    \node[text=white, font=\bfseries\large] at (0, 1.8) {Figure: Module and Environment Hierarchy};

    % Node style declarations
    \tikzset{
        treenode/.style={
            rectangle,
            rounded corners=4pt,
            line width=1.2pt,
            inner sep=8pt,
            align=center,
            font=\bfseries
        },
        rootnode/.style={
            treenode,
            draw=neoncyan,
            fill=darkcyan,
            text=neoncyan
        },
        modA/.style={
            treenode,
            draw=neonorange,
            fill=darkorange,
            text=neonorange
        },
        modB/.style={
            treenode,
            draw=neongreen,
            fill=darkgreen,
            text=neongreen
        },
        subA1/.style={
            treenode,
            draw=neonred,
            fill=darkred,
            text=neonred
        },
        subA2/.style={
            treenode,
            draw=neoncyan,
            fill=darkcyan,
            text=neoncyan
        },
        treeedge/.style={
            draw=neongrey,
            line width=1.2pt
        }
    }

    % Nodes
    \node[rootnode] (Main) at (0, 0.5) {Main (Root Environment)};

    \node[modA] (ModA) at (-2.8, -1.8) {ModuleA};
    \node[modB] (ModB) at (2.8, -1.8) {ModuleB};

    \node[subA1] (SubA1) at (-4.2, -4.0) {SubA1};
    \node[subA2] (SubA2) at (-1.4, -4.0) {SubA2};

    % Connecting Edges
    \draw[treeedge] (Main.south) -- (ModA.north);
    \draw[treeedge] (Main.south) -- (ModB.north);
    \draw[treeedge] (ModA.south) -- (SubA1.north);
    \draw[treeedge] (ModA.south) -- (SubA2.north);

\end{tikzpicture}
```