# Interactive Elements for Obsidian

Enhance lecture notes with Obsidian-specific features for better learning.

## Wikilinks for Concept Maps

Link related concepts using `[[wikilinks]]`:

```markdown
The concept of [[elasticity]] is crucial for understanding [[pricing strategies]].
When [[demand]] is elastic, firms should consider [[price discrimination]].
```

**Naming Convention:**
- Use lowercase with hyphens: `[[marginal-cost]]`
- Include topic prefix for organization: `[[micro/elasticity]]`

## Callout Boxes

Use Obsidian callouts for emphasis:

```markdown
> [!definition] Tanım: Esneklik / Definition: Elasticity
> Bir değişkenin diğer değişkendeki değişime duyarlılığının ölçüsü.

> [!formula] Formül
> $$
> \epsilon_d = \frac{\%\Delta Q}{\%\Delta P}
> $$

> [!example] Örnek / Example
> Benzin fiyatı %10 arttığında talep sadece %2 düşüyorsa...

> [!warning] Dikkat / Caution
> Esneklik ile eğim aynı şey değildir!

> [!tip] İpucu / Tip
> Sınav için: Toplam gelir testini kullanın.
```

**Available Callout Types:**
- `[!note]` - General notes
- `[!tip]` - Helpful hints
- `[!warning]` - Common mistakes
- `[!example]` - Worked examples
- `[!definition]` - Key terms (custom)
- `[!formula]` - Important equations (custom)
- `[!question]` - Practice questions

## Spaced Repetition with Dataview

If user has Dataview plugin, add flashcard-ready metadata:

```markdown
---
cards:
  - q: "Talebin fiyat esnekliği formülü nedir?"
    a: "$\\epsilon_d = \\frac{\\%\\Delta Q}{\\%\\Delta P}$"
  - q: "Esnek talep ne demektir?"
    a: "$|\\epsilon_d| > 1$, fiyat değişimine yüksek duyarlılık"
---
```

Or use inline flashcards (Obsidian Spaced Repetition plugin format):

```markdown
Talebin fiyat esnekliği formülü:: $\epsilon_d = \frac{\%\Delta Q}{\%\Delta P}$

$|\epsilon_d| > 1$ ne anlama gelir?:: Esnek talep - fiyat değişimine yüksek duyarlılık
```

## Foldable Sections

Use HTML details for solutions and extra content:

```markdown
<details>
<summary>💡 Çözüm / Solution</summary>

Step-by-step solution here...

$$
P^* = 24
$$

</details>
```

## Progress Tracking

Add checkbox lists for self-assessment:

```markdown
## ✅ Öğrenme Kontrol Listesi / Learning Checklist

- [ ] Arz ve talep eğrilerini çizebilirim
- [ ] Denge fiyat ve miktarı hesaplayabilirim
- [ ] Esneklik formülünü uygulayabilirim
- [ ] Tüketici ve üretici rantını gösterebilirim
```

## Tags for Organization

Use consistent tags in frontmatter:

```yaml
---
tags:
  - economics
  - microeconomics
  - elasticity
  - level/intro
  - lang/tr
---
```

**Tag Hierarchy:**
- `economics`, `microeconomics`, `macroeconomics`, `econometrics`
- `level/intro`, `level/intermediate`, `level/advanced`
- `lang/tr`, `lang/en`
- Topic-specific: `supply-demand`, `game-theory`, `regression`

## Embedded Graphs

Reference TikZ diagrams with anchors:

```markdown
See the supply-demand equilibrium below:

^supply-demand-graph

The equilibrium point $E$ represents...
```

Then link from other notes:
```markdown
As shown in [[lecture-supply-demand#^supply-demand-graph]]...
```

## Table of Contents

For longer lectures, add manual TOC:

```markdown
## İçindekiler / Table of Contents

1. [[#Giriş|Giriş / Introduction]]
2. [[#Matematiksel Çerçeve|Mathematical Framework]]
3. [[#Örnekler|Examples]]
4. [[#Sorular|Practice Problems]]
```
