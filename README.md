# The "Why Didn't I Do This Sooner?" MacBook Automation Project

Welcome to the land of "I can't believe I manually did this for years." This project is your ticket to automating the heck out of your MacBook, because life's too short for repetitive tasks.

## Getting Started

1. Install Homebrew (if you don't have it already):
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Install chezmoi using Homebrew:
   ```bash
   brew install chezmoi
   ```

3. Clone this repo faster than you can say "Why is my desktop a mess?":
   ```bash
   # Basic initialization - you'll be prompted for name, email, and location
   chezmoi init --apply https://github.com/freakinward/macbook-lifesaver.git
   
   # Or provide values directly to avoid prompts
   chezmoi init --apply https://github.com/freakinward/macbook-lifesaver.git \
     --data='{"name":"Your Name","email":"your.email@example.com","location":"default"}'
   ```
   Note: For `location`, use one of the following:
   - `default`: For your personal machine (used if not specified)
   - `dev`: For development machines
   - `client`: For client-owned machines

## Configuration
The project uses chezmoi for managing dotfiles and configurations. Here are the key commands you'll need:

### Basic File Management
```bash
# Add an existing file to chezmoi
chezmoi add ~/.zshrc

# Edit a managed file
chezmoi edit ~/.zshrc

# Apply changes to your system
chezmoi apply
```

### Working with Templates
```bash
# Create a template file (add .tmpl extension)
chezmoi add --template ~/.gitconfig

# Regenerate config after template changes
chezmoi init

# Apply specific file with verbose output
chezmoi apply -v ~/.gitconfig
```

### Configuration Variables
To modify configuration variables (name, email, etc.):

1. Edit the template: `chezmoi edit ~/.local/share/chezmoi/.chezmoi.toml.tmpl`
2. Regenerate config: `chezmoi init --config-only`
3. Apply changes: `chezmoi apply`

### Source Control
```bash
# Navigate to source directory
chezmoi cd

# Commit and push changes
git add .
git commit -m "Update configuration"
git push
```

Remember to update this README if you add significant new features or configurations!

## License

This project is licensed under the "Please Don't Sue Me, I'm Just Trying to Help" License, also known as MIT. See `LICENSE` for the boring details.
