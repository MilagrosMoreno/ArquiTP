#ヽ༼ຈل͜ຈ༽ﾉ Bootloader - Patched Pure64 ヽ༼ຈل͜ຈ༽ﾉ#

**x64BareBones** loads from a modified version of the [Pure64](http://www.returninfinity.com/pure64.html) bootloader.

From now on we'll call **payload** to the binary that Pure64 loads from the disk when booting. In *x64BareBones** the payload is formed by the kernel itself, and the modules concatenated with it.

The original Pure64 is loaded at address 0x8000 and treats the trailing 26KiB after the end of itself as the payload. The 26KiB limit is not enough for kernels developed on top of **x64BareBones**.

The patched version on **x64BareBones's** source extends the payload's size up to 250KiB.
These are roughly the steps it follows to acchieve that:

* Patched Pure64 starts in Real Mode, as any bootloader.
* It loads the first 256KiB from the disk to the address 0x8000, those are 6KiB for Pure64, the rest for the payload
* Then copies itself and the payload to an unused memory zone between the addresses 0x60000 and 0x9FFFF to preserve the contents, since Pure64 will overwrite data outside that range while enabling modes and creating it's tables
* It initializes Long Mode, enabling also addressing after the first MiB
* Then it copies the payload again to 0x100000
* Finally it jumps to that address, same as the unpatched version

This steps leave the kernel located at address 0x100000, and the modules exactly after the last byte of the kernel.