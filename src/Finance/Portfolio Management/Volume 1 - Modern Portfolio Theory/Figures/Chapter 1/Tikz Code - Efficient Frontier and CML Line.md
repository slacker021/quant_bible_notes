---
dg-publish: true
---
```tikz
\begin{tikzpicture}[
    x=1.35cm, y=1.35cm,
    font=\small,
    >={Stealth[length=2.5mm, width=1.8mm]}
]
    % --- Noir Void Canvas ---
    \definecolor{noirvoid}{HTML}{090A0C}
    \definecolor{accentcyan}{HTML}{38BDF8}
    \definecolor{accentgold}{HTML}{FBBF24}
    \definecolor{accentemerald}{HTML}{34D399}
    \definecolor{mutedslate}{HTML}{64748B}
    \definecolor{bordergrid}{HTML}{1E293B}
    
    \fill[noirvoid] (-1.2, -1.0) rectangle (9.8, 7.8);

    % --- Center-Top Title ---
    \node[text=white, font=\large\bfseries, align=center] at (4.52, 7.41) 
        {Figure:  Efficient Frontier and CML Line};

    % --- Subtle Grid & Calibration ---
    \draw[bordergrid, line width=0.4pt, step=1cm] (0, 0) grid (8.8, 6.2);

    % --- Axes ---
    \draw[->, line width=1.1pt, draw=white] (0, 0) -- (9.0, 0) 
        node[right=2mm, text=white, font=\bfseries] {$\sigma$ (Volatility)};
    \draw[->, line width=1.1pt, draw=white] (0, 0) -- (0, 6.5) 
        node[above=2mm, text=white, font=\bfseries] {$\mu$ (Return)};

    % Origin Tick
    \node[text=mutedslate, below left=1.5mm] at (0, 0) {$0$};

    % --- Coordinate Definitions ---
    % Mathematical hyperbola parameters: sigma(mu) = sqrt(sigma_0^2 + k*(mu - mu_0)^2)
    % GMVP: (sigma_0 = 3.20, mu_0 = 3.00)
    % Tangency Portfolio T: (sigma_T = 4.84, mu_T = 4.80) with R_F = 1.60
    \coordinate (Origin) at (0, 0);
    \coordinate (RF) at (0, 1.6);
    \coordinate (GMVP) at (3.2, 3.0);
    \coordinate (T) at (4.838, 4.8);
    \coordinate (SigmaT) at (4.838, 0);
    \coordinate (MuT) at (0, 4.8);
    \coordinate (CML_End) at (7.8, 6.76);

    % --- Projection / Auxiliary Dashed Lines ---
    \draw[draw=mutedslate, line width=0.8pt, dashed] (0, 4.8) -- (T);
    \draw[draw=mutedslate, line width=0.8pt, dashed] (4.838, 0) -- (T);
    \draw[draw=mutedslate, line width=0.8pt, dashed] (0, 1.6) -- (1.6, 1.6);

    % --- Axis Ticks & Labels ---
    \draw[line width=1pt, draw=white] (-0.1, 1.6) -- (0.1, 1.6) 
        node[left=3mm, text=white, font=\bfseries] {$R_F$};
    \draw[line width=1pt, draw=white] (-0.1, 4.8) -- (0.1, 4.8) 
        node[left=3mm, text=white, font=\bfseries] {$\mu_T$};
    \draw[line width=1pt, draw=white] (4.838, -0.1) -- (4.838, 0.1) 
        node[below=3mm, text=white, font=\bfseries] {$\sigma_T$};

    % --- Inefficient Risky Frontier (Lower Hyperbolic Branch) ---
    \draw[draw=mutedslate, line width=1.1pt, dash pattern=on 3pt off 3pt, smooth]
        plot[variable=\mu, domain=1.2:3.0, samples=60] 
        ({sqrt(10.24 + 4.0635*(\mu - 3.0)^2)}, {\mu});

    % --- Efficient Risky Frontier (Upper Hyperbolic Branch) ---
    \draw[draw=accentcyan, line width=1.8pt, smooth]
        plot[variable=\mu, domain=3.0:6.1, samples=80] 
        ({sqrt(10.24 + 4.0635*(\mu - 3.0)^2)}, {\mu});

    % Frontier Annotation
    \node[text=accentcyan, font=\bfseries, right] at (5.7, 3.8) {Risky Efficient Frontier};
    \draw[->, line width=0.8pt, draw=accentcyan] (5.6, 3.8) -- (4.9, 3.5);

    % --- Capital Market Line (CML) ---
    \draw[draw=accentgold, line width=1.8pt] (RF) -- (CML_End)
        node[text=accentgold, font=\bfseries, pos=1.027609] {CML: Capital Market Line};

    % --- Key Portfolios: Nodes & Callouts ---
    % GMVP Point
    \filldraw[fill=noirvoid, draw=accentemerald, line width=1.5pt] (GMVP) circle (2.8pt);
    \node[right=2mm, text=accentemerald, font=\bfseries] at (GMVP) {GMVP};

    % Tangency Portfolio T
    \filldraw[fill=accentgold, draw=white, line width=1pt] (T) circle (3.2pt);
    \node[above left=2mm, text=white, font=\bfseries] at (T) {Tangency Portfolio $T$};

\end{tikzpicture}
```
