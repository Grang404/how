# how
___

Personal scratchpad for commands I kept forgetting. Probably useful if you're the same.

## Install

**curl**

```bash
curl -o ~/.local/bin/how https://raw.githubusercontent.com/Grang404/how/main/how
chmod +x ~/.local/bin/how
```

**clone and symlink**

```bash
git clone https://github.com/Grang404/how.git
cd how
chmod +x how
ln -s "$PWD/how" ~/.local/bin/how

```

`~/.local/bin` should be on your `$PATH`.

## Usage

```plaintext
how <query>       search entries (case-insensitive, partial match)
how -l            list all entry names
how -a            add an entry interactively
how -e            open the entries file in $EDITOR
how -d <name>     delete an entry (exact name match)
how -h            help
```

```bash
how tar           # find your tar entry
how -a            # add a new one interactively
how -d "tar"      # delete it
```

## Entry format

Entries live in `~/.config/how/entries` (created automatically on first run). Plain text, edit it directly if you want.

```plaintext
tar extract
tar -xzf archive.tar.gz -C /target/dir
---
ffmpeg trim
ffmpeg -ss 00:00:10 -to 00:01:30 -i input.mp4 -c copy out.mp4
---
```

Lines starting with `#` outside an entry body are treated as comments and ignored.

## Config

```bash
HOW_FILE=/path/to/file how <query>
```

Set `HOW_FILE` in your shell profile to make it permanent.

## Requirements

- `bash` 4+
- `awk` (gawk or nawk)
- Nothing else
