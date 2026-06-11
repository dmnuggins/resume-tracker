# Resume Tracker

A Git-based system for managing resume variants and job applications.

## Directory Layout

```
resume-tracker/
├── base/                      # Master resume source (Word doc)
├── variants/                  # Role-specific resume versions
│   ├── sysadmin/
│   ├── network-admin/
│   └── it-project-manager/
├── master/
│   └── career_inventory.md    # Granular experience source — never submitted
├── applications/
│   └── applications.md        # Application tracker
└── exports/                   # Generated PDFs (gitignored by default)
```

## Workflow

### Source files

- **`base/`** — holds the master resume `.docx`. Copy it into a variant folder when starting a new tailored version.
- **`master/career_inventory.md`** — the canonical experience source. Never submitted. Pull from it when drafting or refining variants. Add new achievements here as they happen.
- **`variants/<role>/`** — each role type gets its own subfolder. Keep the tailored `.docx` (and any notes) here.
- **`exports/`** — drop generated PDFs here before sending. Ignored by git unless you tag the snapshot (see below).

### Tracking applications

Log every application in `applications/applications.md`. Update the Status column as things progress.

### Snapshotting a submission

Before submitting, tag the exact state of the files you're sending:

```bash
git add .
git commit -m "apply: <Company> — <Role>"
git tag application/<company>-<role>-<YYYY-MM-DD>
```

To recover exactly what you submitted:

```bash
git checkout application/acme-sysadmin-2026-06-01
```

Tags are lightweight and permanent — use them liberally.
