---
name: update-three-voices-monthly
description: Research, create, and publish a complete monthly Three Voices issue on the website, with three source-backed voice-AI use cases each in autism care, agriculture, and space technologies, plus implementation tools and build steps. Use when asked to create, update, or publish a Three Voices monthly issue.
---

# Update Three Voices monthly

Create and publish one complete new issue on the Three Voices website with **nine cases total: exactly three in each domain** (`autism`, `agriculture`, `space`). Every case must be about voice AI: spoken input or spoken output must be a core part of the real system, not an optional feature on a text-first chatbot. Include an evidence-based account, an operational walkthrough, and a practical technical prototype guide. The finished issue must render on its Cases and How it works pages, and appear as the latest issue on the Three Voices homepage and archive. Do not stop after creating empty page shells or case data that is not connected to the site.

## 1. Inspect and plan

- Read `_data/threevoices/issues.yml`, the latest case file, `_templates/new-issue/cases.yml`, and the two latest issue pages in `issues/`.
- Use the requested `YYYY-MM` when provided; otherwise use the current month. Set the next issue number by incrementing the latest issue.
- Keep all existing issues unchanged. Add the new issue first in `_data/threevoices/issues.yml`.
- Make a research plan of three distinct voice-AI use cases per domain. Prefer varied, recently reported deployments, studies, and pilots; do not pad a domain with duplicate descriptions of one system.

## 2. Research and verify

- Use web research to find cases reported in or relevant to the issue month. Prioritize peer-reviewed studies, universities, government and space agencies, research institutes, and credible independent reporting. Do not rely on vendor marketing as the sole evidence.
- Confirm that voice is central to the documented use case: voice messages, speech conversation, spoken commands, speech recognition, or spoken responses. Exclude text-only assistants, text-first chatbots with optional voice input, and unrelated speech-generation demos.
- Open and verify every cited source. Prefer a primary source plus independent corroboration where available. Record source title, publisher, publication date, and URL.
- If a source cannot be opened, do not treat a search-result snippet or metadata record alone as verification of its claims. Find accessible corroboration, omit unsupported details, or clearly disclose the limitation; never base a numeric figure solely on a snippet.
- For each case, verify the people or organization, location, use case, system and AI role, input/output, reported status, and every quantitative claim. Keep the date reported distinct from the date an event happened.
- Never invent quotes, outcomes, metrics, deployments, model choices, or technical details. Use an empty quote if a verified, useful quote is unavailable; write `figure: Pilot` or another accurate non-numeric label when no meaningful measured figure exists, and say what is and is not known in `figure_note` and `care`.
- Separate what the sources say the real system does from the proposed prototype in `trace.tools` and `trace.build_steps`. Mark prototypes as recommendations, not as the deployed system. Describe uncertainty and limitations plainly.
- For autism and other health-related cases, avoid diagnosis or treatment advice. State whether the tool is a study, pilot, or approved product only when the sources establish it; retain the learning-prototype and clinical-validation caveat.

## 3. Write the nine cases

Use the schema in `_data/threevoices/cases/<YYYY-MM>.yml` and the starter shape in `_templates/new-issue/cases.yml`.

- Assign IDs `c01` through `c09`, grouped in order: `c01`–`c03` autism, `c04`–`c06` agriculture, `c07`–`c09` space. Each `category` is a one-item list with the matching key. Use the existing category labels in `trace.area`.
- Write clear, accessible case summaries in original wording. Include a short headline, who was involved, what happened, evidence and relevant caveats. Use one or more direct source links in both `links` and `trace.sources`.
- Fill `trace.facts` with the problem, AI/system, inputs, outputs, human oversight, and evidence/status. Tailor labels when needed, but preserve those facts.
- Write `trace.steps` as the real user's operational journey, using only roles supported by the site: `person`, `ai`, `expert`, `outcome`. Do not describe speculative implementation as something the real deployment did.
- Provide 4–6 `trace.tools` entries with concrete, appropriate tools or technologies and a brief explanation of each. Avoid implying that a particular vendor/model was used in the reported case unless sourced.
- Include voice-specific implementation components where appropriate, such as audio capture/telephony, ASR or speech-capable models, turn-taking/streaming, TTS, and low-bandwidth or offline operation.
- Provide 4–6 `trace.build_steps` entries. Each has a concise `title` and actionable `detail`, ordered from problem/data definition through a small prototype, testing with people/domain experts, and safe evaluation/deployment. Make each guide specific to its case; mention data protection, human review, offline/low-connectivity, or safety controls where relevant.
- Keep `trace.worked` and `trace.limits` evidence-based. Set `clinical: true` for health-related prototypes so the site's safety note appears; otherwise use `false`.

## 4. Publish the complete issue to the website

1. Add the nine-case YAML file at `_data/threevoices/cases/<YYYY-MM>.yml`.
2. Add the issue metadata at the top of `_data/threevoices/issues.yml` with its two page URLs, title, concise summary, month, number, and compiled date. Summarize all three domains.
3. Copy the two front-matter files from `_templates/new-issue/` into `issues/<YYYY-MM>/cases.html` and `how-it-works.html`. Replace the issue slug, month/title, and add explicit permalinks matching the existing issue-page pattern. Preserve `sitemap: true` on the cases page and the how-it-works script configuration.
4. The homepage (`index.html`) and archive (`archive.html`) read the newest issue and its case records from the data files. Verify they resolve to the new issue and show its cases; do not edit their templates just to duplicate issue content.
5. Do not alter past issue content. The layouts iterate over the case list and the homepage/archive use the newest issue first.

If research cannot support all nine distinct cases, do not add an incomplete issue entry or publish placeholder pages. Report the research gap and ask for sources or permission to continue research instead.

## 5. Validate before finishing

- Parse the YAML (or run the site's build) and confirm all nine case records render.
- Check there are exactly nine unique IDs in order, exactly three cases in each category, and every case has valid source URLs, `trace.steps`, `trace.tools`, and 4–6 `trace.build_steps`.
- Verify both page front matters point at the new slug and the homepage/archive resolve the new issue as latest, with all nine case links and traces present.
- Review every fact and figure against its cited source. Report any unavailable source or failed build clearly; do not claim publication validation succeeded if it did not.
- Summarize the issue slug, case count by domain, created/updated files, and validation outcome.
