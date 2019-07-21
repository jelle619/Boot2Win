# Boot2Win
A desktop entry that boots you into Windows from your Linux desktop

## Setup
This guide will help you getting Boot2Win setup. First of all, make sure you have Windows installed. Install your favourite GNU/Linux operating system with the GRUB bootloader afterwards.

### Setting up GRUB
Make sure Windows is your second entry in the GRUB bootloader menu. If you have two operating systems installed, this often is already the case. While booted into Linux, install gedit from your software repository (you may also use another text editor, but in here we'll use gedit). After that is done, open up the terminal and use the following command.

```bash
sudo gedit /etc/default/grub
```

Search for the line GRUB_DEFAULT=0 and modify it to GRUB_DEFAULT=saved. You may also want to disable the timeout in the GRUB menu by modifying the line GRUB_TIMEOUT=10 (or any other number than 10) to 0.001 (using 0 might yield the same results but it's not guaranteed to work). To apply your changes, save the file and use the following command in the terminal. 

```bash
sudo update-grub
```

On Fedora, you may want to use one of the following commands instead (UEFI only):

```bash
sudo grub2-mkconfig -o "$(readlink /etc/grub2-efi.cfg)"
```

### Placing the desktop entry

Now, download the newest Boot2Win desktop entry from this repository and move the file after downloading to ``~/.local/share/applications``.

### Congratulations!
You have now completed the installation. To boot into Windows from your Linux installation, launch the desktop entry.

## License
This project uses the GNU General Public License v3.0. A copy of this license can be found in the repository.
