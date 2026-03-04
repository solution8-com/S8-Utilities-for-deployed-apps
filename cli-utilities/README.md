```markdown
# 🐚 Zsh Utility Functions & Aliases

A curated collection of Zsh utility functions and aliases to supercharge your terminal productivity. Includes helpers for file management, Git, Docker, PDF generation, Homebrew, OpenAI API, and more.

---

## 🚀 Quick Start

1. **Clone or Copy**  
   Copy the provided `.zshrc` content into your `~/.zshrc` file, or clone your own utilities repository if using `zshrc-push`.

2. **Reload Zsh**  
   ```sh
   source ~/.zshrc
   ```

3. **Install Prerequisites**  
   See [Prerequisites](#-prerequisites) below for required tools.

---

## 🛠️ Function List

| Function / Alias      | Description                                                      |
|-----------------------|------------------------------------------------------------------|
| `mkcd`               | Create a directory and immediately `cd` into it                  |
| `killit`             | Kill all processes matching a name                               |
| `extract`            | Extract almost any compressed file format                        |
| `glog`               | Visualize Git log as a graph                                     |
| `duh`                | Disk usage in human-readable format (default depth 2)            |
| `brewup`             | Update & clean all Homebrew packages                             |
| `ssh-agent-connect`  | Start SSH agent and add default key                              |
| `generate_random_pdf`| Generate a random PDF with N characters                          |
| `gi`                 | Add a file/pattern to `.gitignore`                               |
| `te3l`               | Get OpenAI text-embedding-3-large for a string                   |
| `del`                | Remove a file (with check)                                       |
| `zshrc-push`         | Auto-backup `.zshrc` to GitHub repo (S8-Utilities)               |
| `symlink`            | Create a symbolic link (`ln -s`)                                 |

**Aliases:**

- `ll`      – `ls -lah` (long list)
- `grep`    – Colorized grep
- `gs`      – `git status`
- `ga`      – `git add .`
- `gcm`     – `git commit -m`
- `gp`      – `git push`
- `gpl`     – `git pull`
- `pip`, `pip3` – Warn to use `uv pip install` or `python -m pip`
- `dcu`     – `docker-compose up`
- `dcd`     – `docker-compose down`
- `dps`     – `docker ps`
- `jsondiff-regent` – Run global-scripts/jsondiff_regent.py
- `spdf`    – Launch Stirling-PDF Docker and open in browser
- `n8n`     – Launch n8n Docker and open in browser
- `zshrc-backup` – Alias for `zshrc-push`

---

## 📚 Usage Examples

### Directory & File Utilities

```sh
mkcd myfolder
# Creates 'myfolder' and enters it

del somefile.txt
# Removes 'somefile.txt' if it exists

symlink /path/to/target mylink
# Creates a symlink named 'mylink' pointing to /path/to/target
```

### Process & Disk

```sh
killit node
# Kills all processes with 'node' in their name

duh 3
# Shows disk usage, depth 3 (default is 2)
```

### Git Shortcuts

```sh
gs
# git status

glog
# Pretty git log graph

gi node_modules
# Adds 'node_modules' to .gitignore
```

### Docker Shortcuts

```sh
dcu
# docker-compose up

spdf
# Launches Stirling-PDF Docker and opens browser

n8n
# Launches n8n Docker and opens browser
```

### File Extraction

```sh
extract archive.tar.gz
# Extracts archive.tar.gz to current directory
```

### Homebrew Utilities

```sh
brewup
# Updates, upgrades, and cleans up Homebrew packages
```

### PDF Generation

```sh
generate_random_pdf 10000 /tmp/random.pdf
# Creates a PDF with 10,000 random characters at /tmp/random.pdf
```

### OpenAI Embedding

```sh
te3l "Hello world"
# Gets text-embedding-3-large for "Hello world" and saves to file
```

### .zshrc Backup

```sh
zshrc-push
# Pushes your .zshrc to S8-Utilities repo (requires GitHub token)
```

---

## 🧰 Prerequisites

Some functions and aliases require the following tools:

- **Zsh** (with `compinit`)
- **Homebrew** (`brew`)
- **Git**
- **Docker** (for `spdf`, `n8n`, etc.)
- **curl**
- **unrar**, **7z**, **unzip**, **bunzip2**, **gunzip**, **cupsfilter** (for `extract` and `generate_random_pdf`)
- **Python 3** (for `jsondiff-regent`)
- **OpenAI API key** (for `te3l`)
    - Store in macOS Keychain:  
      ```sh
      security add-generic-password -a "$(whoami)" -s "openai_api_key" -w "sk-your-key"
      ```
- **GitHub token** (for `zshrc-push`)
    - Store in macOS Keychain:  
      ```sh
      security add-generic-password -a "$(whoami)" -s "github_s8_utilities" -w "github_pat_..."
      ```

**Note:**  
- On macOS, `cupsfilter` is pre-installed.  
- Some extract formats require installing `unrar` and `p7zip` via Homebrew.

---

## 📝 Customization

- Add or remove aliases/functions as needed.
- Update `$PATH` as appropriate for your system.
- For additional utilities, see comments in `.zshrc`.

---

## 📄 License

Feel free to use, modify, and share!

---
```