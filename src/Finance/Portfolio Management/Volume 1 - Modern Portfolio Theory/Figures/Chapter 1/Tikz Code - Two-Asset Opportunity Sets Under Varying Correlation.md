---
dg-publish: true
---
```tikz
\begin{tikzpicture}[
    x=1.35cm, y=1.20cm,
    font=\small,
    >={Stealth[length=2.5mm, width=1.8mm]}
]
    % --- Noir Void Canvas Palette ---
    \definecolor{noirvoid}{HTML}{090A0C}
    \definecolor{bordergrid}{HTML}{1E293B}
    \definecolor{mutedslate}{HTML}{64748B}
    \definecolor{lightgrey}{HTML}{D3D3D3}
    \definecolor{funcCyan}{HTML}{00FFFF}
    \definecolor{funcOrange}{HTML}{E69401}
    \definecolor{funcGreen}{HTML}{34D399}
    \definecolor{pointRose}{HTML}{FF073A}

    % Background Fill
    \fill[noirvoid] (-1.4, -1.1) rectangle (9.2, 7.8);

    % --- Center-Top Title ---
    \node[text=white, font=\large\bfseries, align=center] at (3.9, 7.35) 
        {Figure: Two-Asset Opportunity Sets Under Varying Correlation ($\rho$)};

    % --- Structural Calibration Grid ---
    \draw[bordergrid, line width=0.4pt, step=1cm] (0, 0) grid (8.2, 6.4);

    % --- Coordinate Parameterization ---
    % Asset 2: (sigma_2 = 3.50, mu_2 = 2.40)
    % Asset 1: (sigma_1 = 6.80, mu_1 = 5.80)
    % Rho = -1 Zero-Risk Point: w* = 3.5 / (6.8 + 3.5) = 0.3398 -> (sigma = 0, mu* = 3.555)
    % Rho = 0 MVP: w_mvp = 3.5^2 / (6.8^2 + 3.5^2) = 12.25 / 58.49 = 0.2094
    %              sigma_mvp = 3.109, mu_mvp = 3.112
    \coordinate (Origin) at (0, 0);
    \coordinate (A2) at (3.50, 2.40);
    \coordinate (A1) at (6.80, 5.80);
    \coordinate (ZeroRisk) at (0, 3.555);
    \coordinate (MVP0) at (3.109, 3.112);

    % --- Projection & Auxiliary Lines ---
    \draw[draw=lightgrey, line width=0.6pt, dashed] (0, 2.40) -| (3.50, 0);
    \draw[draw=lightgrey, line width=0.6pt, dashed] (0, 5.80) -| (6.80, 0);
    \draw[draw=lightgrey, line width=0.6pt, dashed] (0, 3.112) -- (MVP0);
    \draw[draw=lightgrey, line width=0.6pt, dashed] (MVP0) -- (3.109, 0);

    % --- Coordinate Axes ---
    \draw[->, line width=1.1pt, draw=white] (0, 0) -- (8.5, 0) 
        node[right, text=white, font=\bfseries, pos=1.007549] {$\sigma$ (Volatility)};
    \draw[->, line width=1.1pt, draw=white] (0, 0) -- (0, 6.6) 
        node[above, text=white, font=\bfseries, pos=1.002917] {$\mu$ (Return)};

    % Axis Ticks & Notation
    \node[text=mutedslate, below left=1.5mm] at (Origin) {$0$};
    
    \draw[line width=1pt, draw=white] (3.50, -0.1) -- (3.50, 0.1) 
        node[below=3mm, text=white, font=\bfseries] {$\sigma_2$};
    \draw[line width=1pt, draw=white] (6.80, -0.1) -- (6.80, 0.1) 
        node[below=3mm, text=white, font=\bfseries] {$\sigma_1$};
    \draw[line width=1pt, draw=white] (3.109, -0.08) -- (3.109, 0.08) 
        node[below=3mm, text=funcOrange, font=\bfseries\footnotesize] {$\sigma_{\text{mvp}}$};

    \draw[line width=1pt, draw=white] (-0.1, 2.40) -- (0.1, 2.40) 
        node[left=3mm, text=white, font=\bfseries] {$\mu_2$};
    \draw[line width=1pt, draw=white] (-0.1, 5.80) -- (0.1, 5.80) 
        node[left=3mm, text=white, font=\bfseries] {$\mu_1$};
    \draw[line width=1pt, draw=white] (-0.1, 3.555) -- (0.1, 3.555) 
        node[left=3mm, text=funcGreen, font=\bfseries\footnotesize] {$\mu^*$};

    % =========================================================================
    % 1. Curve: rho = +1 (Linear Degenerate Segment)
    % =========================================================================
    \draw[draw=funcCyan, line width=1.6pt] (A2) -- (A1);
    \node[text=funcCyan, font=\bfseries\footnotesize, rotate=41, anchor=south] 
        at (5.15, 4.04) {$\rho = +1$ (Linear Ray)};

    % =========================================================================
    % 2. Curve: rho = 0 (Convex Hyperbolic Arc)
    % Parameter: w in [0, 1]
    % sigma(w) = sqrt(w^2 * 6.8^2 + (1-w)^2 * 3.5^2)
    % mu(w)    = w * 5.8 + (1-w) * 2.4 = 2.4 + 3.4 * w
    % =========================================================================
    \draw[draw=funcOrange, line width=1.8pt, smooth]
        plot[variable=\w, domain=0:1, samples=60]
        ({sqrt(\w*\w*46.24 + (1-\w)*(1-\w)*12.25)}, {2.40 + 3.40*\w});
    
    \node[text=funcOrange, font=\bfseries\footnotesize, right] at (4.7, 3.65) 
        {$\rho = 0$ (Convex Arc)};

    % =========================================================================
    % 3. Curve: rho = -1 (Piecewise Linear Boundary Touching sigma = 0)
    % =========================================================================
    \draw[draw=funcGreen, line width=1.8pt] (A2) -- (ZeroRisk);
    \draw[draw=funcGreen, line width=1.8pt] (ZeroRisk) -- (A1);

    \node[text=funcGreen, font=\bfseries\footnotesize, rotate=-16, anchor=north] 
        at (1.58, 2.92) {$\rho = -1$};
    \node[text=funcGreen, font=\bfseries\footnotesize, rotate=18, anchor=south] 
        at (2.21, 3.87) {$\rho = -1$};

    % =========================================================================
    % Key Nodes & Annotations
    % =========================================================================
    % Asset 2 Node
    \filldraw[fill=white, draw=noirvoid, line width=1pt] (A2) circle (3pt);
    \node[right=2mm, text=white, font=\bfseries] at (A2) {Asset 2 $(\sigma_2, \mu_2)$};

    % Asset 1 Node
    \filldraw[fill=white, draw=noirvoid, line width=1pt] (A1) circle (3pt);
    \node[above left=1mm, text=white, font=\bfseries] at (A1) {Asset 1 $(\sigma_1, \mu_1)$};

    % Minimum Variance Portfolio (MVP) for rho = 0
    \filldraw[fill=funcOrange, draw=white, line width=1pt] (MVP0) circle (3pt);
    \draw[->, line width=0.8pt, draw=funcOrange] (2.1, 2.3) -- (MVP0);
    \node[below left=-1mm, text=funcOrange, font=\bfseries\footnotesize, align=right] 
        at (2.1, 2.3) {Minimum Variance\\Portfolio (MVP)};

    % Zero-Variance Portfolio (rho = -1)
    \filldraw[fill=funcGreen, draw=white, line width=1pt] (ZeroRisk) circle (3pt);
    \draw[->, line width=0.8pt, draw=funcGreen] (0.35, 4.92) -- (0.15, 3.74);
    \node[right=1mm, text=funcGreen, font=\bfseries\footnotesize, align=left] at (0.44, 4.83) 
        {Risk-Free Hedge Point\\$(\sigma = 0, \mu^*)$};

\end{tikzpicture}
```