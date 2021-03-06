This is a tool for merging dynamic partition system.img to normal.
You can use this tool to extract non dynamic firmware.

Note⚠️: As i have Redmi Note 4x(mido) so i have entered it's system partition size in repack.sh if u have any other device then change count accordingly.

Credits and Special thanks to:
Erfan,Nippon,Jamie and Yash for helping me to make dynamic partition script and repacking script.

# Requirements
- protobuf
- LZMA
- 7z
- lz4
## Linux
```bash
apt install unace unrar zip unzip p7zip-full p7zip-rar sharutils rar uudeview mpack arj cabextract rename
apt install liblzma-dev python-pip brotli lz4
pip install backports.lzma protobuf pycrypto
```
## Arch
```bash
pacman -S unace unrar zip unzip p7zip sharutils uudeview arj cabextract
pacman -S python python-pip brotli lz4
pip install backports.lzma protobuf pycrypto
sudo pip3 install --upgrade protobuf
```
### For "rename" and "mpack" you need to manually clone and install the packages
```bash
for package in mpack rename; do
    git clone https://aur.archlinux.org/"${package}"
    cd "${package}" || continue
    makepkg -si --skippgpcheck
    cd - || break
    rm -rf "${package}"
done
```
## Mac
```bash
brew install protobuf liblzma-dev brotli lz4
pip install backports.lzma protobuf pycrypto
```
Also install [mono](https://www.mono-project.com/docs/getting-started/install/mac/)  

### Windows
Install cygwin, and select

```Latest python and pip packages, arj, brotli, cabextract, dos2unix, lz4, p7zip, renameutils, sharutils, unace, unzip and zip```

If you get syntax errors run dos2unix on extractor.sh

# How to use
## Download
```
git clone --recurse-submodules https://github.com/Hunter-commits/Dynamic_Partition_Extractor.git
```

## Extract images from firmware URL
Example: Extracting images from pixel 2 factory image:
```
cd Dynamic_Partition_Extractor
wget https://dl.google.com/dl/android/aosp/walleye-pq3a.190705.001-factory-cc471c8c.zip -o firmware.zip
./extractor.sh firmware.zip
```
output will be on "Dynamic_Partition_Extractor/out"
