### Obtain ProPresenter Support Files
1. Download this repository as a ZIP file [here](https://github.com/vifa-nextgeneration/ProPresenter/archive/refs/heads/ApartemenRobinson.zip).
2. Decompress the `ProPresenter-ApartemenRobinson.zip` file using either [7-Zip](https://www.7-zip.org/download.html) or [WinRAR](https://www.rarlab.com/download.htm).
3. Rename the `ProPresenter-ApartemenRobinson` folder to `ProPresenter`.
### Utilize ProPresenter Support Files
1. Launch the ProPresenter program at least once after a clean Windows installation.
2. Complete the "Welcome To ProPresenter" first-launch wizard using the default options.
3. Close the ProPresenter program.
4. Delete the default `ProPresenter` folder located in `C:\Users\NXGN\Documents`.
5. Move the previously renamed `ProPresenter` folder to `C:\Users\NXGN\Documents`.
### Restore `desktop.ini` System File Attribute
1. Open the `desktop.ini` file in Notepad. Press the \<Space> key once, followed by the \<Backspace> key.
2. Open the Properties of the containing folder. Go to the "Customize" tab, then click "Change Icon".
3. Simultaneously press the \<Enter> key in the Properties window and the <Ctrl + S> key in the Notepad window.
### Enable NTFS Long Paths
Some folder names exceed the length supported by the default Windows configuration. To enable support for such folders, save this code as a `.reg` file and open it:
  ```
  Windows Registry Editor Version 5.00

  [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem]
  "LongPathsEnabled"=dword:00000001
  ```
  > Tip: Restart your computer for the change to take effect.
### Merge Split Archive Files
Some [Releases](https://github.com/vifa-nextgeneration/ProPresenter/releases) contain split archive files with the `_split-XY` suffix. To decompress such archives, merge the split archive files into a single archive file using the following command:
  ```
  copy /b archive_yyyymmdd.7z_split-* archive_yyyymmdd.7z
  ```
  > Tip: Only merge one release at a time. This command may take a while to complete.
### Batch Scripts Usage
|`MediaExport.cmd`|`MediaImport.cmd`|
|-|-|
|Empties the `Media\Assets` folder by moving each media file into the respective `Added Manually` subfolders.|Populates the `Media\Assets` folder by moving each media file out of the respective `Added Manually` subfolders.|
### Remarks
- All `.lnk` files are safe to delete in an active production environment, as they do not affect availability.
- Fourteen folders contain a `desktop.ini` file.
- All [Releases](https://github.com/vifa-nextgeneration/ProPresenter/releases) contain archive files with media larger than 100 MiB.
