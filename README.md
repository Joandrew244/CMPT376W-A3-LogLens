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

## Input format

The input should be a CSV file. Log files tend to have fields describing the time and what happened, but LogLens is flexible and will work with whatever columns your monitoring system uses. A small example is included somewhere in this repository.

## Questions

If something doesn't work, just contact the developers or create an issue. Make sure you describe the problem so somebody can help. This is a basic tool, so the instructions should be pretty obvious.
