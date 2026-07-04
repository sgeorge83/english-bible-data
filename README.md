# World English Bible data (web)

**Raw base URL:** `https://raw.githubusercontent.com/sgeorge83/english-bible-data/main`

## About

This repository hosts the **World English Bible** (WEB) as structured JSON files for use by apps, websites, and bilingual Bible projects (paired with [Urdu Geo Version data](https://github.com/sgeorge83/urdu-bible-data)).

**Contents**

- `metadata.json` — translation info, license
- `books.json` — 66 books with English names and chapter counts
- `chapters/{book}/{chapter}.json` — 1,189 chapter files (31,103 verses total)

**Translation:** World English Bible (`web`), 2006  
**Script:** English (LTR)  
**Format:** Split from Bible SuperSearch JSON; text and punctuation unchanged

## Structure

```text
english-bible-data/
├── README.md
├── metadata.json
├── books.json
└── chapters/
    ├── 1/                 # Genesis (50 chapters)
    │   ├── 1.json
    │   └── ...
    ├── 40/                # Matthew
    └── 66/                # Revelation (22 chapters)
```

### Example URLs

```text
https://raw.githubusercontent.com/sgeorge83/english-bible-data/main/metadata.json
https://raw.githubusercontent.com/sgeorge83/english-bible-data/main/books.json
https://raw.githubusercontent.com/sgeorge83/english-bible-data/main/chapters/1/1.json
https://raw.githubusercontent.com/sgeorge83/english-bible-data/main/chapters/43/3.json
```

### Chapter file format

```json
{
  "book": 43,
  "book_name": "John",
  "chapter": 3,
  "verse_count": 36,
  "verses": [
    {
      "book_name": "John",
      "book": 43,
      "chapter": 3,
      "verse": 16,
      "text": "For God so loved the world, that he gave his one and only Son, that whoever believes in him should not perish, but have eternal life."
    }
  ]
}
```

### Parallel reading with Urdu Geo

Books use numeric IDs **1–66** (Genesis → Revelation), matching [urdu-bible-data](https://github.com/sgeorge83/urdu-bible-data). Join on `book`, `chapter`, and `verse`. Some chapters may differ in verse count between translations due to versification; spot-check critical passages when building UI.

## License

The World English Bible is **Public Domain**. You may freely copy, share, and use this text in any format, including commercial use.

See `metadata.json` for the full copyright statement from Bible SuperSearch.

## Source

World English Bible (`web`), reformatted for Bible SuperSearch. Split with [urdu-bible-api/scripts/split_bible.py](https://github.com/sgeorge83/urdu-bible-api). No changes were made to the text or punctuation.
