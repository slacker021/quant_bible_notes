---
dg-publish: true
---
```tikz
% ==============================================================================
% The Quant's Bible: Modern Portfolio Management
% Figure: Central Limit Order Book (CLOB) Structure, Depth, and Price Levels
% Architectural Theme: Noir Void (#090A0C) with Neon Visual Hierarchy
% ==============================================================================

\begin{tikzpicture}[
    >=Stealth,
    font=\bfseries,
    % ---------------- Canvas Configuration ----------------
    noirvoid/.style={fill={rgb,255:red,9;green,10;blue,12}},
    % ---------------- Ask Side Blocks (Sell Book) ---------
    ask level/.style={
        draw={rgb,255:red,255;green,7;blue,58},
        fill={rgb,255:red,99;green,4;blue,4}!45,
        line width=1pt,
        rounded corners=4pt
    },
    ask best/.style={
        draw={rgb,255:red,255;green,7;blue,58},
        fill={rgb,255:red,99;green,4;blue,4}!85,
        line width=1.5pt,
        rounded corners=4pt
    },
    ask bar/.style={
        fill={rgb,255:red,255;green,7;blue,58}!40,
        rounded corners=2pt
    },
    % ---------------- Bid Side Blocks (Buy Book) ----------
    bid level/.style={
        draw={rgb,255:red,52;green,211;blue,153},
        fill={rgb,255:red,4;green,43;blue,29}!45,
        line width=1pt,
        rounded corners=4pt
    },
    bid best/.style={
        draw={rgb,255:red,52;green,211;blue,153},
        fill={rgb,255:red,4;green,43;blue,29}!85,
        line width=1.5pt,
        rounded corners=4pt
    },
    bid bar/.style={
        fill={rgb,255:red,52;green,211;blue,153}!40,
        rounded corners=2pt
    },
    % ---------------- Spread & Corridor Blocks -----------
    spread corridor/.style={
        draw={rgb,255:red,230;green,148;blue,1},
        fill={rgb,255:red,111;green,61;blue,0}!30,
        line width=1.2pt,
        rounded corners=6pt
    },
    summary panel/.style={
        draw={rgb,255:red,0;green,255;blue,255},
        fill={rgb,255:red,0;green,93;blue,93}!25,
        line width=1pt,
        rounded corners=5pt
    }
]

    % 1. Canvas Boundary & Noir Void Background
    \fill[noirvoid] (-7.6, -5.4) rectangle (7.6, 5.4);

    % 2. Master Title Block
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\Large] 
        at (0, 4.85) {Figure: Limit Order Book Structure (LOB) Example};

    % 3. Column Header Roster
    \node[text={rgb,255:red,211;green,211;blue,211}, font=\bfseries\scriptsize, align=center] 
        at (-5.16, 4.15) {ROSTER / CLASSIFICATION};
    \node[text={rgb,255:red,211;green,211;blue,211}, font=\bfseries\scriptsize, align=center] 
        at (-0.53, 4.15) {QUEUE DEPTH (LIQUIDITY)};
    \node[text={rgb,255:red,211;green,211;blue,211}, font=\bfseries\scriptsize, align=center] 
        at (3.6, 4.15) {LIMIT PRICE LEVEL};

    % --------------------------------------------------------------------------
    % ASK SIDE: SELL LIQUIDITY (Ascending Price Levels)
    % --------------------------------------------------------------------------
    % Ask Level 3: 3,000 shares @ $100.03
    \draw[ask level] (-7.0, 3.25) rectangle (7.0, 3.85);
    \fill[ask bar] (-2.2, 3.35) rectangle (-2.2 + 2.0, 3.75); % Proportional depth bar
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-6.7, 3.55) {Ask Level 3};
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-2.0, 3.55) {3,000 shares};
    \node[text={rgb,255:red,255;green,7;blue,58}, font=\bfseries\small, anchor=west] 
        at (2.6, 3.55) { \$100.03};

    % Ask Level 2: 1,500 shares @ $100.02
    \draw[ask level] (-7.0, 2.45) rectangle (7.0, 3.05);
    \fill[ask bar] (-2.2, 2.55) rectangle (-2.2 + 1.0, 2.95); % Proportional depth bar
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-6.7, 2.75) {Ask Level 2};
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-2.0, 2.75) {1,500 shares};
    \node[text={rgb,255:red,255;green,7;blue,58}, font=\bfseries\small, anchor=west] 
        at (2.6, 2.75) { \$100.02};

    % Best Ask: 1,000 shares @ $100.01 (Inside Market)
    \draw[ask best] (-7.0, 1.65) rectangle (7.0, 2.25);
    \fill[ask bar] (-2.2, 1.75) rectangle (-2.2 + 0.67, 2.15); % Proportional depth bar
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-6.7, 1.95) {Best Ask (Inside Offer)};
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-2.0, 1.95) {1,000 shares};
    \node[text={rgb,255:red,255;green,7;blue,58}, font=\bfseries\small, anchor=west] 
        at (2.6, 1.95) { \$100.01};
    \draw[<-, >=Stealth, line width=1.5pt, draw={rgb,255:red,255;green,7;blue,58}, color={rgb,255:red,255;green,7;blue,58}] 
        (4.4, 1.95) -- (5.3, 1.95)
        node[right=2pt, font=\bfseries\footnotesize, text={rgb,255:red,255;green,7;blue,58}] 
        {$P_{\text{ask}}$};

    % --------------------------------------------------------------------------
    % CENTRAL SPREAD CORRIDOR & EQUILIBRIUM MID-PRICE
    % --------------------------------------------------------------------------
    \draw[spread corridor] (-7.0, 0.40) rectangle (7.0, 1.25);
    
    % Mid-Price Benchmark Line

    \node[text={rgb,255:red,230;green,148;blue,1}, font=\bfseries\footnotesize, anchor=west] 
        at (-6.69, 0.87) {Quoted Bid-Ask Spread: $\mathcal{S}_{\text{quoted}} = P_{\text{ask}} - P_{\text{bid}} = $ \$0.02};

    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\footnotesize, anchor=east] 
        at (6.5, 0.825) {Mid-Price: $P_{\text{mid}} = \frac{P_{\text{ask}} + P_{\text{bid}}}{2} = $ \$100.00 };

    % --------------------------------------------------------------------------
    % BID SIDE: BUY LIQUIDITY (Descending Price Levels)
    % --------------------------------------------------------------------------
    % Best Bid: 800 shares @ $99.99 (Inside Market)
    \draw[bid best] (-7.0, -0.60) rectangle (7.0, 0.00);
    \fill[bid bar] (-2.2, -0.50) rectangle (-2.2 + 0.53, -0.10); % Proportional depth bar
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-6.7, -0.30) {Best Bid (Inside Bid)};
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-2.0, -0.30) {800 shares};
    \node[text={rgb,255:red,52;green,211;blue,153}, font=\bfseries\small, anchor=west] 
        at (2.6, -0.30) { \$99.99};
    \draw[<-, >=Stealth, line width=1.5pt, draw={rgb,255:red,52;green,211;blue,153}, color={rgb,255:red,52;green,211;blue,153}] 
        (4.4, -0.30) -- (5.3, -0.30)
        node[right=2pt, font=\bfseries\footnotesize, text={rgb,255:red,52;green,211;blue,153}] 
        {$P_{\text{bid}}$};

    % Bid Level 2: 2,200 shares @ $99.98
    \draw[bid level] (-7.0, -1.40) rectangle (7.0, -0.80);
    \fill[bid bar] (-2.2, -1.30) rectangle (-2.2 + 1.47, -0.90); % Proportional depth bar
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-6.7, -1.10) {Bid Level 2};
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-2.0, -1.10) {2,200 shares};
    \node[text={rgb,255:red,52;green,211;blue,153}, font=\bfseries\small, anchor=west] 
        at (2.6, -1.10) { \$99.98};

    % Bid Level 3: 4,500 shares @ $99.95
    \draw[bid level] (-7.0, -2.20) rectangle (7.0, -1.60);
    \fill[bid bar] (-2.2, -2.10) rectangle (-2.2 + 3.0, -1.70); % Proportional depth bar
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-6.7, -1.90) {Bid Level 3};
    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\small, anchor=west] 
        at (-2.0, -1.90) {4,500 shares};
    \node[text={rgb,255:red,52;green,211;blue,153}, font=\bfseries\small, anchor=west] 
        at (2.6, -1.90) { \$99.95};

    % --------------------------------------------------------------------------
    % MARKET MICROSTRUCTURE DERIVED METRICS PANEL
    % --------------------------------------------------------------------------
    \draw[summary panel] (-7.0, -4.85) rectangle (7.0, -2.60);

    \node[text={rgb,255:red,0;green,255;blue,255}, font=\bfseries\footnotesize, anchor=west] 
        at (-6.6, -2.90) {ORDER BOOK DYNAMICS \& INVARIANTS:};

    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\scriptsize, anchor=west] 
        at (-6.6, -3.35) {$\bullet$ Execution Protocol: Price-Time Priority (FIFO within discrete price queues).};

    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\scriptsize, anchor=west] 
        at (-6.6, -3.80) {$\bullet$ Order Book Imbalance: $\operatorname{OBI} = \frac{V_{\text{bid}} - V_{\text{ask}}}{V_{\text{bid}} + V_{\text{ask}}} = \frac{800 - 1{,}000}{800 + 1{,}000} = -\frac{200}{1{,}800} \approx -0.1111$ (Excess Ask Pressure).};

    \node[text={rgb,255:red,255;green,255;blue,255}, font=\bfseries\scriptsize, anchor=west] 
        at (-6.6, -4.30) {$\bullet$ Volume-Weighted Micro-Price: $P_{\text{micro}} = \frac{V_{\text{bid}}P_{\text{ask}} + V_{\text{ask}}P_{\text{bid}}}{V_{\text{bid}} + V_{\text{ask}}} = $ $\frac{800(100.01) + 1{,}000(99.99)}{1{,}800} \approx 99.9989$.};

\end{tikzpicture}
```