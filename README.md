# Daily Scan

> Turn phone photos of documents into searchable PDFs with OCR.

Daily Scan converts photographed documents into searchable PDFs with OCR in Korean and English. It supports single-page and multi-page scanning, with stable filenames based on capture date and headline text.

## Features

- **Single-page scan** — one photo → one searchable PDF
- **Multi-page scan** — combine multiple photos into one PDF
- **OCR** — Korean and English text recognition
- **Image enhancement** — straighten, crop, and improve contrast for readability
- **Smart naming** — `YYYY-MM-DD + headline text` from OCR
- **Retrieval** — search saved scans by date, headline, or keywords
- **Local storage** — year/month folder structure (`daily-scan-storage/YYYY-MM`)

## Trigger Words

| Korean | English | Action |
|--------|---------|--------|
| `스캔` | `scan` | Single-page scan |
| `스캔연속` | `scan multi` | Multi-page combined PDF |
| `스캔찾아` | `scan find` | Search saved scans |

## Workflow

1. Send document photo(s) with a trigger word
2. Image is cleaned up (straightened, cropped, contrast enhanced)
3. OCR extracts text in Korean and English
4. Searchable PDF is generated with smart filename
5. Original photo and PDF are saved together
6. Report: filename, location, and extracted title

## Help Wanted

The scanning engine still needs significant improvement. Contributions are welcome, especially around:

- OCR accuracy improvements
- Image preprocessing pipelines
- Multi-page handling robustness

## License

MIT-0 — MIT No Attribution
