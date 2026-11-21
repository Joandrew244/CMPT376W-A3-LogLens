# LogLens

LogLens is a command-line Python script that counts the records in a CSV log file by log level (`INFO`, `WARN`, or `ERROR`).

## Who this guide is for

This guide is for computing students and new technical interns who:

- understand basic CSV files
- have used a terminal before
- have **not** used LogLens before

You do not need to know this repository's structure or commands. For full setup steps, see the [installation and usage guide](docs/INSTALL.md).

## What LogLens does

- **Counts records.** It reads a CSV log file and prints how many records match one log level, or how many records there are in total.
- **Runs locally.** It does not upload, transmit, or store your data outside your computer.
- **Leaves your file unchanged.** It reads the CSV but does not repair, rewrite, or modify it.
- **Does not diagnose problems.** It counts records by level; it does not explain why a system failed.

## Requirements

- **Python 3.10 or newer**
- **No extra packages.** Loglens uses only the Python standard library, so you do not need `pip install`.
- **A copy of this repository** on your computer (see [Get the files](docs/INSTALL.md#1-get-the-files))

## Quick Start

1. Open terminal in the **repository root**: the folder that contains `loglens.py`.
2. Run LogLens on the included sample file:

   ```bash
   python loglens.py --file data/sample_logs.csv --level ERROR
   ```
   
3. Check the output. You should see:

   ``` text
   Records matching ERROR: 2
   ```

> [!NOTE]
> On some computers, the Python command is `python3` or `py` instead of `python`.

For step-by-step instructions, including how to download the files, see the [installation and usage guide](docs/INSTALL.md).

## Command options

| Option | Required? | What it does |
| --- | --- | --- |
| `--file PATH` | Yes | Path to the CSV log file to read. |
| `--level LEVEL` | No | Counts only records with this level: `INFO`, `WARN`, or `ERROR` (uppercase). If omitted, LogLens counts all records. |
| `--help` | No | Lists the valid options. |

To count every record in the sample file, leave out `--level`:

```bash
python loglens.py --file data/sample_logs.csv
```

```text
Records matching ALL: 6
```

## Input format

Your CSV file needs a header row with these three column names, spelled exactly as shown:

| Column | Contains |
| --- | --- |
| `timestamp` | When the event happened |
| `level` | The log level: `INFO`, `WARN`, or `ERROR` (uppercase) |
| `message` | A short description of the event |

The included sample file, [`data/sample_logs.csv`](data/sample_logs.csv), starts like this:

```csv
timestamp,level,message
2026-01-03T09:00:00Z,INFO,Startup complete
2026-01-03T09:05:00Z,WARN, Memory usage high
2026-01-03T09:10:00Z,ERROR,Connection lost
```

## Questions

1. Check [Troubleshooting](docs/INSTALL.md#troubleshooting) in the installation guide.
2. If the problem continues, open the issue in this repository. Include:
   - the exact command u ran
   - the full error message
   - your Python version (run `python --version`)
  
> [!WARNING]
> Do not post private or sensitive log data publicly. Describe the problem and, if needed, share a small sanitized example: a few rows with any private details removed or replaced.
