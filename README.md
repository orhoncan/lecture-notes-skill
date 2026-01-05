# Lecture Notes Generator / Ders Notu Oluşturucu

A Claude skill for generating undergraduate economics lecture notes with mathematical foundations, daily-life examples, and practice problems. Optimized for Obsidian.

Lisans düzeyinde iktisat ders notları oluşturmak için bir Claude skill'i. Matematiksel altyapı, günlük hayat örnekleri ve alıştırmalar içerir. Obsidian için optimize edilmiştir.

---

## Features / Özellikler

| EN | TR |
|----|-----|
| 6-agent workflow (Research → Structure → Content → Quiz → Visual → Interactive) | 6 ajanlı iş akışı (Araştırma → Yapı → İçerik → Soru → Görsel → Etkileşim) |
| Turkish/English output | Türkçe/İngilizce çıktı |
| 3 difficulty levels (Intro/Intermediate/Advanced) | 3 zorluk seviyesi (Giriş/Orta/İleri) |
| Obsidian-compatible LaTeX & TikZ | Obsidian uyumlu LaTeX & TikZ |
| Syllabus parsing from PDF/image | PDF/görselden müfredat çıkarma |
| Wikilinks, callouts, flashcards | Wikilink, callout, flashcard desteği |

## Contents / İçerik

```
lecture-notes/
├── SKILL.md
└── references/
    ├── content-guidelines.md    # LaTeX rules / LaTeX kuralları
    ├── quiz-patterns.md         # Question formats / Soru şablonları
    ├── tikz-templates.md        # Diagram templates / Grafik/görsel vb. şablonları
    ├── economics-glossary-tr.md # TR-EN economics terms / İktisat terimleri
    ├── interactive-elements.md  # Obsidian features / Obsidian özellikleri
    └── topics/
        ├── microeconomics.md    # 6 topics / 6 konu (örnek)
        ├── macroeconomics.md    # 8 topics / 8 konu (örnek)
        └── econometrics.md      # 8 topics / 8 konu (örnek)
```

## Installation / Kurulum

```bash
# Extract to Claude skills directory
# Claude skills dizinine çıkart
unzip lecture-notes.skill -d ~/.claude/skills/
```

## Usage / Kullanım

```
"Create lecture notes on price elasticity"
"Fiyat esnekliği konusunda ders notu oluştur"
```

Claude will ask / Claude size şunları soracak:
1. Language / Dil (TR/EN)
2. Level / Seviye (100/200/300)
3. Syllabus / Müfredat (optional/opsiyonel - PDF, görsel vs. olur.)
4. Scope / Kapsam

## Output Example / Çıktı Örneği

- YAML frontmatter with tags / Etiketli YAML frontmatter
- Learning objectives with checkboxes / Checkbox'lı öğrenme hedefleri
- Bilingual terms table (TR/EN/Symbol) / İki dilli terimler tablosu (TR/EN/Sembol)
- LaTeX equations (Obsidian-compatible) / LaTeX denklemleri (Obsidian uyumlu)
- Daily-life examples in callout boxes / Callout kutularında günlük hayattan örnekler
- Practice problems with foldable solutions / Açılır çözümlü alıştırma soruları
- Related topics via `[[wikilinks]]` / `[[wikilink]]` ile ilgili konular

## Requirements / Gereksinimler

- Claude Code or Claude.ai with skills support / Claude aboneliği, skill desteği için ücretli olanlar lazım sanırım
- Obsidian (recommended for viewing / görünütleme için) 
- TikZ plugin for diagrams (optional / opsiyonel ama grafikler için gerekli)

---

MIT License


