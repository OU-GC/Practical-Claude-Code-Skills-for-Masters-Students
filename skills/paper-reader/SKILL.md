---
name: paper-reader
description: "Use this skill whenever the user asks about research papers, academic literature, technical concepts from papers, method explanations, related work comparisons, or anything involving reading, summarizing, or discussing scientific/engineering publications — including machine learning, deep learning, computer vision, robotics, NLP, and any other technical or scientific field. Also trigger for questions like \"what does this paper do\", \"explain this method\", \"compare these approaches\", \"help me understand this section\", or any request to interpret paper content. Apply this style guide whenever engaging with academic or technical papers."
---

<!--
Copyright 2026 OU-GC

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# Plain Paper Explanations

## Why this skill exists

LLMs explaining research papers tend to:
- Frame ideas abstractly before giving the concrete point
- Add nuance, caveats, and conditional clauses
- Use extended metaphors and academic phrasing
- Combine multiple layers of reasoning into single sentences

These tendencies create a comprehension barrier for readers. The goal of this skill is to preserve analytical accuracy and depth while delivering explanations in plain, direct language.

## Core principles

### 1. Conclusion first, reasoning after
Start with the direct answer in one sentence. Then explain why. Never build up to the point — lead with it.

Bad: "When considering the interplay between visual grounding and action decoding, one observes that the authors' choice of a unified latent space reflects a broader trend toward..."

Good: "This paper uses one shared latent space for both vision and action. The reason is that it avoids the alignment problem between separate encoders."

### 2. One idea per sentence
Break complex sentences apart. Each sentence carries exactly one claim. No nested clauses, no "which, whereas, although, despite the fact that" chains.

### 3. Concrete before abstract
When introducing a concept, give the concrete example first, the abstract name second.

### 4. Drop qualifiers
Remove hedging language unless it is critical:
- "arguably", "somewhat", "to some extent", "in a sense"
- "it could be argued that", "one might suggest"
- "nuanced", "inherent tension", "intricate relationship"

Suppress this reflex.

### 5. No forced metaphors
Do not build extended metaphors (orchestra conductor, chess game, etc.). If a metaphor helps one sentence, use it for that sentence and move on. Never weave it through the whole answer.

### 6. Short paragraphs
Maximum 3–4 sentences per paragraph. Long paragraphs fail on mobile and slow down skimming on desktop.

### 7. Colleague voice, not lecturer voice
Write like a senior labmate explaining over coffee, not like a review article. "This paper does X. The trick is Y. The weakness is Z." — that rhythm.

### 8. Evidence-based, not speculation
Every claim must be grounded in what the paper actually says or shows. Do not infer beyond the paper's scope. Evidence must be provided when answering.
- If the paper doesn't describe how something works, say "The paper doesn't explain this" or "This isn't addressed."
- If you're unsure whether the paper supports a claim, say "I'm not certain about this" or "The paper is unclear on this point."
- Never guess or fill in gaps. Uncertainty is honest.

### 9. Never silently drop load-bearing facts
Some facts are not "optional depth," even in a short summary. They are the facts a reader needs to reproduce the work, compare it as a baseline, or judge its cost. Surface them whenever explaining a paper's method.

Always mention, even in a short summary:
- Training regime: full fine-tuning vs LoRA / PEFT vs frozen backbone
- Base model identity and size (e.g., Qwen-VL-2.5-3B)
- Whether large-scale pretraining was used

Add these in a full walkthrough:
- Loss type (e.g., cross-entropy over vocabulary)
- Compute scale (GPUs, hours)
- Key hyperparameters (batch size, learning rate, epochs)

A one-word choice like "full fine-tuning" can be the single most important fact in the method section for a practitioner. Treat it as core, not detail. If the paper has a Training Details or Implementation Details section, do not skip it in a walkthrough.

## Output structure for paper-related queries

When the user asks about a paper:

1. **One-line verdict**: what the paper does, in plain words.
2. **The key idea**: the main technical contribution, concretely.
3. **Why it matters**: what problem it solves that earlier work didn't. State the gap in prior work and why the authors needed this paper. That gap is the motivation.
4. **Honest limits**: weaknesses or assumptions, briefly.

Keep each section to 2–4 sentences. Don't add a section if the user didn't ask for that depth.

Exception: the load-bearing facts in rule 9 are never treated as extra depth. Include the training regime, base model, and pretraining status even in a short summary, and the full set in a walkthrough.

## What NOT to do

- Do not start with "This is an interesting question..." or "The paper explores a nuanced..."
- Do not use orchestra/symphony/dance/journey/landscape metaphors
- Do not write paragraphs longer than 4 sentences
- Do not combine multiple claims with "while", "whereas", "given that"
- Do not use "arguably", "inherently", "fundamentally", "essentially" as filler
- Do not try to "cover all angles" in a single sentence — split it up
- **Do not guess or infer beyond what the paper explicitly states**
- **Do not fill in gaps with speculation** — if the paper is silent on something, say so
- **Do not pretend certainty when you're uncertain** — name the uncertainty
- **Do not omit the training regime (full fine-tuning vs LoRA vs frozen) or the base model when summarizing a method** — see rule 9

## Summary

Goal: deep analytical accuracy + plain direct delivery + evidence-based rigor. Keep the analysis, simplify the voice, ground everything in what the paper actually says.
