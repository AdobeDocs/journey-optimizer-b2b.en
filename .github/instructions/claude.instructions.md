---
applyTo: "**/*.md"
---

# Adobe Experience League Documentation: Claude Code Instructions

You are assisting a technical writer on the Adobe Experience League public documentation repo (`journey-optimizer-b2b.en`). Every piece of content you draft, edit, or review MUST follow all rules below. When in doubt about terminology, consult the referenced wikis using the Confluence MCP tool (`mcp__adobe-wiki-confluence`).

---

## 1. Voice, Tone, and Style

### User-focused writing

Center the user, not the feature. Write what the user can **do**, not what the feature does.

- Use second person ("you") and imperative mood for instructions.
- Use "you" when speaking to the audience about themselves, not "users." "Users" is acceptable when referring to a role (e.g., an admin managing users).
- AVOID "Feature X allows you to…" or "Feature X enables you to…". Put the user as the subject or use imperative mood.
  - Bad: "The Server API can be used on servers."
  - Good: "Use the Server API on servers."
  - Bad: "Calculated fields allow for values to be created…"
  - Good: "Use calculated fields to create values…"
- Be mindful of "you can." It is appropriate but can be overused, creating repetitive or wordy sentences.
- Use "select" for choosing options from a list or highlighting text. Use "click" only for explicit mouse actions. Avoid naming the control type (button, link) unless required for disambiguation.
- Use "Open" / "Close" for applications and major windows or panels.
- Use "Leave" for leaving a site or experience (e.g., "Leave Report Builder").
- Use "go to" or "navigate to" for navigation.
- Use "Play video," not "Watch video." Not everyone is watching.
- Use "View," "Show," or "Go to all," not "See all." Not everyone is seeing.
- Use "sign in" / "sign out," not "log in" / "log out."
- Avoid "in order to." Use "to" instead.
- Avoid "utilize." Use "use" instead.
- Avoid vague adjectives like "fast" or "easy." Be precise: "This process usually takes 5 minutes."
- Avoid weak adverbs: very, extremely, incredibly.

### Sentence and paragraph structure

- Target ≤20 words per sentence (authoring guide says ≤35 max). One thought per sentence.
- Paragraphs: max 125 words, ideally ≤100. Max 4 to 5 sentences. No walls of text.
- Use active voice. Avoid passive constructions and nominalizations (e.g., use "create" not "creation").
- Use simple subject-verb-object structure.
- Avoid false subjects ("It is…", "There are…").
- Use the same word consistently. Do not rotate synonyms.
- No humor, slang, jargon, or culture-specific examples (must localize well).
- Use the Oxford comma in lists of three or more items.
- Spell out whole numbers zero through nine; use numerals for 10 and above.
- No semi-colons. Use a period and a new sentence instead.

### Scannability

- Readers should grasp the article scope from title, headings, and captions alone.
- Max 2 to 5 subsections per section.
- Target 7 steps per task; 10 is the practical maximum. Break longer procedures into subtasks.
- Max 8 items per bulleted list.
- Use tables when they make term/definition lists easier to scan.
- Content should score below grade 10 on a readability test (after removing proper nouns and titles).

### Writing for AI discovery

AI assistants and search tools increasingly surface Experience League content in generated answers.

- Put key terms (product names, feature names, tasks) in body text and link text, not only in images or complex tables. AI systems rely on readable text.
- Write clear, self-contained headings and first paragraphs. AI tools often extract these in isolation; they must make sense without surrounding context.
- Keep sentences short and direct. Concise prose is easier for AI to parse and quote accurately.
- Use structured formats (numbered steps, short bullets, definition-style headings) for procedures and comparisons. Structure helps AI identify the correct answer.
- Include synonyms or alternate terms on first use (e.g., "ECID (Experience Cloud ID)") to improve retrieval for varied query phrasing.
- Ensure metadata fields (title, description, feature tags) are complete and accurate.

---

## 2. Adobe Markdown Syntax (Experience League)

### Frontmatter (required on every file)

```yaml
---
title: Title Case Title Here
description: Learn how to... or Learn about... (150-160 chars, sentence case).
---
```

Additional optional fields used in this repo: `solution`, `type`, `role`, `exl-id`. Match the pattern of existing files.

**IMPORTANT:** Do NOT add `exl-id` when creating a new page. It is generated automatically at publishing time. Only `exl-id` fields that already exist on existing pages should be preserved.

**Title metadata rules:**

- Title case (only place on Experience League that uses title case).
- Max 60 characters (English). The system appends `| Adobe Experience Platform` automatically. Factor that into length.
- Do NOT add the pipe or product name. It is added automatically.
- Think of it as the SEO version of your page name (what users search for).
- Concept title: noun phrase (e.g., "Page Views Report").
- Task title: verb phrase (e.g., "Create a Segment for Page Views").
- Acronyms are not approved by Marketing for most uses, but limited use is acceptable for SEO, TOC entries, description metadata, and headings where length is a concern.

**Description metadata rules:**

- Sentence case. 150 to 160 characters ideally; 160 max.
- One to two concise sentences. First sentence summarizes; second is a call to action.
- Begin concept descriptions with "Learn about..." or "Understand...".
- Begin task descriptions with "Learn how to..." or an imperative verb.
- Do NOT begin with the product name. Start with a verb for SEO.
- Do NOT copy the first paragraph verbatim (different purpose).
- If a metadata field begins with a `[!DNL]` or `[!UICONTROL]` tag, enclose the entire field value in quotation marks or validation fails.

### Headings

- `#` = H1 (article title, one per page). `##` = H2 main sections. `###` = H3, etc.
- Do NOT skip heading levels (e.g., do not jump from H2 to H4).
- Target ≤5 words. Max 69 characters (English).
- Blank line before AND after every heading.
- Every heading must be followed by at least one sentence of body text. NEVER stack two headings or place a note, list, or table directly under a heading without a paragraph first.
- Custom anchor IDs: `## Section title {#section-id}` (lowercase, hyphenated, no periods).
- Avoid anchor names that conflict with JavaScript/CSS: search, results, content, header, footer, navigation, sidebar, pagination, etc.
- Do NOT place badges or any Markdown elements inside heading text.
- Do NOT use single-word abstract headings like "Overview" or "Introduction" alone. Always describe what the overview or introduction is about.
- Do NOT number H1s. For tutorials, use "Step 1: ..." in subheadings rather than numbered anchors.
- Sentence case for all headings (proper nouns and UI elements excepted).
- Concept headings: nouns and noun phrases (e.g., "Overview of segmentation").
- Task headings: imperative verbs (e.g., "Create a targeting workflow"). Avoid gerunds (-ing forms).
- Avoid nounifying verbs with -ment or -ion (use "Create a roadmap" not "Roadmap creation").
- Keep heading structure parallel within sections.
- No duplicate heading anchor IDs in a document.
- If a heading includes numerals, specify an explicit heading ID that does not start with a number (e.g., `## Release notes for 2016 {#release-notes-2016}`).

### Links

- Internal cross-references: root-relative paths starting with `/help/`: `[link text](/help/path/to/file.md)`
- Deep links to anchors: `[text](/help/path/to/file.md#anchor-id)`
- External links (outside this repo): absolute `https://` URLs. These open in a new tab automatically.
- Open in new tab explicitly: append `{target="_blank"}` (use for cross-guide links).
- Reference links (using `[1]: url` style): only work with absolute URLs.
- Do NOT add the same file multiple times in a TOC.
- Avoid raw URLs in body text. Always use descriptive link text.
- Never use "click here" or "link" as link text. Screen readers surface links out of context and cannot distinguish multiple "click here" instances.
- Link text must make the destination clear on its own.
- For "More information" cross-reference lists, use a `More help on this topic` subheading with a bullet list.

### Images

- Syntax: `![alt text](path/to/image.png)`
- Resize: `{width="300"}` or `{width="50%"}`
- Align: `{align="center"}` or `{align="right"}`
- Zoomable: `{zoomable="yes"}`
- Modal display: `{modal="regular"}`. Do NOT combine with a link.
- Recommended width: 640 to 2000 px. Maximum file size: 5 MB recommended; 100 MB hard limit. Max 100 images per article.
- Images go in an `assets/` subfolder relative to the markdown file.
- Images that must NOT be localized go in a `do-not-localize/` subfolder.
- Always capture screenshots using the **Light** theme in Experience Cloud product UI, not the Dark theme.
- Do NOT show customer data in screenshots.
- Do NOT document third-party interfaces in screenshots. Link to the third party's own documentation instead.
- Do NOT use screenshots just to track progress through screens or show obvious UI elements.
- Do NOT include illustrations of easily identifiable icons more than once per article.
- Do NOT use images of code. Use code blocks instead.
- Do NOT use color alone to convey information (not accessible for colorblind users).
- Do NOT use animated graphics that flash more than three times per second (seizure risk).
- Make sure images have good contrast and are clear.
- Screenshot pixel size guidelines: 2000 px max for large, 672 px for medium, 300 px for small, 30-35 px for icons.
- For callouts: use red HEX #EB1000, 3 px line weight, 8 px corner radius.

### Alt text

Alt text is indexed by Google and read by screen readers. Always write it carefully.

- Describe what the image shows, not just the screen name.
- Use complete sentences with proper grammar and punctuation.
- Include relevant text from the image.
- Use full words, not abbreviations. Screen readers spell out abbreviations.
- Do NOT begin with "This image shows...". Just describe the content directly.
- Alt text is usually not needed for purely decorative images, but provide it when in doubt.

| Good alt text | Avoid |
|---|---|
| Screenshot of the Audience Builder showing geo and age demographic filters selected. | Audience Builder |
| Select an extension from the extension catalog. | Extensions library |

### Videos

- Syntax: `>[!VIDEO](https://video.tv.adobe.com/v/xxxxx/?quality=12&learn=on)`
- Add `?quality=12&learn=on` at the end of all video URLs for best playback.
- Videos must NOT autoplay. Do not add `?autoplay=true` in documentation.
- Always provide a text alternative, transcript, or link to written instructions: "For written instructions, see [link]."
- Use meaningful captions.
- Enable transcripts with `{transcript=true}` on individual videos, or add `auto-video-transcripts: true` to `TOC.md` for an entire guide.

### Notes and admonitions

```markdown
>[!NOTE]
>
>Note content here.

>[!TIP]
>
>Tip content here.

>[!IMPORTANT]
>
>Important content here.

>[!WARNING]
>
>Warning content here.

>[!CAUTION]
>
>Caution content here.
```

Additional types: `[!ADMIN]`, `[!AVAILABILITY]`, `[!PREREQUISITES]`, `[!INFO]`, `[!ERROR]`, `[!SUCCESS]`.

CRITICAL syntax rules:
- There MUST be a blank `>` line between the tag line and the content.
- Every continuation line must start with `>`.
- Blockquote syntax (`>` without a tag) is supported but renders as a plain blockquote. Do NOT use it expecting styled callouts.
- Do NOT add comments inside block components such as bullet lists, especially nested bullet lists. The comment can change how the list renders.

### Tabs

```markdown
>[!BEGINTABS]

>[!TAB Tab label]

Tab content here.

>[!TAB Another tab]

More content.

>[!ENDTABS]
```

- Do NOT nest tab sets.
- Do NOT nest tab sets within lists.
- Tab titles cannot be formatted with bold or italic.
- In-page search (Ctrl+F) does not find content in hidden tabs.

### Collapsible sections

```markdown
+++Click to expand
Content here.

* Bullet one
* Bullet two

+++
```

- Add blank lines above and below lists and code blocks inside collapsibles.
- Do NOT nest collapsible sections inside collapsible sections.
- Headings inside collapsibles are allowed but not recommended.
- Note: Find in Page (Ctrl+F) detects collapsed text in Chrome but not in Safari.

### Shade boxes

```markdown
>[!BEGINSHADEBOX "Optional Title"]

Content with gray background.

>[!ENDSHADEBOX]
```

### Code blocks

- Inline: single backticks `` `code` ``. Use for cookie names, file names, values, parameters, commands, and sample URLs that should not be validated.
- Fenced blocks: triple backticks with language identifier (enables syntax highlighting and a Copy button).
- Optional attributes: `{line-numbers="true"}`, `{start-line="7"}`, `{highlight="11-13, 16"}`
- Code blocks are NOT localized. No need to add DNL or UICONTROL inside them.
- Use backticks (not quotation marks) for code, file names, parameters, and typed text.
- Do NOT use images of code. Always use code blocks.

### Badges

- Inline: `[!BADGE Beta]{type=Informative}`
- Metadata (above H1): `badgePremium: label="Premium" type="Positive"`
- Types: `Informative` (blue), `Positive` (green), `Negative` (red), `Neutral` (dark gray), `Caution` (yellow)
- Max 2 badges in metadata per article.
- Do NOT place badges in headings.
- Do NOT use badges for information that quickly becomes obsolete (e.g., "New").
- Badge labels are localized. Keep them concise.
- For the beta badge, use frontmatter `badgeBeta` only. Do NOT place an inline badge in the H1.
- If you want a badge URL to open in a new tab, add `newtab=true` to the badge syntax.

### Lists

- Use `*` or `-` consistently within a single article. Check the existing file's convention. Mixing markers causes a validation error.
- For numbered lists, use `1.` for every item. GitHub/EDS auto-numbers them correctly.
- Bullet lists: when order is not important. Numbered lists: for steps and ordered procedures.
- For a single-step procedure, use a bullet (`*`) instead of `1.`.
- Keep list entries brief. Usually one sentence or less.
- Use periods for complete sentences; omit periods for single-word or incomplete-sentence entries (apply the rule consistently within a list).
- Do NOT end list items with semicolons, commas, or conjunctions like "and" or "or" when items are meant to read as a simple series.
- All list entries must be grammatically parallel.
- Indent nested content: 3 spaces for numbered lists, 2 for bullet lists.
- Surround lists with blank lines.
- Do NOT use task lists (GitHub-style `- [ ]` checkboxes). They are not supported in Experience League.

### Tables

- Use standard markdown tables.
- For complex layouts (merged cells, borders off), HTML `<table>` is allowed.
- Surround tables with blank lines.
- Use `{style="table-layout:auto"}` for auto-width tables when needed.
- Avoid screenshots in table cells. Small icons or thumbnails are acceptable in cells.

### Preview feature highlighting

Use a span for inline preview content and a div for multi-paragraph preview content:

```markdown
<span class="preview">This feature is in limited availability.</span>
```

```markdown
<div class="preview">

Multiple paragraphs of preview content here.

</div>
```

### Snippets and includes

```markdown
{{$include /path/to/snippet.md}}
```

Use for reusable content blocks shared across multiple articles.

### Special characters

- Escape special characters in body text with a backslash: `\#`, `\*`, `\[`, `\]`.
- Use HTML entities for angle brackets: `&lt;`, `&gt;`, `&amp;`.
- Use HTML entities for special symbols: `&reg;`, `&mdash;`, `&ndash;`.

### Comments

Use HTML comments for draft text or notes to other writers:

```markdown
<!-- This is a comment. Not rendered in the published doc. -->
```

Comments ARE visible to users editing on GitHub.com. Do NOT include confidential information in comments.

Do NOT add comments inside block components like bullet lists (especially nested ones). Comments can break list rendering. In TOC.md files, do not comment out lines in the middle of the TOC list — move comments to the end of the file instead.

### Keyboard actions

Bold each individual key in a keyboard shortcut: **cmd** + **shift** + **p**.

### File and folder naming

- Markdown filenames: lowercase with hyphens. No capitals, underscores, periods, or spaces.
- Use descriptive slugs: `create-calculated-metric.md`, `calculated-metric-overview.md`. Avoid bare filenames like `overview.md` or `introduction.md` unless the IA requires a fixed name.
- Avoid filenames that conflict with JavaScript/CSS: `metadata.md`, `search.md`.
- Asset filenames: lowercase preferred; capital letters and underscores allowed but not recommended.

---

## 3. Localization Tags (CRITICAL)

Always apply localization tags. Machine translation runs automatically on every commit to main.

### `[!DNL Product Name]`: Do Not Localize

Use for branded product names that must remain in English.

**Apply to:**
- Adobe product names: `[!DNL Analytics]`, `[!DNL Target]`, `[!DNL Campaign]`, `[!DNL Experience Platform]`
- Third-party product names: `[!DNL Mozilla Firefox]`, `[!DNL Workfront]`
- Functional names that could confuse translation: `[!DNL Pass]`, `[!DNL Campaign]`
- Boolean operators used as logical terms: `[!DNL AND]`, `[!DNL OR]`

**Do NOT apply to:**
- URLs, file names, or directory names
- Code blocks (not localized by default)
- Acronyms (stay in English automatically)
- Terms already in the Do Not Translate database

**In link text:** Remove the tag brackets to prevent rendering issues. Use `[Adobe](https://www.adobe.com)` not `[[!DNL Adobe]](https://www.adobe.com)`.

### `[!UICONTROL Label]`: UI Controls

Use for interface elements: options, fields, tabs, pages, menus, buttons, and feature names as they appear in the UI. This is the most critical tag for translation quality. Treat it as mandatory in procedures.

**Apply to:**
- Every clickable UI element in procedure steps (mandatory)
- Feature names and navigation elements as shown in the product
- Page names, options, fields, and tabs as labeled in the interface

**Formatting:**
- Bold in steps and navigation: `Select **[!UICONTROL Destinations]** from the left navigation.`
- Italics acceptable in conceptual text (non-step) for clarity.
- In HTML tables: use `<span class="uicontrol">term</span>` instead of `[!UICONTROL]`.
- In link text: remove the tag brackets.

**Capitalization:** Match the interface exactly.

**Do NOT apply to:**
- Generic terms used conceptually: "segment", "metric", "campaign" (only tag when explicitly referring to the UI element)
- Long sentences (unless the UI element name itself is a long phrase)
- Code blocks or acronyms
- Icon descriptions. Use the icon's hover/tooltip name if available; do not tag generic descriptions like "pencil icon"

### `[!DONOTLOCALIZE]`: Exclude entire sections

Wrap content that must remain in English across all locales:

```markdown
>[!DONOTLOCALIZE]
>
>Content that must not be translated.
```

Not needed inside code blocks. Those are not localized by default.

### Where tags can and cannot be used

**Can be used in:** paragraphs, lists, headings, tables, badges, alt text, and metadata.

**Cannot be used in:** code blocks, acronyms.

**Metadata rule:** If a metadata field (title or description) begins with a `[!DNL]` or `[!UICONTROL]` tag, enclose the entire field value in quotation marks or validation will fail.

---

## 4. Information Structure and Content Types

### Three content types: keep them separated

- **Concept**: What and why. Introductions, overviews, background. Use noun/noun-phrase headings.
- **Task**: How. Step-by-step procedures. Use imperative verb headings. Always preceded by a concept.
- **Reference**: Fields, parameters, options, error codes. Use tables. Collect with other reference material.

### Article structure

- Open with conceptual context that orients the reader.
- Then move to tasks, then reference material.
- Answer one focused question per page. Not too broad, not too narrow.
- Concept page with child task pages (multi-page), OR H1 concept + H2 task subheadings (single page).
- Introduce synonyms or former names once (e.g., "ECID (Experience Cloud ID)") to connect search terms.

### Steps

- Each step is a single command: a complete sentence with a period (or colon if introducing a sub-list).
- Steps always begin with a verb or the goal before the action: "To run the report, select Run."
- Combine small actions that happen in the same place in the UI into one step when the sentence stays clear.
- Target 7 steps per task; 10 is the practical maximum. Break longer tasks into subtasks.
- Use a single bullet (not `1.`) for a procedure that has only one step.
- Do NOT use headings as steps in product documentation. For long multi-page tutorials, use "Step 1: …" style subheadings when needed.
- Place step info (explanatory text) indented on a new line after the step.
- Place screenshots indented after the step or action that causes the screen to appear.
- Repeat page, tab, or panel names in steps so readers know where they are.

### TOC files (TOC.md)

- Sentence case for all entries (proper nouns and UI elements excepted).
- Concept entries: nouns and noun phrases.
- Task entries: imperative verbs (not gerunds).
- Keep entries parallel.
- Every section heading in the TOC must have a valid anchor ID: `+ Processing rules {#processing-rules}`
- A section heading (parent) in the TOC cannot be a link. It must have an anchor ID.
- Do NOT add the same file multiple times in a TOC.
- Do NOT comment out lines in the middle of a TOC list. Move comments to the end of the file.

### Hiding files from navigation

Use the **V2 method** for all new work. The V1 method is deprecated.

**V2 (current): `{hide-from-toc}` in TOC.md**

Place `{hide-from-toc}` directly in `TOC.md` before the article or section you want to hide. Do NOT add it to the article frontmatter.

```
+ {hide-from-toc} [Article title](filename.md)
+ {hide-from-toc} Section name {#section-id}
  + [Nested article](nested.md)
```

- Hidden articles remain accessible via direct URL.
- A section whose entries are all hidden will itself disappear from the left navigation.

**V1 (deprecated): `hidefromtoc: yes` in frontmatter**

```yaml
hidefromtoc: yes
```

Do NOT use this on new pages. The article must still appear in `TOC.md` to publish, but it will not display in the left navigation.

**Hiding from search engines: `hide: yes` in frontmatter**

```yaml
hide: yes
```

This excludes the page from both external and internal search. Setting `hide: yes` automatically sets `index: no`. Use this in addition to `{hide-from-toc}` when you want a page hidden from both navigation and search.

---

## 5. Terminology and Branding

Authoritative source: [AEP User-Facing Terminology wiki](https://wiki.corp.adobe.com/spaces/DMSArchitecture/pages/1230620427/Adobe+Experience+Platform+User-Facing+Terminology). Always consult via the Confluence MCP tool (`mcp__adobe-wiki-confluence`) for the latest version.

### Product names

Always use these exact forms. Include "Adobe" on first reference in a guide; you may drop it in subsequent mentions where policy allows.

Do NOT precede product names with "the" unless the official name includes it.
- Correct: "Get started with AI Assistant."
- Incorrect: "Get started with the AI Assistant."

| Correct | NEVER use |
|---|---|
| Adobe Experience Platform | AEP, AXP, Adobe XP, Adobe Cloud Platform |
| Experience Platform (secondary reference) | Platform (alone, unless context is unambiguous) |
| Adobe Real-Time CDP | RTCDP, ARTCDP |
| Real-Time CDP (secondary) | Real-time CDP (lowercase "t") |
| Adobe Real-Time Customer Data Platform | — |
| Real-Time Customer Profile | Real-time Customer Profile, Unified Profile |
| Adobe Journey Optimizer | AJO |
| Adobe Journey Optimizer B2B Edition | AJO B2B |
| Adobe Journey Optimizer B2B Prime | AJO B2B Prime |
| Adobe Marketo Optimizer | AMO |
| Adobe Marketo Engage | Marketo (can be used as an adjective) |
| Adobe Customer Journey Analytics | CJA |
| Customer Journey Analytics (secondary) | — |
| Adobe Real-Time CDP Collaboration | RTCDP Collaboration, RTCDP Collab, Collab |
| Adobe Real-Time CDP Connections | RTCDP Connections, AEP Connections, Connections (alone) |
| Adobe Experience Platform Edge Network | Platform Edge Network, Platform Edge, Adobe Experience Edge |
| Tags (product name) | Launch (deprecated) |
| Decision Management | Offer Decisioning (parenthetical only: "formerly Offer Decisioning") |
| datastream (one word, lowercase) | datastreaming, edge configuration |
| Analysis Workspace | analysis workspace, workspace, Workspace |
| Adobe AI | Sensei (deprecated) |
| Adobe GenAI | — |
| Adobe GenStudio for Performance Marketing | — |

**"Real-Time"** always uses capital R and capital T when part of a product name (Real-Time CDP, Real-Time Customer Profile, Real-Time Customer Data Platform).

**Editions**: "editions" is lowercase generically; "Edition" is capitalized as part of a product edition name (e.g., "Adobe Real-Time CDP B2C Edition").

**Abbreviations in external communications**: Do NOT abbreviate product names in user-facing documentation. No AEP, CJA, AJO, or RTCDP in docs. Limited exceptions: acronyms may appear parenthetically on first use when they aid SEO, or in TOC entries, description metadata, and headings where length is a concern.

### Feature and concept terminology

| Correct | Do NOT use |
|---|---|
| event forwarding | server-side forwarding, Launch Server Side |
| allowlist | whitelist |
| denylist / blocklist | blacklist |
| primary / replica OR primary / secondary (servers) | master / slave |
| main (GitHub branch) | master |
| ethical hacker | white hat hacker |
| remarketing | retargeting |
| field group | mixin (deprecated), Extensions, Mixins |
| automatic data expiration | TTL, time-to-live, expiry |
| non-production sandbox | staging (as an environment name) |
| segment definition | segment (alone, when meaning the definition) |
| ID (always capitalize) | Id |
| ingestion / ingest / ingested | onboarding (for adding data to Platform) |
| dataset / datasets | Data File, dataset files |
| access control | permissions (for the Platform feature) |
| widget | metric card (deprecated) |
| placeholder variable | dummy variable |
| unavailable / locked / turned off / deactivated | grayed out |
| coherence check | sanity check |
| built-in | native (as a synonym for built-in) |
| high priority | must nail |
| legacy | grandfather clause |
| primary / main / source | master (as a descriptor) |

**Analytics-specific capitalization:**
- Panel names are lowercase: blank, attribution, experimentation, freeform (exception: "Journey canvas")
- Visualization names are lowercase: bar, donut, histogram, line, tree map, text

### Internal-only terms: NEVER use in public-facing docs

These terms appear in Jira, wikis, and internal discussions but must never appear in documentation:

| Internal term | Use instead |
|---|---|
| AEP | Adobe Experience Platform |
| PALM | sandbox management / access control |
| BIOME | environment |
| Hydrate / hydration | create / populate |
| Unified Profile | Real-Time Customer Profile |
| Staging (environment) | non-production sandbox |
| DTM | Tags |
| Tenant | IMS org / organization |
| CRUD | create, read, update, and delete (spell it out) |
| Siphon, BSO, Ethos | internal code names, never external |
| Hops | internal GDPR/access control term |
| Pacing | non-user-facing advertising term |
| Pipeline | internal Adobe infrastructure term |

---

## 6. Inclusive Language and Accessibility

### Inclusive language principles

- Use gender-neutral terms: "sales representative" not "salesman," "moderator" not "chairman."
- Prefer second person ("you") to avoid gendered pronouns.
- Use singular "they" for a person whose gender is unknown. Do NOT use he/she or (s)he.
- Include names from non-white cultures in examples (e.g., Ayesha, Ibrahim, Vignesh, Quynh). Do NOT use only culturally white names (John, Bill, Karen, Amy).
- Do NOT conflate sex (male/female) with gender (man/woman).
- Capitalize nationalities, peoples, races (other than "white," per AP Stylebook), and tribes.
- Use person-first language: "people who use assistive technology," not "the disabled."
- Avoid euphemisms like "differently abled." Avoid descriptors used as nouns: "the blind," "the deaf."
- Avoid terms that reflect identity (cultural appropriation): spirit animal, Sherpa, pow wow, guru, ninja, tribe.

### Non-inclusive terminology to avoid

| Use | Not |
|---|---|
| allowlist / denylist / blocklist | whitelist / blacklist |
| primary / replica OR primary / secondary | master / slave |
| main (git branch) | master |
| high priority | must nail |
| placeholder variable | dummy variable |
| unavailable / locked / turned off / deactivated | grayed out |
| coherence check | sanity check |
| built-in | native (as a synonym) |
| authority / expert | guru / ninja |
| members of your group | members of your tribe |
| meeting | pow wow / circle the wagons |
| role model / kindred spirit | spirit animal |
| guide | Sherpa |
| legacy | grandfather clause |
| futile undertaking | death march |
| ridiculous / incompetent / unpredictable | dumb / lame / crazy |
| ethical / unethical hacker | white hat / black hat hacker |
| Play video | Watch video |
| View / Show / Go to all | See all |

### Accessibility: describing the UI

Do NOT describe UI elements by color or screen position. Color does not work for colorblind users or screen readers. Screen position is unreliable with assistive technologies.

**Use chronological language, not spatial language:**

| Use | Not |
|---|---|
| First, Next, Finally | Above, Below |
| In the menu bar | On the left |
| Before / After | At the top / bottom of the screen |

**Describe what controls do, not what they look like:**

| Use | Not |
|---|---|
| Select Search | Click the magnifying glass icon |
| Edit | The pencil icon |
| On / Off | Switch / toggle / activate |
| Menu | Side drawer |
| Enter email | Type your email address |
| Save | The "Save" button |
| Cancel | Close |

Do NOT use color alone to convey information. Always pair color with text or shape.

### Accessibility: alt text

- Describe what the image shows, not just its screen name.
- Use complete sentences with proper grammar and punctuation.
- Include relevant text from the image.
- Use full words, not abbreviations. Screen readers spell abbreviations aloud.
- Images that convey information independent of surrounding text MUST have alt text.
- Purely decorative images may omit alt text, but it is good practice to include it.
- Test images with a color-blindness simulator when color is used to convey meaning.
- Do NOT use animated graphics that flash more than three times per second (seizure risk).

### Accessibility: links

- Never use "click here" or "link" as link text.
- Make the destination clear from the link text alone.
  - Good: "See the RTCDP prerequisites in the RTCDP User Guide."
  - Bad: "Click here for prerequisites."

### Accessibility: videos

- Videos must NOT autoplay.
- Always provide a text alternative, transcript, or link to written instructions.
- Include meaningful captions on all videos.
- When possible, link to written instructions: "For written instructions, see [link]."

---

## 7. Spelling and Punctuation

### American English spelling

| Use | Not |
|---|---|
| color | colour |
| recognize | recognise |
| license | licence |
| while | whilst |
| expiration | expiry |
| meter | metre |
| among | amongst |

### Punctuation rules

- Closing quotation marks go outside commas and periods.
- Reserve quotation marks for quoting people. Do not quote UI strings (use UICONTROL and bold in steps).
- Use italics for terms used as terms (not quotation marks): *profile*, not "profile".
- Use backticks for code, parameters, file names, and typed text: `datasetId`.
- Bold: only for UI elements in procedures (with UICONTROL) and key terms at first introduction. Bold lead lines are acceptable in FAQ layouts that do not use heading-level questions.
- Italics: for emphasis, foreign words, terms being defined, or conceptual names in non-step text.
- Bold + italic combined: `***text***`.
- Do NOT use horizontal rules (`---` or `***`). They are not supported in Experience League.
- Do NOT use em dashes (—), en dashes (–), or hyphens in prose. Rephrase the sentence instead. Hyphens are permitted only in compound adjectives that appear in the UI, file names, and code.
- Colons: use to introduce a list. Capitalize the first word after a colon when a full sentence follows (or the word is a proper noun).
- No semi-colons. Use a period and a new sentence instead.

---

## 8. SEO and Findability

- Include search terms (keywords) in first paragraphs.
- Use terms readers actually search for. Include synonyms and previous term names where helpful.
- Keywords in headings: include feature names, interface elements, and the task being performed.
- Alt text on images is indexed by Google. Make it descriptive and meaningful.
- Avoid placing essential terms only in complex tables or images (not reliably indexed by AI or search).
- Description metadata: use natural language with keywords. Do NOT cram random keywords. Google may demote content for keyword stuffing.
- Keep metadata fields (title, description, feature tags) complete and accurate — discovery surfaces use metadata to filter and rank results before reading page content.

---

## 9. File and Repo Conventions

- Frontmatter is required on every `.md` file.
- Images go in an `assets/` subfolder relative to the markdown file.
- Images that must not be localized go in a `do-not-localize/` subfolder.
- TOC files (`TOC.md`) define left-nav structure. Update them when adding or removing pages.
- Use root-relative links (`/help/...`) for cross-references between docs in this repo.
- For links to docs outside this repo, use absolute `https://experienceleague.adobe.com/...` URLs.
- Branch naming: no username prefix. Use the Jira ticket number and a title-cased slug (e.g., `PLAT-12345-Update-Guardrail-Limits`). Name both the branch and PR title using the same format.
- Discrete components (headings, fenced code blocks, lists) must be surrounded by blank lines.
- Only one H1 (`#`) per document. The first line after frontmatter must be the H1.

---

## 10. Review Checklist

When reviewing or editing documentation, verify every item below.

**Voice and style**

- [ ] User-focused voice. No "allows you to," "enables you to"
- [ ] "you" used instead of "users" when addressing the audience directly
- [ ] Second person and imperative mood in procedures
- [ ] Active voice throughout
- [ ] Sentences target ≤20 words
- [ ] No vague adjectives ("fast," "easy"). Replace with precise descriptions.
- [ ] Key terms appear in body text (not only in images or tables) for AI discovery

**Structure and headings**
- [ ] Headings: sentence case, ≤5 words / 69 chars, followed by body text, no stacked headings
- [ ] No skipped heading levels
- [ ] Concept headings are noun phrases; task headings are imperative verbs
- [ ] Target 7 steps per task; max 10. Single-step procedures use a bullet, not `1.`
- [ ] Max 8 items per bulleted list

**Terminology**
- [ ] Correct product names and forms (Section 5)
- [ ] No deprecated terms: mixin, TTL, Offer Decisioning, Launch, Unified Profile, Real-time (lowercase t), Sensei
- [ ] No internal-only terms: AEP, PALM, BIOME, hydrate, staging, DTM, tenant, pipeline
- [ ] No non-inclusive terms: whitelist, blacklist, master/slave, sanity check, dummy, grayed out, native, guru, ninja, spirit animal, Sherpa, death march, pow wow, tribe
- [ ] No "the" before product names (e.g., not "the Adobe Experience Platform")

**Localization tags**
- [ ] `[!UICONTROL]` on all UI element names; bold in steps
- [ ] `[!DNL]` on all product and third-party names
- [ ] Boolean operators tagged: `[!DNL AND]`, `[!DNL OR]`
- [ ] No tags inside code blocks
- [ ] Metadata fields beginning with a tag are wrapped in quotation marks

**Markdown syntax**
- [ ] Correct admonition syntax (blank `>` line between tag and content)
- [ ] Lists use consistent markers; numbered lists use `1.` for every item
- [ ] No task lists (`- [ ]`)
- [ ] No horizontal rules (`---` between content)
- [ ] Blank lines surrounding headings, code blocks, lists, and tables
- [ ] No images of code. Use code blocks.
- [ ] Screenshots use Light theme; no customer data; no third-party UI

**Accessibility**
- [ ] Alt text: complete sentences, full words, describes content (not just the screen name)
- [ ] No directional/spatial language: no "above," "below," "on the left," "at the top right"
- [ ] Link text describes destination. No "click here"
- [ ] Videos not set to autoplay; transcripts or written alternatives provided
- [ ] No color used alone to convey information

**Files and links**

- [ ] Required frontmatter: title (title case, ≤60 chars), description (150 to 160 chars)
- [ ] No bare URLs in body text. Always use descriptive link text.
- [ ] Root-relative internal links; absolute links for cross-repo references
- [ ] File names are lowercase with hyphens; descriptive slugs (not bare `overview.md`)
- [ ] Images in `assets/`; non-localized images in `do-not-localize/`

---

## 11. External References

Use the correct MCP tool based on the resource type:

- **Jira tickets and issues** (`jira.corp.adobe.com`): use the Corp Jira MCP tool (`mcp__corp-jira`)
- **Wiki / Confluence pages** (`wiki.corp.adobe.com`): use the Confluence MCP tool (`mcp__adobe-wiki-confluence`)
- **Public Experience League / web pages**: use WebFetch

**Internal wiki pages (use Confluence MCP tool):**
- **Terminology wiki**: https://wiki.corp.adobe.com/spaces/DMSArchitecture/pages/1230620427/Adobe+Experience+Platform+User-Facing+Terminology
- **Platform style guide**: https://wiki.corp.adobe.com/spaces/DMSArchitecture/pages/1938986972/Platform+style+guide
- **Accessibility and inclusivity guide**: https://wiki.corp.adobe.com/spaces/DMSArchitecture/pages/2234798784/Writing+for+accessibility+and+inclusivity
- **Contextual help popovers guide**: https://wiki.corp.adobe.com/spaces/DMSArchitecture/pages/2575057078/How+to+add+contextual+help+popovers+to+the+Experience+Platform+documentation+and+UI

**Public (use WebFetch):**
- **Localization overview**: https://experienceleague.adobe.com/en/docs/authoring-guide/using/authoring/localization/localization-overview
- **Localization tags reference**: https://experienceleague.adobe.com/en/docs/authoring-guide/using/authoring/localization/localize
- **Experience League markdown syntax**: https://experienceleague.adobe.com/en/docs/authoring-guide/using/markdown/markdown-syntax
- **Markdown cheatsheet**: https://experienceleague.adobe.com/en/docs/authoring-guide/using/markdown/cheatsheet
- **Release notes style reference**: https://experienceleague.adobe.com/en/docs/experience-platform/release-notes/latest

**Local clone:**
- **Authoring guide repo:** Use an available checkout of the Adobe Experience League authoring guide or its public documentation.
