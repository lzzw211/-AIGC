---
name: aigc-originality-revision
description: Ethical originality and author-voice revision for academic drafts, reports, homework, application materials, blog posts, and other texts that feel AI-generated, generic, templated, statistically uniform, or high in AIGC features. Use when the user asks to lower AIGC rate, reduce AI flavor, humanize writing, polish academic prose, revise Chinese论文/综述/结论/展望, or make text sound more authentic, specific, evidence-grounded, and author-owned without evading detectors, fabricating facts, or hiding required AI disclosure.
---

# AIGC Originality Revision

## Boundaries

Use this skill to improve writing quality, originality, specificity, and author ownership. Do not promise detector scores, guarantee "passing" AI detection, or optimize text to bypass institutional/platform review.

If the user asks for evasion, concealment, fake personal experience, fake citations, or detector-specific tricks, redirect to legitimate revision: clarify authorship, add real evidence, preserve truthful disclosure, and produce a revision note.

Do not explain or exploit particular detector mechanics as a bypass recipe. It is acceptable to discuss observable writing problems such as excessive uniformity, repetitive sentence patterns, generic transitions, unsupported claims, and overly symmetric paragraph structure.

## Workflow

1. Identify the text type, audience, language, required style, and whether citations or AI-use disclosure rules apply.
2. Ask only for missing facts that are necessary to make the writing genuinely specific, such as the author's own experience, dataset, method details, reading notes, examples, instructor requirements, or source list.
3. Diagnose AI-like features before editing:
   - Generic claims without concrete evidence.
   - Repetitive sentence frames and overly balanced paragraphs.
   - Long sentences with stacked modifiers and nested clauses.
   - Consecutive paragraphs with similar length and identical logic.
   - Mechanical numbering, colon-led lists, and template transitions.
   - Vague authority without citations or observable details.
   - Smooth but empty summaries that avoid tradeoffs, limitations, anomalies, and author judgment.
   - Mismatched register, especially overly formal language in personal or student writing.
4. Revise for authentic authorship:
   - Replace generic claims with verifiable details, examples, numbers, source-backed points, or the author's own observations.
   - Vary sentence and paragraph rhythm naturally while keeping the text coherent; avoid forced slang, random errors, or artificial awkwardness.
   - Add qualified judgment, uncertainty, limitations, and causal reasoning where the draft currently overstates.
   - Convert passive phrasing to active academic phrasing when it improves clarity, for example use "测得" instead of "被测定为" and "检测发现" instead of "经检测发现".
   - Preserve the user's meaning, discipline terms, data, citations, quotations, and formatting.
   - Keep academic tone for academic work; "human" does not mean casual.
5. Verify factual integrity:
   - Mark unsupported claims that need sources instead of inventing citations.
   - Keep quoted material exact and citation-dependent.
   - Do not add personal anecdotes, experimental observations, batch anomalies, error ranges, or environmental explanations unless the user supplied them or they are clearly marked as placeholders to verify.
6. Return a transparent result:
   - Provide the revised text.
   - Add a concise change summary focused on specificity, structure, evidence, rhythm, and voice.
   - List any facts, citations, operation details, or personal details still needed from the user.
   - Include an AI-use disclosure suggestion when the context requires one.

## Chinese Academic Rewrite Rules

For Chinese academic or student writing, prefer concrete subject-action-object sentences over broad abstractions. Reduce formulaic phrases such as "随着时代的发展", "综上所述", "具有重要意义", "具有广阔的应用前景", and "不可忽视". Replace them with the actual research object, observed phenomenon, data, source, limitation, or author's judgment.

Break long sentences when they exceed roughly 50 Chinese characters and contain multiple causal, conditional, or parallel clauses. Split them into two or three sentences with uneven length. Keep key terms stable.

Avoid nested enumeration such as "（1）（2）（3）", "第一、第二、第三", and "A：...；B：...；C：...". Convert list logic into natural academic transitions such as "在...方面", "与此同时", "另外值得关注的是", "从实验过程看", or "这一差异还体现在...". Do not overuse any one transition.

Remove colon-led parallel blocks when they make the passage read like a template. Turn each item into a separate sentence or paragraph, and vary paragraph openings.

Add concrete fluctuation only when supported by the user's material. Useful details include operation observations, error ranges, abnormal batches, environmental conditions, sample differences, parameter drift, and measurement uncertainty. If the source text lacks these details, insert a bracketed placeholder such as "[此处可补充第3批样品偏高的原因]" rather than fabricating.

Add author judgment after objective statements when appropriate. Use restrained academic judgment such as "这一现象值得注意", "综合来看，该结果更可能反映...", "实际应用中仍需权衡...", or "该差异提示后续实验应进一步控制...". Avoid empty concluding formulas.

Create asymmetric paragraph lengths. Do not let three consecutive paragraphs have nearly identical length and structure. Condense one paragraph when it only repeats background; expand another when method details, evidence, or limitation analysis are necessary.

Use transitions between paragraphs. End a paragraph with a sentence that points to the next variable, method, result, or limitation, or start the next paragraph by explicitly carrying forward the previous finding.

Do not use oral or internet-style expressions such as "说白了", "问题不大", "有点意思", or "挺明显". Maintain formal academic prose.

Do not use vague source signals such as "据统计", "相关研究表明", or "一般认为" unless the user provides a concrete citation or dataset.

## Literature Review Guidance

For literature reviews, avoid flat patterns such as "A认为...B指出...C提出...". First identify the central study or dominant view, then compare secondary studies around method, object, evidence, or conclusion. End with the user's evaluation of what the literature explains well and what remains unresolved.

Keep source attributions precise. Do not add authors, years, journals, or conclusions that are not present in the user's source material.

## Conclusion And Outlook Guidance

For conclusion sections, merge numbered findings into natural paragraphs when possible. Preserve all core conclusions and data, but arrange them by research question, evidence chain, or practical implication instead of a rigid list.

For outlook sections, discuss real constraints such as sample size, operating conditions, engineering cost, reproducibility, data availability, model assumptions, measurement error, or scenario transfer. Avoid generic claims about "broad application prospects" unless the passage names concrete application conditions.

## Revision Modes

Use **light revision** when the draft is mostly user-written and needs polish. Keep structure and most wording.

Use **deep revision** when the draft is generic or visibly templated. Rebuild paragraph logic, add placeholders for missing evidence, and explain what user-provided material would improve authenticity.

Use **diagnostic only** when the user wants an AIGC-risk review. Score qualitatively as low, medium, or high risk, explain observable reasons, and avoid claiming certainty about authorship.

## Output Format

If the user requests the Chinese "先输出改写后的段落，然后末尾一句话注明方法" format, return:

```markdown
改写后的段落...

——[改写使用了：拆长句、调整段落节奏、弱化模板表达、补充过渡句、加入作者判断]
```

Otherwise, for short text, return:

```markdown
### Revised Text
...

### What Changed
- ...

### Still Needed
- ...
```

For long documents, work section by section. Start with the highest-risk passages, keep headings intact, and avoid rewriting the entire document unless the user explicitly asks.

## Quality Checklist

Before finalizing, confirm:

- The revision is more specific, not merely more irregular.
- Added details are either supplied by the user, clearly marked as placeholders, or source-backed.
- The text still matches the requested genre and audience.
- Professional terms, data, citations, quotations, and factual claims are preserved or flagged.
- The response does not offer detector-bypass tactics or guaranteed AIGC-rate reduction.
