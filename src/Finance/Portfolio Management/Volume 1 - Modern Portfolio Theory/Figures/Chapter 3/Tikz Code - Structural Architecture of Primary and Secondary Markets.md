---
dg-publish: true
---
```tikz
% ==============================================================================
% The Quant's Bible: Modern Portfolio Management
% Figure: Structural Topology of Primary and Secondary Financial Markets
% Architectural Theme: Noir Void (#090A0C) with Neon Visual Hierarchy
% ==============================================================================

\begin{tikzpicture}[
    >=Stealth,
    font=\bfseries,
    node distance=1.8cm and 2.2cm,
    % ---------------- Color Definitions ----------------
    noirvoid/.style={fill={rgb,255:red,9;green,10;blue,12}},
    % ---------------- Block Styles ---------------------
    panel primary/.style={
        draw={rgb,255:red,0;green,255;blue,255},
        fill={rgb,255:red,0;green,93;blue,93}!35,
        line width=1.2pt,
        rounded corners=8pt
    },
    panel secondary/.style={
        draw={rgb,255:red,230;green,148;blue,1},
        fill={rgb,255:red,111;green,61;blue,0}!35,
        line width=1.2pt,
        rounded corners=8pt
    },
    entity primary/.style={
        draw={rgb,255:red,0;green,255;blue,255},
        fill={rgb,255:red,0;green,93;blue,93},
        text={rgb,255:red,255;green,255;blue,255},
        line width=1.2pt,
        rounded corners=5pt,
        inner sep=8pt,
        minimum width=3.4cm,
        minimum height=1.2cm,
        align=center
    },
    entity secondary/.style={
        draw={rgb,255:red,230;green,148;blue,1},
        fill={rgb,255:red,111;green,61;blue,0},
        text={rgb,255:red,255;green,255;blue,255},
        line width=1.2pt,
        rounded corners=5pt,
        inner sep=8pt,
        minimum width=3.4cm,
        minimum height=1.2cm,
        align=center
    },
    header primary/.style={
        draw={rgb,255:red,0;green,255;blue,255},
        fill={rgb,255:red,0;green,93;blue,93}!80,
        text={rgb,255:red,0;green,255;blue,255},
        line width=1pt,
        rounded corners=4pt,
        inner sep=4pt
    },
    header secondary/.style={
        draw={rgb,255:red,230;green,148;blue,1},
        fill={rgb,255:red,111;green,61;blue,0}!80,
        text={rgb,255:red,230;green,148;blue,1},
        line width=1pt,
        rounded corners=4pt,
        inner sep=4pt
    }
]

    % 1. Canvas Boundary & Noir Void Background (1024x768 approx. aspect ratio)
    \fill[noirvoid] (-7.6, -5.4) rectangle (7.6, 5.4);

    % 2. Master Title Block
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\large] 
        at (0, 4.8) {Figure: Structural Architecture of Primary and Secondary Markets};

    % --------------------------------------------------------------------------
    % PRIMARY MARKET PANEL (Capital Formation)
    % --------------------------------------------------------------------------
    \draw[panel primary] (-7.0, 0.8) rectangle (7.0, 4.2);
    
    \node[header primary, font=\bfseries\small] 
        at (0, 3.85) {PRIMARY MARKET: CAPITAL FORMATION};

    \node[entity primary] (issuer) at (-4.62, 2.3) {
        \textbf{Issuer}\\
        \footnotesize (Corporation / Sovereign)
    };

    \node[entity primary] (investors_p) at (4.4, 2.3) {
        \textbf{Investors}\\
        \footnotesize (Underwriters / Allocators)
    };

    % Capital Flow and Claims Issuance
    \draw[->, >=Stealth, line width=1.8pt, {rgb,255:red,0;green,255;blue,255}] 
        ([yshift=4pt]issuer.east) -- ([yshift=4pt]investors_p.west)
        node[above=19pt, font=\bfseries\footnotesize, text={rgb,255:red,0;green,255;blue,255}, pos=0.5] 
        {Issuance of Newly-Created Financial Claims};

    \draw[<-, >=Stealth, line width=1.8pt, {rgb,255:red,52;green,211;blue,153}] 
        ([yshift=-6pt]issuer.east) -- ([yshift=-6pt]investors_p.west)
        node[below=22pt, font=\bfseries\footnotesize, text={rgb,255:red,52;green,211;blue,153}, pos=0.5] 
        {[Direct Infusion of Net Capital Proceeds]};
% --------------------------------------------------------------------------
    % INTER-MARKET RECURSIVE FEEDBACK CHANNELS
    % --------------------------------------------------------------------------
    % Downward Flow: Pricing Anchors & Signal Feedback
    \draw[->, >=Stealth, line width=2pt, draw={rgb,255:red,230;green,148;blue,1}, color={rgb,255:red,230;green,148;blue,1}] 
        (-0.8, 0.8) -- (-0.8, -1.0)
        node[midway, left=4pt, font=\bfseries\scriptsize, text={rgb,255:red,230;green,148;blue,1}, align=right] 
        {Price Signal Feedback\\(Secondary Yield Guides Primary Cost of Capital)};

    % Upward Flow: Seasoned Liquidity Pipeline
    \draw[->, >=Stealth, line width=1.5pt, dashed, draw={rgb,255:red,211;green,211;blue,211}, color={rgb,255:red,211;green,211;blue,211}] 
        (0.8, -1.0) -- (0.8, 0.8)
        node[midway, right=4pt, font=\bfseries\scriptsize, text={rgb,255:red,211;green,211;blue,211}, align=left] 
        {Seasoned Securities Conduit\\(Underwritten Assets Enter Secondary Circulation)};

    % --------------------------------------------------------------------------
    % SECONDARY MARKET PANEL (Liquidity & Price Discovery)
    % --------------------------------------------------------------------------
    \draw[panel secondary] (-7.0, -4.6) rectangle (7.0, -1.0);
    
    \node[header secondary, font=\bfseries\small] 
        at (0, -1.35) {SECONDARY MARKET: LIQUIDITY \& PRICE DISCOVERY};

    \node[entity secondary] (investor_a) at (-4.4, -2.85) {
        \textbf{Investor A}\\
        \footnotesize (Seller / Capital Demander)
    };

    \node[entity secondary] (investor_b) at (4.4, -2.85) {
        \textbf{Investor B}\\
        \footnotesize (Buyer / Capital Supplier)
    };

    % Secondary Market Mutual Exchange
    \draw[<->, >=Stealth, line width=2pt, {rgb,255:red,230;green,148;blue,1}] 
        (investor_a.east) -- (investor_b.west)
        node[above=15pt, font=\bfseries\footnotesize, text={rgb,255:red,255;green,255;blue,255}, pos=0.44621] 
        {Continuous Double Auction / Central Limit Order Book}
        node[below=19pt, font=\bfseries\footnotesize, text={rgb,255:red,230;green,148;blue,1}, pos=0.449374] 
        {[Exchange of Existing Ownership \& Risk Transfer]};

    % Terminal Microstructure Subtext
    \node[text={rgb,255:red,211;green,211;blue,211}, font=\bfseries\scriptsize] 
        at (0, -4.39) {Underlying Issuer Receives Exactly Zero Capital Inflow From Secondary Trades};

\end{tikzpicture}
```