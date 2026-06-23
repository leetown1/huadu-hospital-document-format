---
name: huadu-hospital-document-format
description: Apply and verify the 2023 Guangzhou Huadu District People's Hospital document formatting standard. Use when a user provides a Word, DOCX, PDF, or text draft and asks to standardize it to "广州市花都区人民医院文书格式要求（2023年版）", including page setup, typography, headings, paragraph spacing, page numbers, signatures, tables, attachments, and rendered layout validation.
---

# 广州市花都区人民医院文书格式规范

Use this skill to convert a supplied document into the format required by `广州市花都区人民医院文书格式要求（2023年版）`. Preserve the user's substantive content unless the format standard explicitly requires normalization, such as title wording, department/date placement, hierarchy numbering, attachment labels, and date style.

This standard applies to documents written by functional departments and clinical/business departments. It does not apply to institutional policy documents, which must follow the hospital's separate policy-document standard.

## Workflow

1. Read the input file and identify document type.
   - For `.docx`, inspect sections, styles, paragraphs, runs, tables, headers, footers, and page setup.
   - For `.pdf`, extract text for content and render pages to images for layout review; do not rely on text extraction alone.
   - For plain text or copied content, create a `.docx` unless the user requests another output format.
2. Preserve and structure content.
   - Identify title, body, hierarchy headings, tables, attachments, signature block, and date.
   - Do not rewrite business meaning. Only normalize formatting, numbering, date expression, and required labels.
3. Apply the complete format standard below.
4. Validate with both programmatic inspection and visual rendering.
   - Inspect DOCX styles/page setup with a document library or OOXML.
   - Export/render to PDF or page images when available, then review margins, alignment, page numbers, line spacing, table placement, and orphaned signature blocks.
5. Report any unresolved issue, such as missing fonts, ambiguous heading levels, or content that cannot fit the required signature spacing without user judgment.

## Required Format

### Paper And Scope

- Use international standard A4 paper: `210 mm x 297 mm`.
- Compose ordinary documents from title, body content, and signature/date block.
- Do not use this standard for hospital policy/institutional system documents.

### Title, Body, And Signature Placement

- Main title: standardize to `广州市花都区人民医院XXX` when the document is a normal hospital document.
- Signature: standardize department signature to `广州市花都区人民医院XX科` and date to `YYYY年M月D日`.
- Place the main body one blank line below the main title.
- Place the signature block three blank lines below the body or attachment description.
- Keep the signature block on the same page as the body. Do not put the signature alone on a separate page.
- If three blank lines after the body would force the signature onto a new page, adjust body fixed line spacing within the allowed range before reducing required structure.
- Align the department signature right with a two-character right indent.
- Align the date by moving it two Chinese characters to the right based on the first character of the department signature.

### Fonts

- Main title: `方正小标宋简体`, Chinese size `二号` (`22 pt`), not bold, centered.
- First-level heading: `黑体`, Chinese size `三号` (`16 pt`), not bold.
- Second-level heading: `楷体_GB2312`, Chinese size `三号` (`16 pt`).
- Third- and fourth-level headings: `仿宋_GB2312`, Chinese size `三号` (`16 pt`), may be bold for emphasis.
- Body Chinese text: `仿宋_GB2312`, Chinese size `三号` (`16 pt`).
- Table Chinese text: `仿宋_GB2312`, Chinese size `三号` (`16 pt`) by default; adjust only when table density requires it.
- English text: `Times New Roman`.
- Signature and date: `仿宋_GB2312`, Chinese size `三号` (`16 pt`).
- Directory/table-of-contents text: generally Chinese size `小四` (`12 pt`), adjustable for special cases.
- Page numbers: `宋体`, Chinese size `四号` (`14 pt`).
- Font color: black for all document text.
- If required Chinese fonts are not installed, still set the font names in the DOCX styles/runs and report the font availability risk.

### Date Style

- Use Arabic numerals for all dates.
- Write full year/month/day, such as `2023年10月23日`.
- Do not abbreviate years, such as writing `23年` for `2023年`.
- Do not add leading zeroes to month or day; write `2023年1月5日`, not `2023年01月05日`.

### Hierarchy Numbering

- First level: Chinese numeral plus dunhao, such as `一、`, `二、`, `三、`.
- Second level: Chinese numeral in full-width parentheses, such as `（一）`, `（二）`, `（三）`.
- Third level: Arabic numeral plus period, such as `1.`, `2.`, `3.`.
- Fourth level: Arabic numeral in full-width parentheses, such as `（1）`, `（2）`, `（3）`.
- Normally use no more than four hierarchy levels.
- Do not add punctuation after a first-level heading.
- Add punctuation after second-level and lower headings when the heading continues as sentence text.
- Hierarchy levels may skip levels when the structure is simple. If the document has only two levels, use `一、` for the first level and either `（一）` or `1.` for the second level.

### Table Of Contents

- Put the table of contents on a separate page.
- Use `小四` (`12 pt`) by default; adjust only for special cases.
- Use bold `黑体` for each chapter title.
- Use `宋体` for each section title.
- Right-align page numbers.

### Paragraphs And Line Spacing

- Main title line spacing: fixed `32 pt`.
- Body line spacing: fixed `28-30 pt`, adjusted according to content fit.
- First-line indent: `2` Chinese characters for body paragraphs.
- Paragraph spacing before and after: `0` lines.
- Use the same body formatting for attachment body content.

### Margins

- Portrait pages: top `3.7 cm`, bottom `3.5 cm`, left `2.8 cm`, right `2.6 cm`.
- Landscape pages: top `2.8 cm`, bottom `2.8 cm`, left `3.5 cm`, right `3.5 cm`.
- Binding line position: left.
- Binding gutter width: `0 cm`.
- Physical binding expectation: two staples on the left side.

### Page Numbers

- Insert Arabic numeral page numbers.
- Use `宋体` `四号` (`14 pt`).
- Put a horizontal one-character dash on each side of the number, for example `- 3 -`.
- Odd page numbers: align right, leaving one Chinese character of right-side space.
- Even page numbers: align left, leaving one Chinese character of left-side space.

### Tables

- Table text: `仿宋_GB2312`, `三号` (`16 pt`) unless density requires adjustment.
- Table alignment: centered.
- Text wrapping: none.
- Keep table content legible after any size adjustment.

### Attachments

- If attachments exist, place an attachment description one blank line below the body, with a two-character left indent.
- Use `仿宋_GB2312`, `三号` (`16 pt`) for the attachment description.
- Label as `附件` followed by a full-width colon and the attachment name, such as `附件：XXXX`.
- If there are multiple attachments, use Arabic numerals for attachment order, such as `附件：1.XXXX`.
- Do not add punctuation after an attachment name.
- If an attachment name wraps to a new line, align the wrapped line with the first character of the attachment name on the previous line.
- In the body, when referencing attachment content, add a parenthetical note such as `（见附件）` or `（附后）`.
- Attachment sequence numbers and titles must exactly match the attachment description.
- Put attachment content on a new page. Do not place attachment content on the same page as the body.
- Format attachment content the same as body content.

## DOCX Implementation Guidance

- Prefer editing styles for document-wide rules, then fix direct formatting only where needed.
- Set the Normal/body style to `仿宋_GB2312`, `16 pt`, black, fixed `28-30 pt` line spacing, first-line indent `2` characters, and no before/after spacing.
- Create or update explicit styles for main title, heading levels 1-4, table text, TOC entries, and signature/date.
- Apply section-level page setup for orientation-specific margins.
- For mixed Chinese/English runs, set East Asian font to the required Chinese font and ASCII/HAnsi font to `Times New Roman`.
- For page numbers, use different odd/even footers when possible so odd pages right-align and even pages left-align.
- After formatting, save a new file rather than overwriting the original unless the user explicitly asks to overwrite.

## Validation Checklist

Run these checks before delivering:

- Confirm page size is A4.
- Confirm portrait and landscape margins match the required centimeter values.
- Confirm all required font families, sizes, and black color are assigned.
- Confirm main title is centered, `22 pt`, not bold, and followed by one blank line.
- Confirm body paragraphs use `16 pt` 仿宋_GB2312, fixed `28-30 pt` line spacing, first-line indent `2` characters, and `0` before/after spacing.
- Confirm hierarchy numbering uses the allowed patterns and no more than four levels.
- Confirm first-level headings have no trailing punctuation and lower-level heading punctuation is handled consistently.
- Confirm dates use full Arabic numerals without leading zeroes.
- Confirm tables are centered, readable, and not text-wrapped.
- Confirm page numbers render as `- n -`, use `宋体` `14 pt`, and alternate odd/even alignment.
- Confirm signature/date block is not orphaned on a separate page and follows the three-blank-line rule.
- Confirm attachments are described, numbered, referenced, matched, and started on a new page when present.
- Render the final document to PDF or page images and visually inspect at least the first page, one middle page, and the final page.
