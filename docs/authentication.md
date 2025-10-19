# GitHub Authentication Setup Guide

This guide covers two methods to authenticate with GitHub: HTTPS (using Personal Access Tokens) and SSH keys.

---

## Method 1: HTTPS with Personal Access Token (PAT)

### Why Not Regular Passwords?

GitHub no longer accepts regular passwords for Git operations. You must use Personal Access Tokens instead.

### Creating a Personal Access Token

1. **Go to GitHub Settings**

   - Click your profile picture (top-right) → Settings
   - Scroll down to "Developer settings" (bottom-left)
   - Click "Personal access tokens" → "Tokens (classic)"

2. **Generate New Token**

   - Click "Generate new token" → "Generate new token (classic)"
   - Give it a descriptive name (e.g., "My Laptop - Git Access")
   - Set expiration (recommend 90 days for security)
   - Select scopes (minimum: check "repo" for full repository access)
   - Click "Generate token"

3. **IMPORTANT: Save Your Token**
   - Copy the token immediately (it won't be shown again)
   - Save it in a secure password manager
   - Treat it like a password

### Using Your Token

When Git asks for your password during push/pull/clone:

- **Username**: Your GitHub username
- **Password**: Paste your Personal Access Token (not your GitHub password)

### Caching Credentials (Avoid Repeated Entry)

#### On macOS:

```bash
git config --global credential.helper osxkeychain
```

#### On Windows:

```bash
git config --global credential.helper wincred
```

#### On Linux:

```bash
# Cache for 1 hour (3600 seconds)
git config --global credential.helper 'cache --timeout=3600'

# Or use libsecret for permanent storage
sudo apt-get install libsecret-1-0 libsecret-1-dev
cd /usr/share/doc/git/contrib/credential/libsecret
sudo make
git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret
```

---

## Method 2: SSH Keys (Recommended for Frequent Use)

SSH keys allow you to connect to GitHub without entering credentials each time.

### Step 1: Check for Existing SSH Keys

#### macOS & Linux:

```bash
ls -al ~/.ssh
```

#### Windows (Git Bash or PowerShell):

```bash
ls -al ~/.ssh
```

Look for files named:

- `id_rsa.pub`
- `id_ecdsa.pub`
- `id_ed25519.pub`

If you see these, you already have SSH keys. You can use them or create new ones.

---

### Step 2: Generate New SSH Key

#### All Platforms:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

**Note**: If your system doesn't support ed25519, use:

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

**During key generation**:

- Press Enter to save in default location (`~/.ssh/id_ed25519`)
- Enter a passphrase (optional but recommended for security)
- Re-enter passphrase

---

### Step 3: Add SSH Key to SSH Agent

#### On macOS:

1. Start the SSH agent:

```bash
eval "$(ssh-agent -s)"
```

2. Check if `~/.ssh/config` exists:

```bash
ls ~/.ssh/config
```

3. If it doesn't exist, create it:

```bash
touch ~/.ssh/config
```

4. Add this to `~/.ssh/config`:

```
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

5. Add your key:

```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

If you didn't set a passphrase, omit `--apple-use-keychain`:

```bash
ssh-add ~/.ssh/id_ed25519
```

#### On Linux:

1. Start the SSH agent:

```bash
eval "$(ssh-agent -s)"
```

2. Add your key:

```bash
ssh-add ~/.ssh/id_ed25519
```

To make the key persist across reboots, add this to your `~/.bashrc` or `~/.zshrc`:

```bash
if [ -z "$SSH_AUTH_SOCK" ] ; then
  eval "$(ssh-agent -s)"
  ssh-add ~/.ssh/id_ed25519
fi
```

#### On Windows:

**Using Git Bash:**

1. Start SSH agent:

```bash
eval "$(ssh-agent -s)"
```

2. Add your key:

```bash
ssh-add ~/.ssh/id_ed25519
```

**Using PowerShell (Windows 10/11):**

1. Start SSH agent service (as Administrator):

```powershell
Get-Service ssh-agent | Set-Service -StartupType Automatic
Start-Service ssh-agent
```

2. Add your key:

```powershell
ssh-add ~\.ssh\id_ed25519
```

---

### Step 4: Add SSH Key to GitHub

1. **Copy your public key to clipboard**:

   **macOS:**

   ```bash
   pbcopy < ~/.ssh/id_ed25519.pub
   ```

   **Linux:**

   ```bash
   cat ~/.ssh/id_ed25519.pub
   # Then select and copy the output
   ```

   Or with xclip:

   ```bash
   sudo apt-get install xclip
   xclip -sel clip < ~/.ssh/id_ed25519.pub
   ```

   **Windows (Git Bash):**

   ```bash
   clip < ~/.ssh/id_ed25519.pub
   ```

   **Windows (PowerShell):**

   ```powershell
   Get-Content ~\.ssh\id_ed25519.pub | Set-Clipboard
   ```

2. **Add to GitHub**:
   - Go to GitHub Settings
   - Click "SSH and GPG keys" (left sidebar)
   - Click "New SSH key"
   - Title: Give it a name (e.g., "My MacBook Pro")
   - Key type: Authentication Key
   - Paste your copied key into "Key" field
   - Click "Add SSH key"

---

### Step 5: Test Your Connection

```bash
ssh -T git@github.com
```

You should see:

```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

If you see a message about authenticity of host, type `yes` to continue.

---

## Using SSH URLs

When cloning or adding remotes, use SSH URLs instead of HTTPS:

**SSH URL format:**

```
git@github.com:username/repository.git
```

**HTTPS URL format:**

```
https://github.com/username/repository.git
```

### Examples:

**Clone with SSH:**

```bash
git clone git@github.com:username/repository.git
```

**Change existing repo from HTTPS to SSH:**

```bash
git remote set-url origin git@github.com:username/repository.git
```

**Check current remote URL:**

```bash
git remote -v
```

---

## Troubleshooting

### "Permission denied (publickey)" Error

1. Verify SSH key was added to GitHub
2. Check SSH agent is running:
   ```bash
   ssh-add -l
   ```
3. If no keys listed, add your key again:
   ```bash
   ssh-add ~/.ssh/id_ed25519
   ```
4. Test connection:
   ```bash
   ssh -vT git@github.com
   ```

### "Could not open a connection to your authentication agent"

Start SSH agent:

```bash
eval "$(ssh-agent -s)"
```

Then add key:

```bash
ssh-add ~/.ssh/id_ed25519
```

### Authentication Failed with Token

1. Verify token hasn't expired
2. Check token has correct permissions (repo scope)
3. Make sure you're using the token, not your password
4. Clear credential cache and try again:

   **macOS:**

   ```bash
   git credential-osxkeychain erase
   host=github.com
   protocol=https
   ```

   (Press Enter twice)

   **Windows:**

   ```bash
   git credential-wincred erase
   host=github.com
   protocol=https
   ```

   (Press Enter twice)

### SSH Key Passphrase Issues on macOS

If you're repeatedly asked for passphrase:

```bash
ssh-add --apple-use-keychain ~/.ssh/id_ed25519
```

And ensure `~/.ssh/config` has:

```
Host github.com
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
```

---

## Which Method Should You Use?

### Use HTTPS + Token if:

- You're just getting started
- You work on different computers frequently
- You're behind a firewall that blocks SSH (port 22)
- You prefer simplicity

### Use SSH if:

- You push/pull frequently (no credential entry needed)
- You want maximum security
- You work primarily from one machine
- You're comfortable with command line

**Pro tip**: You can use both! Use SSH on your main computer and HTTPS with tokens on others.

---

## Quick Reference

### HTTPS Authentication:

```bash
Username: your-github-username
Password: your-personal-access-token
```

### SSH Test:

```bash
ssh -T git@github.com
```

### Check Current Auth Method:

```bash
git remote -v
# https:// = HTTPS
# git@github.com = SSH
```

### Switch from HTTPS to SSH:

```bash
git remote set-url origin git@github.com:username/repo.git
```

### Switch from SSH to HTTPS:

```bash
git remote set-url origin https://github.com/username/repo.git
```
