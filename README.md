# Pico Submodules Index
This repository provides an index of useful Pico-related submodules to help streamline development and project organization.

Below you'll find links to recommended submodules and instructions for adding, creating, and working with Git submodules in your own projects.

## Submodules
- [Displays](https://github.com/AlexBramhill/pico-displays.git)
- [Event Loop](https://github.com/AlexBramhill/pico-event-loop)
- [Wifi Manager](https://github.com/AlexBramhill/pico-wifi-manager)
- [Clock Service](https://github.com/AlexBramhill/pico-clock-service)

## Working with submodules
### Adding to a project
To add a submodule to your project, run:
```bash
git submodule add <repository-url> <desired-location>
```
Replace `<repository-url>` with the URL of the submodule repository, and `<desired-location>` with the path where you want it in your project.

After adding, initialize and update submodules with:
```bash
git submodule update --init --recursive
```
This ensures all submodules are fetched and ready to use.

### Creating from existing project

To create a submodule from an existing project directory:

1. **Clone your main repository**
    ```bash
    git clone <main-repository-url>
    cd <main-repo-folder>
    ```

2. **Extract the desired subdirectory**
    ```bash
    git filter-repo --subdirectory-filter <subdirectory-name>
    ```
    Replace `<subdirectory-name>` with the folder you want to turn into a submodule.

3. **Create a new repository and push**
    ```bash
    git remote rename origin old-origin
    git remote add origin <new-repository-url>
    git push -u origin main
    ```
    Replace `<new-repository-url>` with the URL of your new submodule repository.

### Cloning projects that use these submodules

To clone a project and initialize its submodules, use:
```bash
git clone --recurse-submodules <repository-url>
```
Replace `<repository-url>` with the actual URL of the repository you want to clone.
