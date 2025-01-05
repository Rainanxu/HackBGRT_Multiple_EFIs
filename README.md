# HackBGRT_Multiple_EFIs

This is a modified version of HackBGRT for Multiple Systems (EFI).
Just changed the profile path.

The HackBGRT README is here.
[HackBGRT_README.md](HackBGRT_README.md)

HackBGRT is intended as a boot logo changer for UEFI-based Windows systems.

## Usage

You can find the compiled EFI files in the Release, and each EFI file runs according to its corresponding configuration file.You can find the compiled EFI files in the Release, and each EFI file runs according to its corresponding configuration file.
The correspondence is as follows:

*.efi|config.txt
------|------
bootaa64_0.efi bootarm_0.efi <br> bootia32_0.efi bootx64_0.efi | config_0.txt
bootaa64_1.efi bootarm_1.efi <br> bootia32_1.efi bootx64_1.efi | config_1.txt
bootaa64_2.efi bootarm_2.efi <br> bootia32_2.efi bootx64_2.efi | config_2.txt
... | ...

You can also modify the code of the configuration file path in src/main.c:
line 443 `\\EFI\\HackBGRT` in `if (EFI_ERROR(root_dir->Open(root_dir, &base_dir, L"\\EFI\\HackBGRT", EFI_FILE_MODE_READ, 0))) {`
or 
line 450 `config_0.txt` in `const CHAR16* config_path = L"config_0.txt";`

## Building

By Windows

1. install MinGW64_gcc;
2. mingw32-make clean;
3. mingw32-make efi.
