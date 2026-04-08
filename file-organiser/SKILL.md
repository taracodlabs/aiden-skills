---
name: file-organiser
description: Scan a folder, classify files by type, project, or date, rename generically-named files based on content, and sort into a clean folder structure. Use when the user asks to organise files, clean up a folder, or sort their downloads.
---

# File Organiser

Scan, classify, rename, and sort files into a clean folder structure.

## When to Use This Skill

- User says "organise my downloads" or "clean up this folder"
- User has a messy directory with mixed file types
- User wants files sorted by type, date, project, or content
- User says "rename these files" or "sort these files"

## Process

### Step 1: Scan

List all files in the target directory:
```bash
# List with sizes and dates
ls -la [folder]        # Linux/Mac
Get-ChildItem [folder] -Recurse | Select-Object Name, Length, LastWriteTime  # Windows
```

Count by extension:
```
.pdf: 23 files
.docx: 8 files  
.png/.jpg: 45 files
.xlsx: 3 files
.py/.js/.ts: 12 files
Other: 7 files
Total: 98 files
```

### Step 2: Classify

Assign each file to a category:

| Category | Extensions |
|----------|-----------|
| Documents | .pdf, .docx, .doc, .txt, .md, .odt, .rtf |
| Spreadsheets | .xlsx, .xls, .csv, .tsv |
| Images | .png, .jpg, .jpeg, .gif, .svg, .webp, .bmp |
| Videos | .mp4, .mov, .avi, .mkv, .webm |
| Audio | .mp3, .wav, .flac, .aac, .ogg |
| Code | .py, .js, .ts, .html, .css, .json, .yaml |
| Archives | .zip, .tar, .gz, .rar, .7z |
| Presentations | .pptx, .ppt, .key |
| Installers | .exe, .msi, .dmg, .deb, .AppImage |

### Step 3: Smart Rename (optional)

For files with generic names (IMG_20240315, Screenshot 2024, document(1)):

1. **Images**: Rename based on date taken (from EXIF if available) or file date
2. **Screenshots**: `screenshot-YYYY-MM-DD-HHMMSS`
3. **Documents**: Read first line/title and use that (e.g., "Q3-Budget-Report.pdf")
4. **Downloads with (1)(2)**: Remove duplicate suffixes, keep latest

Ask user before renaming: "I found 23 generically named files. Want me to rename them based on content/date?"

### Step 4: Create Folder Structure

```
[Target Folder]/
├── Documents/
│   ├── PDFs/
│   ├── Word/
│   └── Text/
├── Images/
│   ├── Screenshots/
│   └── Photos/
├── Code/
├── Spreadsheets/
├── Videos/
├── Audio/
├── Archives/
├── Installers/
└── _Unsorted/          # Anything that doesn't fit
```

### Step 5: Move Files

Move each file to its category folder. Log every move:

```
✅ Budget-Q3.pdf → Documents/PDFs/Budget-Q3.pdf
✅ IMG_20240315.jpg → Images/Photos/2024-03-15-photo.jpg
✅ app.py → Code/app.py
⚠️ mystery-file.dat → _Unsorted/mystery-file.dat
```

### Step 6: Report

```
📁 Organisation Complete!

98 files processed:
  23 → Documents/
  45 → Images/ (12 renamed)
  12 → Code/
  8 → Spreadsheets/
  3 → Videos/
  7 → _Unsorted/

No files deleted. Duplicates moved to _Unsorted/ for manual review.
```

## Safety Rules

- **NEVER delete files** — only move and rename
- **Always ask before renaming** — show the proposed renames first
- **Keep a move log** — save to `[folder]/_organisation-log.txt`
- **Don't touch hidden files** (.gitignore, .env, etc.) unless explicitly asked
- **Preserve file dates** — use copy-then-verify-then-delete instead of move if the OS doesn't preserve metadata
- **Duplicates**: Move to `_Duplicates/` subfolder, don't delete
