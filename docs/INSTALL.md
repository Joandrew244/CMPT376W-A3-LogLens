# Install and run LogLens

This guide walks you through downloading LogLens, running it on the included sample file, and then running it on your own CSV file. It assumes you understand basic CSV files and have used a terminal before.

For an overview of what LogLens does, see the [README](../README.md).

## Before you begin

You need:

- **Python 3.10 or newer.** No other package are required, and you do not need `pip`.
- **A terminal.**
- **For step 4 only:** your own CSV log file with the collumns `timestamp`, `level`, and `message`. See [Input format](../README.md#input-format) in the README.

To check your Python version, run:

```bash
python --version
```

The number shown should be 3.10 or higher.

> [!NOTE]
> LogLens runs entirely on your computer. It does not need a network connection and does not upload your data.

## 1. Get the files

1. Open this repository's page on GitHub.
2. Select **Code**, then **Download ZIP**.
3. Extract (unzip) the downloaded file.
4. Open the extracted folder and find the folder that directly contains `loglens.py`.
   This is the **repository root**. It also contains `README.md` and the `data` and `docs` folders.

You do not need to install anything else. LogLens runs directly as `loglens.py`.

## 2. Open a terminal in the repository root

1. Open a terminal.
2. Move into the repository root, replacing the path with the location of your extracted folder:

   ```bash
   cd path/to/repository-root
   ```

3. Confirm you are in the right folder by running:

   ```bash
   python loglens.py --help
   ```

   If you see a list of options starting with `usage: loglens.py`, you are in the repository root.

## 3. Run LogLens on the sample file

From the repository root, count the `ERROR` records in the included sample file:

```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```

Expected output:

```text
Records matching ERROR: 2
```

To count all records instead, leave out `--level`:

```bash
python loglens.py --file data/sample_logs.csv
```

Expected output:

```text
Records matching ALL: 6
```

If your output matches, LogLens is working.

## 4. Run LogLens on your own file

Replace `path/to/your-log.csv` with the path to your file:

```bash
python loglens.py --file path/to/your-log.csv --level WARN
```

- `--level` accepts `INFO`, `WARN`, or `ERROR`, in uppercase only. Leave it out to count all records.
- Your file must have the columns `timestamp`, `level`, and `message`. See [Input format](../README.md#input-format).
- LogLens only reads your file. It does not change it.

## Troubleshooting

Find the message you see in the left column.

| Message or problem | Likely cause | Fix |
| --- | --- | --- |
| `python` is not recognized or not found | Your computer uses a different Python command | Try `python3` or `py` instead of `python`. |
| `the following arguments are required: --file` | The command is missing `--file` | Add `--file` followed by the path to your CSV file. |
| `File not found: ...` | The path is wrong, or you are not in the repository root | Check the path. Run the command from the folder that contains `loglens.py` (see [step 2](#2-open-a-terminal-in-the-repository-root)). |
| `invalid choice: 'error'` | The level is not in uppercase | Use `INFO`, `WARN`, or `ERROR` in uppercase. |
| `CSV must contain timestamp, level, and message columns` | The file's header row uses different column names | Rename the columns to exactly `timestamp`, `level`, and `message`. |

If none of these solve the problem, see [Getting help](../README.md#getting-help) in the README.

> [!WARNING]
> Do not post your full log file in a public issue. Logs can contain private or sensitive information. Describe the problem and share only a small sanitized example with private details removed.
