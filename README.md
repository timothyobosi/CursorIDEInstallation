# CursorIDEInstallation
Instructions:\
Install Cursor on Ubuntu

To install the Cursor AI code editor on Ubuntu 24.04, follow these steps:

1. **Download the AppImage**: Use the Download button on the [Cursor website](https://www.cursor.com/) to download the `NAME.AppImage` file.

2. **Move the AppImage**: Copy the downloaded `.AppImage` file to your Applications directory.
   ```bash
   mkdir -p ~/Applications
   mv NAME.AppImage ~/Applications/cursor.AppImage
   ```

3. **Make the AppImage Executable**: Ensure the `.AppImage` file is executable.
   ```bash
   chmod +x ~/Applications/cursor.AppImage
   ```

4. **Install Dependencies**: If you encounter issues running the AppImage, install `libfuse2`.
   ```bash
   sudo apt update
   sudo apt install libfuse2
   ```

5. **Add to .bashrc or .zshrc**: Add an alias to your shell configuration file to easily run Cursor.
   ```bash
   echo "alias cursor='~/Applications/cursor.AppImage --no-sandbox'" >> ~/.bashrc
   source ~/.bashrc
   ```

6. **Create a Desktop Entry**: Optionally, create a `.desktop` file for easy access from the application menu.
   ```bash
   echo "[Desktop Entry]
   Name=Cursor
   Exec=/home/yourusername/Applications/cursor.AppImage --no-sandbox
   Icon=/path/to/icon/cursor.png
   Type=Application
   Terminal=false" > ~/.local/share/applications/cursor.desktop
   ```

7. **Install AppArmor Profile (Optional)**: To secure the installation, you can install an AppArmor profile for Cursor.
   ```bash
   curl https://gist.githubusercontent.com/tatosjb/0ca8551406499d52d449936964e9c1d6/raw/eec8df843c35872ba3e590c7db5451af7e131906/install-cursor-sh | bash
   ```

8. **Reboot**: After completing the installation, reboot your system to ensure everything is set up properly.

If you encounter any issues, such as graphical errors or a white screen after login, you can recover by reinstalling the desktop environment:
```bash
sudo apt-get install --reinstall ubuntu-desktop
```

Alternatively, if you prefer not to use `libfuse2`, you can extract the AppImage manually and run the application from the extracted files.
