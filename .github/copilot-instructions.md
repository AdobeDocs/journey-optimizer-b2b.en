# GitHub Copilot repository instructions

When general guidance in the copied Claude instructions conflicts with repository-specific conventions or task-specific instructions, follow the repository-specific or task-specific instruction.

## Purpose

Use these repository instructions for documentation work in this repo. Keep edits concise, technically accurate, and aligned to Adobe Experience League documentation standards.

## Write in the repo’s documentation style

- Prefer clear, direct, user-focused language.
- Keep sentences short and scannable.
- Prefer specific, actionable language over marketing or filler text.
- Avoid boilerplate sections such as "Related topics," "FAQs," or generic summary blocks unless they are explicitly required.
- Use in-context cross-links instead of end-of-page navigation blocks.
- Do not add a references list or a "Related topics" section at the end of an article. Introduce related links where they are relevant in the content, and explain how each destination relates to the current topic.
- Do not use spatial language such as "below" or "above" to describe document order; use "following," "previous," or "in the next section" instead.

## External documentation naming rules

- Do not use Adobe product acronyms in external documentation.
- First mention of Adobe product names must use the full product name, including "Adobe" when appropriate.
- Use DNL tags for product names in content, for example:
  - [!DNL Adobe Experience Platform]
  - [!DNL Adobe Journey Optimizer B2B Edition]
  - [!DNL Experience Platform]
  - [!DNL Journey Optimizer B2B Edition]
- Replace acronym-only references such as "AEP" and "AJO B2B" with their full product names in user-facing documentation.
- When a product is introduced for the first time, write the full name. Later mentions can use the shorter product name without the acronym, and keep the DNL tag when the product name appears in UI or docs text.
- Apply these terms consistently across the page title, first paragraph, and any labels or cross-links that are visible to readers.

## Repository-specific naming conventions

- Use "Adobe Journey Optimizer B2B Edition" for the product name in user-facing docs.
- Use "Adobe Experience Platform" for the platform name in user-facing docs.
- Use the product name in its full form on the first mention and then keep later references short and consistent.
- For dataset references, preserve the actual dataset names and IDs exactly as they appear in the source contract, even when they include legacy prefixes such as `AJOB2B-`.

## Markdown and formatting guidance

- Write valid GitHub-flavored Markdown.
- Keep headings concise and descriptive.
- Use tables only when they help readers scan technical details.
- Use relative links for repo-local references.
- Keep code blocks and field paths exact and copyable.
- Avoid redundant product references in headings if the page title already states them.

## Validation checklist before finishing

- Ensure there are no acronyms for Adobe products in user-facing content.
- Ensure first mentions use the full product name.
- Ensure product names are tagged with [!DNL ...] where required by the repo style.
- Ensure the doc avoids boilerplate and spatial wording issues.
- Ensure the technical content remains accurate and the in-context cross-links are preserved.
