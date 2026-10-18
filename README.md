# Pustaka Terbuka — USM (Universiti Sains Malaysia)

> **Pustaka Terbuka: Katalog Induk Terbuka untuk Perpustakaan dan Sekolah Malaysia.**  
> *Official Perpustakaan Hamzah Sendut (Universiti Sains Malaysia) (USM) Bibliographic Dataset & Standalone Harvester.*

This repository contains the harvested open MARCXML collection and harvester pipeline for **Perpustakaan Hamzah Sendut (Universiti Sains Malaysia)** (`USM`), contributing to the national Malaysian union catalog at [pustaka-terbuka/opac](https://github.com/pustaka-terbuka/opac).

---

## Institutional Metadata

| Attribute | Value |
| :--- | :--- |
| **Institution Code** | `usm` |
| **Agency Code** | `USM` |
| **Official Name** | Perpustakaan Hamzah Sendut (Universiti Sains Malaysia) |
| **Institution Type** | `university` |
| **State / Territory** | Pulau Pinang |
| **Classification Scheme** | `LCC` |
| **OPAC Base URL** | [https://lib.usm.my/](https://lib.usm.my/) |
| **Platform / Engine** | `koha` |
| **Default Branch** | Perpustakaan Hamzah Sendut (Gelugor) |

---

## Directory Structure

```text
usm/
├── README.md                      # Institutional repository documentation
├── package.json                   # Node.js project specification & scripts
├── harvest/
│   └── inbox/usm/             # Sealed MARCXML batch chunks and manifests
│       └── <run-id>-chunk-001/
│           ├── manifest.json      # Chunk SHA-256 manifest & metadata
│           ├── provenance.jsonl   # Record-level attribution and fetch logs
│           └── records/           # Batched MARC21 slim XML files
├── tools/
│   ├── harvesters/usm/        # Automated OPAC crawler & MARC21 converter
│   ├── lib/                       # Supporting MARCXML, LCC, and validation utilities
│   ├── schemas/                   # JSON schemas for manifests and provenance
│   ├── validate-inbox.js          # Dataset integrity and schema validator
│   ├── merge.js                   # Local catalog merge engine
│   └── ingest-to-master.js        # Safe master ingestion bridge into pustaka-terbuka/opac
└── tests/
    └── harvester-usm.test.js  # Autonomous test suite
```

---

## Usage

```bash
# Install dependencies
npm install

# Test run harvester (10 sample records)
npm run harvest:sample

# Run harvester with chunking
npm run harvest:chunked

# Validate dataset integrity
npm run validate-inbox harvest/inbox/usm/<chunk-directory>

# Ingest new harvested batches into the central OPAC union catalog
npm run ingest:master
```

---

## Attribution & License

Dataset harvested and preserved under open library metadata standards for educational, civic, and cooperative indexing. Attribution: **Perpustakaan Hamzah Sendut (Universiti Sains Malaysia) (USM)** & **Pustaka Terbuka**.
