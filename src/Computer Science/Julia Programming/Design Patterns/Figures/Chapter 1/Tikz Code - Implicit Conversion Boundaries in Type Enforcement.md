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
    \definecolor{orchid}{HTML}{AF69EE}
    \definecolor{darkpurple}{HTML}{341539}
    \definecolor{neongrey}{HTML}{D3D3D3}

    % Background canvas
    \fill[noirvoid] (-8.2, -5.6) rectangle (8.2, 3.0);

    % Title
    \node[text=white, font=\bfseries\large] at (0, 2.35) {Figure: Implicit Conversion Boundaries in Type Enforcement};

    % Node style declarations
    \tikzset{
        boundnode/.style={
            rectangle,
            rounded corners=4pt,
            line width=1.2pt,
            inner sep=8pt,
            align=center,
            font=\bfseries
        },
        rootnode/.style={
            boundnode,
            draw=neoncyan,
            fill=darkcyan,
            text=neoncyan
        },
        nodeArray/.style={
            boundnode,
            draw=neonorange,
            fill=darkorange,
            text=neonorange
        },
        nodeField/.style={
            boundnode,
            draw=neongreen,
            fill=darkgreen,
            text=neongreen
        },
        nodeReturn/.style={
            boundnode,
            draw=neonred,
            fill=darkred,
            text=neonred
        },
        nodeVariable/.style={
            boundnode,
            draw=orchid,
            fill=darkpurple,
            text=orchid
        },
        graphline/.style={
            draw=neongrey,
            line width=1.3pt
        },
        grapharrow/.style={
            draw=neongrey,
            line width=1.3pt,
            ->,
            >=stealth
        }
    }

    % Root Node
    \node[rootnode] (Root) at (0, 1.2) {Conversion Boundaries};

    % Level 1 Nodes
    \node[nodeArray] (ArrayNode) at (-5.1, -1.2) {
        1. Array Element\\
        Assignment\\[1.5mm]
        \texttt{A[i] = v}
    };

    \node[nodeField] (FieldNode) at (0, -1.2) {
        2. Struct Field\\
        Assignment\\[1.5mm]
        \texttt{obj.field = v}
    };

    \node[nodeReturn] (ReturnNode) at (5.1, -1.2) {
        3. Declared Return\\
        Type Boundary\\[1.5mm]
        \texttt{f()::T = v}
    };

    % Level 2 Node (Directly subordinate to Struct Field Assignment)
    \node[nodeVariable] (VarNode) at (0, -4.1) {
        4. Typed Global / Local\\
        Assignment\\[1.5mm]
        \texttt{x::T = v}
    };

    % Horizontal distribution bus bar
    \draw[graphline] (Root.south) -- (0, 0.15);
    \draw[graphline] (-5.1, 0.15) -- (5.1, 0.15);

    % Downward arrows from bus bar to Level 1 nodes
    \draw[grapharrow] (-5.1, 0.15) -- (ArrayNode.north);
    \draw[grapharrow] (0, 0.15) -- (FieldNode.north);
    \draw[grapharrow] (5.1, 0.15) -- (ReturnNode.north);

    % Vertical connection from Struct Field to Typed Variable Assignment
    \draw[grapharrow] (FieldNode.south) -- (VarNode.north);

\end{tikzpicture}
```