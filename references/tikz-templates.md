# TikZ Templates for Economics

Simple, Obsidian-compatible TikZ diagrams. These use basic features that render reliably.

## Important Notes

1. Keep diagrams simple - complex `plot` functions often fail
2. Use straight lines and basic shapes
3. Avoid `domain`, `samples`, and complex math in plots
4. Test each diagram before including in notes

## Supply and Demand (Basic)

```tikz
\begin{document}
\begin{tikzpicture}
  % Axes
  \draw[->] (0,0) -- (5,0) node[right] {$Q$};
  \draw[->] (0,0) -- (0,4) node[above] {$P$};
  
  % Demand curve (straight line)
  \draw[blue, thick] (0.5,3.5) -- (4,0.5) node[right] {$D$};
  
  % Supply curve (straight line)
  \draw[red, thick] (0.5,0.5) -- (4,3.5) node[right] {$S$};
  
  % Equilibrium point
  \fill (2.25,2) circle (2pt);
  \node[above right] at (2.25,2) {$E$};
  
  % Dashed lines to axes
  \draw[dashed] (2.25,0) -- (2.25,2);
  \draw[dashed] (0,2) -- (2.25,2);
  
  % Labels
  \node[below] at (2.25,0) {$Q^*$};
  \node[left] at (0,2) {$P^*$};
\end{tikzpicture}
\end{document}
```

## Consumer and Producer Surplus

```tikz
\begin{document}
\begin{tikzpicture}
  % Axes
  \draw[->] (0,0) -- (5,0) node[right] {$Q$};
  \draw[->] (0,0) -- (0,4) node[above] {$P$};
  
  % Demand and Supply
  \draw[blue, thick] (0.5,3.5) -- (4,0.5);
  \draw[red, thick] (0.5,0.5) -- (4,3.5);
  
  % Consumer surplus - blue triangle
  \fill[blue, opacity=0.2] (0.5,3.5) -- (2.25,2) -- (0.5,2) -- cycle;
  
  % Producer surplus - red triangle  
  \fill[red, opacity=0.2] (0.5,0.5) -- (2.25,2) -- (0.5,2) -- cycle;
  
  % Labels
  \node at (1,2.8) {\small CS};
  \node at (1,1.2) {\small PS};
  
  % Equilibrium
  \draw[dashed] (2.25,0) -- (2.25,2);
  \draw[dashed] (0,2) -- (2.25,2);
  \node[below] at (2.25,0) {$Q^*$};
  \node[left] at (0,2) {$P^*$};
\end{tikzpicture}
\end{document}
```

## Price Ceiling Effect

```tikz
\begin{document}
\begin{tikzpicture}
  % Axes
  \draw[->] (0,0) -- (5,0) node[right] {$Q$};
  \draw[->] (0,0) -- (0,4) node[above] {$P$};
  
  % Demand and Supply
  \draw[blue, thick] (0.5,3.5) -- (4,0.5) node[right] {$D$};
  \draw[red, thick] (0.5,0.5) -- (4,3.5) node[right] {$S$};
  
  % Price ceiling line
  \draw[thick, green!50!black] (0,1.2) -- (4.5,1.2);
  \node[left, green!50!black] at (0,1.2) {$P_c$};
  
  % Shortage
  \draw[<->] (1.2,0.3) -- (3.3,0.3);
  \node[below] at (2.25,0.3) {Shortage};
  
  % Quantity points
  \draw[dashed] (1.2,0) -- (1.2,1.2);
  \draw[dashed] (3.3,0) -- (3.3,1.2);
  \node[below] at (1.2,0) {$Q_s$};
  \node[below] at (3.3,0) {$Q_d$};
\end{tikzpicture}
\end{document}
```

## Budget Constraint

```tikz
\begin{document}
\begin{tikzpicture}
  % Axes
  \draw[->] (0,0) -- (5,0) node[right] {$x$};
  \draw[->] (0,0) -- (0,5) node[above] {$y$};
  
  % Budget line
  \draw[red, thick] (0,4) -- (4,0);
  \node[red, right] at (2.5,1.5) {$BC$};
  
  % Intercept labels
  \node[left] at (0,4) {$\frac{M}{P_y}$};
  \node[below] at (4,0) {$\frac{M}{P_x}$};
  
  % Feasible region
  \fill[gray, opacity=0.1] (0,0) -- (0,4) -- (4,0) -- cycle;
  \node at (1.2,1.2) {Feasible};
\end{tikzpicture}
\end{document}
```

## Game Theory Matrix

```tikz
\begin{document}
\begin{tikzpicture}
  % Draw grid
  \draw (0,0) rectangle (4,2);
  \draw (2,0) -- (2,2);
  \draw (0,1) -- (4,1);
  
  % Row/Column labels  
  \node at (1,2.4) {Left};
  \node at (3,2.4) {Right};
  \node at (-0.6,1.5) {Up};
  \node at (-0.6,0.5) {Down};
  
  % Player labels
  \node at (2,3) {\textbf{Player 2}};
  \node[rotate=90] at (-1.3,1) {\textbf{Player 1}};
  
  % Payoffs
  \node at (1,1.5) {$(3,3)$};
  \node at (3,1.5) {$(0,5)$};
  \node at (1,0.5) {$(5,0)$};
  \node at (3,0.5) {$(1,1)^*$};
\end{tikzpicture}
\end{document}
```

## Simple PPF

```tikz
\begin{document}
\begin{tikzpicture}
  % Axes
  \draw[->] (0,0) -- (5,0) node[right] {Good $X$};
  \draw[->] (0,0) -- (0,5) node[above] {Good $Y$};
  
  % PPF as quarter ellipse (approximated with bezier)
  \draw[blue, thick] (0,4) .. controls (1,3.8) and (3.5,2) .. (4,0);
  \node[blue] at (3.5,2.5) {PPF};
  
  % Points
  \fill (1.5,3.2) circle (2pt);
  \node[above right] at (1.5,3.2) {$A$};
  
  \fill[red] (1.5,1.5) circle (2pt);
  \node[below right, red] at (1.5,1.5) {$B$ (inefficient)};
\end{tikzpicture}
\end{document}
```

## Monopoly (Simplified)

```tikz
\begin{document}
\begin{tikzpicture}
  % Axes
  \draw[->] (0,0) -- (5,0) node[right] {$Q$};
  \draw[->] (0,0) -- (0,4) node[above] {$P$};
  
  % Demand (AR)
  \draw[blue, thick] (0.5,3.5) -- (4,0.5);
  \node[blue, right] at (4,0.5) {$D$};
  
  % MR (steeper, same intercept)
  \draw[blue, dashed] (0.5,3.5) -- (2.25,0.5);
  \node[blue, right] at (2.25,0.5) {$MR$};
  
  % MC (upward sloping)
  \draw[red, thick] (0.5,0.8) -- (3.5,2.5);
  \node[red, right] at (3.5,2.5) {$MC$};
  
  % Monopoly output
  \fill (1.4,1.3) circle (2pt);
  \draw[dashed] (1.4,0) -- (1.4,2.6);
  \draw[dashed] (0,2.6) -- (1.4,2.6);
  
  \node[below] at (1.4,0) {$Q_m$};
  \node[left] at (0,2.6) {$P_m$};
  
  % Price point on demand
  \fill (1.4,2.6) circle (2pt);
\end{tikzpicture}
\end{document}
```

## Usage Tips

1. **Always test** - Copy diagram to Obsidian and verify it renders
2. **Keep it simple** - Straight lines are more reliable than curves
3. **Use bezier for curves** - `.. controls (x1,y1) and (x2,y2) ..` is more reliable than `plot`
4. **Turkish labels** - Replace English labels when writing in Turkish
5. **Color scheme** - Blue = demand/consumer, Red = supply/producer
