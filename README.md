# ThinkPad UEFI firmware patches collection

## Applying

Dump your firmware with an SPI flasher and or get a `bios` region binary from Lenovo.
Comment/Uncomment wanted patches in patches file for your model.
Use [LongSoft's UEFIPatch](https://github.com/LongSoft/UEFITool/releases) to apply them to your rom.
To get a working TPM use [Thrimbor's uefi-sign](https://github.com/thrimbor/thinkpad-uefi-sign) for xx20, xx30, and xx40 ThinkPads. For soldered xx40, xx50 and xx80 replace `4C 4E 56 42 42 53 45 43 FB` with `4C 4E 56 42 42 53 45 43 FF` on the previously patched binary, and [sibrazdic's utility](https://github.com/sibradzic/UEFI-playground/blob/master/fix_vendor_hashes.py) for other machines.

## Compatibility WIP

| Model/Series | Supported | Notes | TPM |
| --- | --- | --- | --- |
| T430 | Yes | N/A | Yes |
| T530 | Yes | N/A | Yes |
| T430s | Yes | N/A | Yes |
| W530 | Yes | N/A | Yes |
| X230 | Yes | N/A | Yes|
| X230t | Yes | Different Whitelist patch | Yes |
| X131e | Yes | Different Whitelist patch | ? |
| X1C1 | ? | N/A | Yes |
| T440p | Yes | N/A | Yes |
| W540/W541 | Yes | Different stock trackpad and PS/2 ID | Yes |
| T540p | Yes | N/A | Yes |
| T440 | Yes | N/A | No |
| T440s | Yes | N/A | No |
| X240 | ? | N/A | No |
| X1C2 | ? | N/A | No |
| L540 | Yes | N/A | ? |
| L440 | Probably | L540 and L440 share firmware | ? |
| T450s | Yes | N/A | No |
| T450 | Probably | N/A | No |
| T550/W550s | Probably | N/A | No |
| X250 | ? | N/A | No |
| X1C3 | ? | N/A | No |
| T460 | Yes | N/A | No |
| T460s | Probably | N/A | No |
| T560/P50s | No | N/A | No |
| X260 | ? | N/A | No |
| X1C4 | ? | N/A | No |
| T470 | Yes | N/A | No |
| T470s | Probably | N/A | No |
| T570/P51s | Probably | N/A | No |
| X270 | ? | N/A | No |
| X1C5 | ? | N/A | No |
| T480 | Yes | N/A | No |
| A485 | Probably | N/A | Yes |
| A285 | Yes | N/A | Yes |
| T480s | Probably | N/A | No |
| T580/P52s | Probably | N/A | No |
| X280 | ? | N/A | No |
| X1C6 | Yes | N/A | No |
| T490/T590/P43s/P53s | No | N/A | ? |
| T495 | Probably | N/A | Yes |
| T490s/X390 | No | N/A | ? |
| T495s/X395 | Yes | N/A | Yes |
| X1C7/X1C8 | No | N/A | No |

## Reporting comaptibility

Open a new issue with the following table:

| Model | T430 |
| --- | --- |
| Patchset | Default for generation |
| TPM | Yes, thinkpad-uefi-sign |
| Notes | DDR3-1066/800 speed limiter makes machine unbootable and is a non-volatile setting | 


## Submitting patchset

Open a pull request with the patchset added and the following table in comment:

| Model | X131e |
| --- | --- |
| TPM | Haven't tested |
| Notes | Different whitelist patch | 

Patches are standard UEFIPatch format, mention what it does, what machine it is for, who made it(your name if you did, if you found it on a forum mention OP's name) for special patchsets make sure they are uncommented by default. Example:

```
# LenovoWmaPolicyDxe | WL removal | ripped from nephiel | x131e 3.01
# uncomment to use
#79E0EDD7-9D1D-4F41-AE1A-F896169E5216 10 P:100BC841390B0F84:100BC841390B90E9 
#79E0EDD7-9D1D-4F41-AE1A-F896169E5216 10 P:00000045390B0F84:00000045390B90E9 
#79E0EDD7-9D1D-4F41-AE1A-F896169E5216 10 P:100BC841394B0474:100BC841394B04EB 
#79E0EDD7-9D1D-4F41-AE1A-F896169E5216 10 P:0F846CFFFFFFEBAF:9090909090909090
```

### Credits

xx
paranoidbashthot
dudu2002
leokim
nephiel

