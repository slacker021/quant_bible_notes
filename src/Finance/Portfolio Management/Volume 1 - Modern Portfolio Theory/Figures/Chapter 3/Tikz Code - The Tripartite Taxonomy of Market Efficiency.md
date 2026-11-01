---
dg-publish: true
---
```tikz
% ==============================================================================
% The Quant's Bible: Modern Portfolio Management
% Figure: The Tripartite Taxonomy of Market Efficiency
% Architectural Theme: Noir Void (#090A0C) with Neon Visual Hierarchy
% ==============================================================================

\begin{tikzpicture}[
    >=Stealth,
    font=\bfseries,
    % ---------------- Color Definitions ----------------
    noirvoid/.style={fill={rgb,255:red,9;green,10;blue,12}},
    % ---------------- Hierarchy Node Styles ------------
    root node/.style={
        draw={rgb,255:red,175;green,105;blue,238},
        fill={rgb,255:red,52;green,21;blue,57}!80,
        text={rgb,255:red,255;green,255;blue,255},
        line width=1.5pt,
        rounded corners=6pt,
        inner sep=10pt,
        minimum width=7.2cm,
        minimum height=1.5cm,
        align=center
    },
    allocative node/.style={
        draw={rgb,255:red,0;green,255;blue,255},
        fill={rgb,255:red,0;green,93;blue,93}!45,
        text={rgb,255:red,255;green,255;blue,255},
        line width=1.3pt,
        rounded corners=6pt,
        inner sep=8pt,
        minimum width=4.6cm,
        minimum height=3.0cm,
        align=center
    },
    productive node/.style={
        draw={rgb,255:red,230;green,148;blue,1},
        fill={rgb,255:red,111;green,61;blue,0}!45,
        text={rgb,255:red,255;green,255;blue,255},
        line width=1.3pt,
        rounded corners=6pt,
        inner sep=8pt,
        minimum width=4.6cm,
        minimum height=3.0cm,
        align=center
    },
    informational node/.style={
        draw={rgb,255:red,52;green,211;blue,153},
        fill={rgb,255:red,4;green,43;blue,29}!45,
        text={rgb,255:red,255;green,255;blue,255},
        line width=1.3pt,
        rounded corners=6pt,
        inner sep=8pt,
        minimum width=4.6cm,
        minimum height=3.0cm,
        align=center
    },
    synthesis panel/.style={
        draw={rgb,255:red,211;green,211;blue,211},
        fill={rgb,255:red,20;green,24;blue,30}!85,
        line width=1pt,
        rounded corners=5pt,
        inner sep=6pt,
        minimum width=14.4cm,
        align=center
    }
]

    % 1. Canvas Boundary & Noir Void Background
    \fill[noirvoid] (-7.7, -5.4) rectangle (7.5, 5.4);

    % 2. Master Title Block
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\Large] 
        at (0, 4.8) {Figure: The Tripartite Taxonomy of Market Efficiency};

    % --------------------------------------------------------------------------
    % ROOT APEX NODE: MARKET EFFICIENCY
    % --------------------------------------------------------------------------
    \node[root node] (root) at (0, 3.2) {
        {\Large \textbf{MARKET EFFICIENCY}}\\[2mm]
        \footnotesize \textnormal{\textcolor{white}{Aggregate Economic Welfare, Information Aggregation \& Frictionless Clearance}}
    };

    % --------------------------------------------------------------------------
    % STRUCTURAL TAXONOMY PILLARS (LEVEL 1)
    % --------------------------------------------------------------------------
    % Left Pillar: Allocative Efficiency
    \node[allocative node] (allocative) at (-6.12, -0.6) {
        {\normalsize \textcolor[rgb]{0.0, 1.0, 1.0}{\textbf{Allocative Efficiency}}}\\[2mm]
        {\small \textbf{[Pareto Optimal Capital Flow]}}\\[3mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Optimal distribution of scarce capital}}\\[1mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Directs primary funds to productive uses}}\\[1mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Equilibrates state-contingent returns}}
    };

    % Central Pillar: Productive (Operational) Efficiency
    \node[productive node] (productive) at (0, -0.6) {
        {\normalsize \textcolor[rgb]{0.902, 0.580, 0.004}{\textbf{Productive Efficiency}}}\\[2mm]
        {\small \textbf{[Minimal Friction Costs]}}\\[3mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Transaction cost minimization}}\\[1mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Tight bid-ask spreads \& liquidity}}\\[1mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Lowers execution \& search drag}}
    };

    % Right Pillar: Informational Efficiency
    \node[informational node] (informational) at (5.77, -0.6) {
        {\normalsize \textcolor[rgb]{0.204, 0.827, 0.600}{\textbf{Informational Efficiency}}}\\[2mm]
        {\small \textbf{[Martingale \& EMH Dynamics]}}\\[3mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Immediate price adaptation to news}}\\[1mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Filtration $\mathcal{F}_t$ reflected in spot prices}}\\[1mm]
        \scriptsize \textnormal{\textcolor{white}{$\bullet$ Absence of systematic excess alpha}}
    };

    % --------------------------------------------------------------------------
    % HIERARCHICAL VECTOR CONDUITS (Explicit RGB Assignment to Prevent Black Paths)
    % --------------------------------------------------------------------------
    % Central Stem
    \draw[-, line width=2pt, draw={rgb,255:red,175;green,105;blue,238}, color={rgb,255:red,175;green,105;blue,238}] 
        (root.south) -- (0, 1.7);

    % Horizontal Distribution Bus
    \draw[-, line width=2pt, draw={rgb,255:red,175;green,105;blue,238}, color={rgb,255:red,175;green,105;blue,238}] 
        (-6.12, 1.69) -- (5.77, 1.71);

    % Branch to Allocative Efficiency
    \draw[->, >=Stealth, line width=2pt, draw={rgb,255:red,0;green,255;blue,255}, color={rgb,255:red,0;green,255;blue,255}] 
        (-6.12, 1.68) -- (allocative.north);

    % Branch to Productive Efficiency
    \draw[->, >=Stealth, line width=2pt, draw={rgb,255:red,230;green,148;blue,1}, color={rgb,255:red,230;green,148;blue,1}] 
        (0, 1.7) -- (productive.north);

    % Branch to Informational Efficiency
    \draw[->, >=Stealth, line width=2pt, draw={rgb,255:red,52;green,211;blue,153}, color={rgb,255:red,52;green,211;blue,153}] 
        (5.77, 1.75) -- (informational.north);



    % --------------------------------------------------------------------------
    % THEORETICAL SYNTHESIS FOOTER
    % --------------------------------------------------------------------------
    \node[synthesis panel] (footer) at (0, -3.9) {
        \footnotesize \textcolor{white}{\textbf{Microeconomic Invariant:}} \ 
        \scriptsize \textnormal{\textcolor{white}{Allocative efficiency is fundamentally contingent upon productive efficiency (low execution friction)}}\\
        \scriptsize \textnormal{\textcolor{white}{and informational efficiency (accurate secondary market price discovery to eliminate the misdirection of capital).}}
    };

\end{tikzpicture}
```