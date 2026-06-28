# Practical Claude Code Skills for Chinese-speaking Master's Students

A small collection of Claude Code skills for Chinese-speaking master's students, built for academic and research work. Each skill encodes a working pattern — not a rigid checklist — so Claude reasons from the underlying principle when a new situation comes up.

## Skills

### [`chinese-polisher`](skills/chinese-polisher/SKILL.md)

A Chinese-writing style guide that applies to *all* Chinese output, removing the
translated-from-English stiffness and tightening the syntax.

- **One idea per sentence** — a single subject and a complete predicate; no long
  comma-chained run-ons.
- **Cut connectives, keep grammar words** — drop logical glue like 因此 / 此外
  where the parallel structure already carries it, but never drop the
  load-bearing prepositions 以 / 把 / 對 / 被 / 將.
- **No word-for-word structure words** — don't render `vs` / `and/or` / `via` /
  `such as` literally; state comparisons with a verb instead.
- **No em-dash** — replace `——` with a period, comma, or colon by
  what it's actually doing.
- **Parentheses only for term glosses** — keep clauses, reasons, and qualifiers
  in the main sentence; parentheses are for English-term translations only.

### [`paper-reader`](skills/paper-reader/SKILL.md)

Plain, direct explanations of research papers for Chinese-speaking readers,
keeping analytical depth while dropping academic stiffness.

- **Conclusion first, reasoning after** — lead with the one-sentence answer;
  one claim per sentence; the concrete example before the abstract name.
- **Plain voice** — drop hedging qualifiers, no extended metaphors, short
  paragraphs (3–4 sentences), a senior-labmate-over-coffee tone rather than a
  lecturer's.
- **Prose first, lists when warranted** — explain in connected prose; reserve
  bullets for genuinely list-like content, and never shatter a chain of reasoning
  into fragments.
- **Strictly evidence-based** — grounded in what the paper actually says; name
  the uncertainty instead of guessing or filling gaps.
- **Never drops load-bearing facts** — training regime (full fine-tune / LoRA /
  frozen), base model and size, whether large-scale pretraining was used, and
  compute scale.
- **Inputs, outputs, and data flow precisely** — for every component, name the
  modality and representation that go in and come out, trace the end-to-end
  path, distinguish a component from what feeds it, and quote the paper's actual
  numbers.
- **Fixed answer structure** — one-line verdict, the key idea, the authors' own
  claimed contributions (kept separate), the motivation (the gap in prior work),
  and honest limits.
- **Established terms only** — uses terminology the field already recognizes;
  never coins term-like phrases, and says so plainly when no standard term exists.
- **Chinese gloss** — English term first, pure Chinese translation in
  parentheses, e.g. `attention mechanism（注意力機制）`; commonly accepted terms
  like query / key / value / token keep their English names.

### [`report-writer`](skills/report-writer/SKILL.md)

A working pattern for writing, rewriting, and polishing academic reports — Word
(`.docx`) documents and presentation decks (`.pptx`) — with a bilingual
English/Chinese workflow.

- **Content before format** — draft each section in Markdown and review it
  before pouring it into the `.docx`/`.pptx`; plan and confirm the structure
  before writing.
- **One source of truth** — every term, stage name, number, and claim aligns to
  the canonical spec/diagram/data; fixes are applied everywhere, not just where
  pointed.
- **Faithful to the data** — write results strictly from the real numbers, no
  overclaiming, no jarring metaphors; surface contradictions instead of hiding
  them.
- **Citations are claims** — verify each reference actually supports what it's
  cited for, renumbered by order of first appearance.
- **Tables & figures** — numbered in order, grouped, cleaned up.
- **Diagrams** — architecture / flow / framework figures authored in HTML and
  exported to PNG, with the HTML kept as the editable master.
- **Format hygiene** — no emoji, no awkward justification gaps, deliberate use
  of space; slides designed as slides, not walls of prose.
- **Manual edits are sacred** — the user edits the same file by hand, so never
  clobber their wording.
- **English first, then translate into idiomatic, academically natural
  Chinese** — re-expression, not word-for-word mapping; the Chinese keeps the
  English layout identical.
- **Language-correct tables** — no Chinese text left inside the English version.

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

## Installing

Claude Code discovers skills under `~/.claude/skills/` (personal) or
`.claude/skills/` (per-project). To install all of them personally:

```bash
# clone, then copy the skills into your personal skills directory
git clone https://github.com/OU-GC/Practical-Claude-Code-Skills-for-Masters-Students.git
cp -r Practical-Claude-Code-Skills-for-Masters-Students/skills/* ~/.claude/skills/
```

Or install just one:

```bash
cp -r Practical-Claude-Code-Skills-for-Masters-Students/skills/report-writer ~/.claude/skills/
```

Each skill is a directory containing a `SKILL.md` with YAML frontmatter
(`name`, `description`). Claude Code auto-loads it and triggers it based on the
`description`. Restart Claude Code (or start a new session) after copying.

## Repository layout

```
Practical-Claude-Code-Skills-for-Masters-Students/
├── LICENSE
├── NOTICE
├── README.md
└── skills/
    ├── chinese-polisher/SKILL.md
    ├── paper-reader/SKILL.md
    ├── report-writer/SKILL.md
    └── science-confirmer/SKILL.md
```

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) and
[NOTICE](NOTICE).
