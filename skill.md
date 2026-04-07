---
name: daily-scan
description: Scan photographed documents into searchable PDFs with OCR and stable file naming. Use when the user sends one or more document photos and asks to scan, save, archive, OCR, preserve paperwork, or retrieve previously scanned files. Trigger words: `스캔` or `scan` for a single page, `스캔연속` or `scan multi` for a multi-page combined PDF, and `스캔찾아` or `scan find` for retrieval.
---

# Daily Scan

## Overview

Turn phone photos of documents into searchable PDFs with OCR and stable filenames based on capture date and headline text. Preserve the original photo, generate a readable scan-like PDF, and support later retrieval of saved scan files.

## Workflow

1. Confirm the trigger.
   - `스캔` / `scan` — one-page processing.
   - `스캔연속` / `scan multi` — combine multiple photos into one searchable PDF.
   - `스캔찾아` / `scan find` — search previously saved scan files.
2. Collect the attached image files or search keywords.
3. Apply document-style scan cleanup when possible.
   - straighten and crop to the page
   - improve contrast for readability
   - keep the output practical rather than over-processed
4. Run OCR in Korean and English.
5. Build the filename as:
   - `YYYY-MM-DD + headline text`
   - derive headline text from the top 2 to 3 OCR lines
6. Create a searchable PDF.
7. Save the output to the configured storage destination.
8. Keep the original image together with the saved output.
9. For retrieval requests, search by date, headline text, or OCR keyword in the configured scan storage path.
10. Report back with:
    - filename
    - save location
    - OCR title line

## Operating Rules

- Use `daily-scan-storage/YYYY-MM` as the default local staging/search path.
- Treat cloud upload as optional integration, not a required dependency.
- Use year/month folder structure.
- Do not auto-classify document types.
- For multi-page capture, combine pages into one PDF only when the trigger is `스캔연속` or `scan multi`.
- OCR language defaults to Korean plus English.
- Retrieval requests should search existing saved scan outputs before asking follow-up questions.
- Keep replies concise.

## Failure Handling

- If OCR fails, still save the PDF when possible.
- If headline extraction fails, ask the user what title to use.
- If OCR fails, explicitly report that OCR failed.
- Preserve the original image unless the user later asks otherwise.

## Output Contract

Return only the practical result:
- saved filename
- save location
- extracted title line when available

## Resources

### scripts/
Use scripts for deterministic image cleanup, OCR execution, searchable PDF generation, and saved scan retrieval.

### references/
Store implementation notes for OCR engine choice, Drive upload path rules, and filename normalization if the skill grows more complex.
