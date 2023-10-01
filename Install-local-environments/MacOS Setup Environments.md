### Prerequisites
- Make sure you have [Homebrew](https://brew.sh/) installed. If not, you can install it by running:
    `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`
### Step 1: Install pyenv
Open your terminal and run the following command to install `pyenv` using Homebrew:
`brew install pyenv`
### Step 2: Add pyenv to Shell
You'll need to add `pyenv` to your shell so that the `pyenv` command is available every time you open a new terminal window.
If you're using `zsh` (the default shell on macOS), add the following lines to your `.zshrc` file:
`echo 'if command -v pyenv 1>/dev/null 2>&1; then eval "$(pyenv init --path)"; fi' >> ~/.zshrc`
If you're using `bash`, add the following lines to your `.bash_profile`:
`echo 'if command -v pyenv 1>/dev/null 2>&1; then eval "$(pyenv init --path)"; fi' >> ~/.bash_profile`
After adding these lines, apply the changes:
`source ~/.zshrc  # For zsh # or source ~/.bash_profile  # For bash`
### Step 3: Install Python Versions
Now you can install different versions of Python. To see a list of available versions, run:
`pyenv install --list`
To install a specific version, run:
`pyenv install 3.9.7  # Replace 3.9.7 with the version you want`
### Step 4: Set Global Python Version
To set the global Python version across your system, use:
`pyenv global 3.9.7  # Replace 3.9.7 with the version you installed`
To verify that it's set correctly, run:
`python --version`
### Step 5: Set Local Python Version (Optional)
If you want to set a Python version for a specific project, navigate to the project directory and run:
`pyenv local 3.9.7  # Replace 3.9.7 with the version you want for this project`
This will create a `.python-version` file in the directory, specifying the Python version to use.
### Step 6: Install pyenv-virtualenv
After installing `pyenv`, you can install the `pyenv-virtualenv` plugin to manage virtual environments. Open your terminal and run:
`brew install pyenv-virtualenv`
### Step 7: Integrate pyenv-virtualenv with Shell
You'll need to add `pyenv-virtualenv` to your shell just like you did with `pyenv`.
If you're using `zsh`, add the following lines to your `.zshrc`:
`echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.zshrc`
If you're using `bash`, add the following lines to your `.bash_profile`:
`echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bash_profile`
Apply the changes:
`source ~/.zshrc  # For zsh # or source ~/.bash_profile  # For bash`
### Step 8: Create a Virtual Environment
Navigate to your project directory and create a new virtual environment. Replace `myenv` with your desired environment name and `3.9.7` with the Python version you want to use.
`pyenv virtualenv 3.9.7 myenv`
### Step 9: Activate the Virtual Environment
To activate the virtual environment, you can use:
`pyenv activate myenv`
Your shell prompt will change to show the name of the activated environment.
### Step 10: Deactivate the Virtual Environment
To deactivate the virtual environment and revert to the global Python version, run:
`pyenv deactivate`
### Step 11: Set a Local Environment for a Project (Optional)
If you want to automatically activate a virtual environment when you enter a project directory, you can set a local environment:
`pyenv local myenv`
This will create a `.python-version` file in the directory, specifying the virtual environment to use.
### Step 12: Delete a Virtual Environment (Optional)
If you want to delete a virtual environment, first deactivate it if it's active, and then run:
`pyenv uninstall myenv`
