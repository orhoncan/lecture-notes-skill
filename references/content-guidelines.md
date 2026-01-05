# Content Writing Guidelines

## Mathematical Presentation

### Progression Pattern

1. **Intuitive introduction**: Start with a relatable scenario
2. **Verbal definition**: Explain concept in plain language
3. **Formal definition**: Present mathematical notation
4. **Derivation**: Show step-by-step mathematical development
5. **Interpretation**: Explain what the math means economically
6. **Application**: Connect back to real examples

### LaTeX Conventions for Obsidian

**Inline math**: Use single dollars with spaces: `$P = MC$`

**Display equations**: MUST have blank lines before and after, and `$$` on own lines:

```markdown
The profit function is:

$$
\pi = TR - TC
$$

where $TR$ is total revenue.
```

**NEVER do this** (won't render):
```markdown
The answer is: $$x = 5$$ which means...
$$\text{GDP}_A = \frac{500}{50} = 10$$ $$\text{GDP}_B = 15$$
```

**Multi-line equations**: Use `aligned` environment with blank lines around:

```markdown
Solving for equilibrium:

$$
\begin{aligned}
MR &= \frac{d(TR)}{dQ} \\[6pt]
&= \frac{d(P \cdot Q)}{dQ} \\[6pt]
&= P + Q \cdot \frac{dP}{dQ}
\end{aligned}
$$

This shows that marginal revenue depends on...
```

**Fractions with text**: Use `\textrm{}` not `\text{}` for better compatibility:

```markdown
$$
\textrm{Kişi Başı GSYİH} = \frac{\textrm{Toplam GSYİH}}{\textrm{Nüfus}}
$$
```

**Subscripts with text**: Prefer simple subscripts or wrap carefully:

```markdown
Good: $GDP_A$ or $\textrm{GDP}_A$
Avoid: $\text{Kişi Başı GSYİH}_A$
Better: $Y_A$ (define $Y$ = GSYİH in text)
```

**Numbered equations**: Use `\tag{}` on separate display:

```markdown
$$
Q_d = a - bP \tag{1}
$$
```

### Common Economics Notation

| Symbol | Meaning |
|--------|---------|
| $P$ | Price |
| $Q$ | Quantity |
| $D(P)$, $Q_d$ | Demand |
| $S(P)$, $Q_s$ | Supply |
| $\pi$ | Profit |
| $U(x,y)$ | Utility function |
| $C(Q)$, $TC$ | Total cost |
| $MC$ | Marginal cost |
| $MR$ | Marginal revenue |
| $\epsilon$ | Elasticity |
| $\mathcal{L}$ | Lagrangian |
| $\lambda$ | Lagrange multiplier |

## Daily-Life Examples

### Guidelines

- Use examples from Turkish/local context when writing in Turkish
- Reference familiar products, services, and situations
- Include current approximate prices/values when relevant
- Connect to student experiences (coffee shops, streaming services, transportation)

### Example Patterns

**Consumer choice**: Spotify vs. Apple Music subscription decisions
**Elasticity**: Fuel price changes and commuting behavior
**Market structures**: Local bakeries vs. supermarket chains
**Game theory**: Group project free-riding, social media coordination
**Externalities**: Traffic congestion, neighbor's loud music

### Example Box Format

```markdown
> 💡 **Günlük Hayat Örneği / Daily-Life Example**
> 
> [Scenario description]
> 
> **Economic interpretation**: [How this illustrates the concept]
```

## Section Depth Guidelines

| Section Type | Target Length | Focus |
|--------------|---------------|-------|
| Introduction | 150-250 words | Motivation, relevance |
| Core concept | 300-500 words | Definition, intuition |
| Mathematical framework | 400-600 words | Derivations, proofs |
| Examples | 200-300 words each | Application, interpretation |
| Summary | 100-150 words | Key takeaways only |

## Callout Boxes (Obsidian-compatible)

```markdown
> [!note] Note Title
> Additional context or clarification

> [!warning] Dikkat / Caution
> Common misconceptions or errors

> [!tip] İpucu / Tip  
> Helpful shortcuts or insights

> [!example] Örnek / Example
> Worked example or case study
```
