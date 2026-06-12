# Practical Claude Code Skills for Graduate Students

A small collection of three [Claude Code](https://claude.com/claude-code)
skills for graduate students, built for academic and research work. Each skill encodes a *working pattern* —
not a rigid checklist — so Claude reasons from the underlying principle when a
new situation comes up.

## Skills

### [`paper-reader`](skills/paper-reader/SKILL.md)

Plain, direct explanations of research papers that keep analytical depth while
dropping academic stiffness.

- **Conclusion first**, reasoning after; one idea per sentence; concrete example
  before the abstract name.
- **Plain voice** — drop hedging qualifiers, no forced metaphors, short
  paragraphs, a senior-labmate tone rather than a lecturer's.
- **Strictly evidence-based** — grounded in what the paper actually says; name
  the uncertainty instead of guessing or filling gaps.
- **Never drops load-bearing facts** — training regime (full fine-tune / LoRA /
  frozen), base model and size, and whether large-scale pretraining was used.
- **Fixed answer structure** — one-line verdict, the key idea, why it matters,
  and honest limits.

### [`science-confirmer`](skills/science-confirmer/SKILL.md)

Enforces evidence-based answers for any science, social-science, or finance
claim.

- **Search before you speak** — find evidence before answering, preferring
  high-quality sources (peer-reviewed > institutional > reputable news).
- **Honest about uncertainty** — calibrate the wording to the strength of the
  evidence; lay out both sides when findings conflict.
- **No fabrication** — never invent technical terms, never present a hypothesis
  as established fact, never fill gaps with plausible-sounding guesses.
- **Sound reasoning** — don't confuse correlation with causation; don't overuse
  parenthetical asides.

### [`report-writer`](skills/report-writer/SKILL.md)

A working pattern for writing, rewriting, translating, and polishing academic
reports — English/Chinese Word (`.docx`) documents and presentation decks
(`.pptx`).

- **Content before format** — draft each section in Markdown and review it
  before pouring it into the `.docx`/`.pptx`; plan and confirm the structure
  before writing.
- **English first, then translate** into idiomatic, academically natural
  Chinese — re-expression, not word-for-word mapping; the Chinese keeps the
  English layout identical.
- **One source of truth** — every term, stage name, number, and claim aligns to
  the canonical spec/diagram/data; fixes are applied everywhere, not just where
  pointed.
- **Faithful to the data** — write results strictly from the real numbers, no
  overclaiming, no jarring metaphors; surface contradictions instead of hiding
  them.
- **Citations are claims** — verify each reference actually supports what it's
  cited for, renumbered by order of first appearance.
- **Tables & figures** — numbered in order, grouped, cleaned up, language-correct.
- **Diagrams** — architecture / flow / framework figures authored in HTML and
  exported to PNG, with the HTML kept as the editable master.
- **Format hygiene** — no emoji, no awkward justification gaps, deliberate use
  of space; slides designed as slides, not walls of prose.
- **Manual edits are sacred** — the user edits the same file by hand, so never
  clobber their wording.

## Installing

Claude Code discovers skills under `~/.claude/skills/` (personal) or
`.claude/skills/` (per-project). To install all three personally:

```bash
# clone, then copy the skills into your personal skills directory
git clone https://github.com/OU-GC/claude-skills.git
cp -r claude-skills/skills/* ~/.claude/skills/
```

Or install just one:

```bash
cp -r claude-skills/skills/report-writer ~/.claude/skills/
```

Each skill is a directory containing a `SKILL.md` with YAML frontmatter
(`name`, `description`). Claude Code auto-loads it and triggers it based on the
`description`. Restart Claude Code (or start a new session) after copying.

## Repository layout

```
claude-skills/
├── LICENSE
├── NOTICE
├── README.md
└── skills/
    ├── paper-reader/SKILL.md
    ├── science-confirmer/SKILL.md
    └── report-writer/SKILL.md
```

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) and
[NOTICE](NOTICE).
