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
    \fill[noirvoid] (-8.6, -6.6) rectangle (8.6, 2.8);

    % Title
    \node[text=white, font=\bfseries\large] at (0, 2.15) {Figure: Multiple Dispatch Across Engine Matrix and Instrument Taxonomy};

    % Node style declarations
    \tikzset{
        basebox/.style={
            rectangle,
            rounded corners=3pt,
            line width=1.2pt,
            inner sep=6pt,
            align=center,
            font=\bfseries
        },
        rootcall/.style={
            basebox,
            draw=neoncyan,
            fill=darkcyan,
            text=neoncyan,
            font=\bfseries\normalsize
        },
        categoryheader/.style={
            basebox,
            font=\bfseries\normalsize,
            inner sep=6pt
        },
        leafbox/.style={
            basebox,
            font=\bfseries\small,
            inner sep=5pt,
            anchor=west
        },
        busline/.style={
            draw=neongrey,
            line width=1.3pt
        },
        busarrow/.style={
            draw=neongrey,
            line width=1.3pt,
            ->,
            >=stealth
        },
        treeline/.style={
            draw=neongrey,
            line width=1.1pt
        }
    }

    % Top Node: Generic Function Call
    \node[rootcall] (FuncCall) at (0, 1.0) {Function Call: \texttt{cross\_orders(engine, instrument)}};

    % Level 1 Category Headers
    \node[categoryheader, draw=neonorange, fill=darkorange, text=neonorange] (EngineHeader) at (-4.2, -1.0) {Engine Type Matrix};
    \node[categoryheader, draw=neongreen, fill=darkgreen, text=neongreen] (InstHeader) at (4.2, -1.0) {Instrument Taxonomy};

    % Central Distribution Bus Bar
    \draw[busline] (FuncCall.south) -- (0, 0.0);
    \draw[busline] (-4.2, 0.0) -- (4.2, 0.0);
    \draw[busarrow] (-4.2, 0.0) -- (EngineHeader.north);
    \draw[busarrow] (4.2, 0.0) -- (InstHeader.north);

    % Left Subtree: Engine Types
    \node[leafbox, draw=neonorange, fill=darkorange, text=neonorange] (LitBook) at (-4.0, -2.4) {\texttt{LitBookExecution}};
    \node[leafbox, draw=neonorange, fill=darkorange, text=neonorange] (DarkPool) at (-4.0, -3.8) {\texttt{DarkPoolExecution}};

    % Left Tree Branching Lines
    \draw[treeline] (-5.3, -1.45) -- (-5.3, -3.8);
    \draw[treeline] (-5.3, -2.4) -- (LitBook.west);
    \draw[treeline] (-5.3, -3.8) -- (DarkPool.west);

    % Right Subtree: Instrument Types
    \node[leafbox, draw=neongreen, fill=darkgreen, text=neongreen] (SpotEq) at (3.5, -2.4) {\texttt{SpotEquity}};
    \node[leafbox, draw=neongreen, fill=darkgreen, text=neongreen] (EuroOpt) at (3.5, -3.8) {\texttt{EuropeanOption}};
    \node[leafbox, draw=neongreen, fill=darkgreen, text=neongreen] (CDS) at (3.5, -5.2) {\texttt{CreditDefaultSwap}};

    % Right Tree Branching Lines
    \draw[treeline] (2.2, -1.45) -- (2.2, -5.2);
    \draw[treeline] (2.2, -2.4) -- (SpotEq.west);
    \draw[treeline] (2.2, -3.8) -- (EuroOpt.west);
    \draw[treeline] (2.2, -5.2) -- (CDS.west);

\end{tikzpicture}
```