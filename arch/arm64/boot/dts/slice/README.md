# Slice Device tree building directory

1. run the following:

    ```bash
    export WORKDIR=~/docker-yocto-build/luxomed/am62x-var-som-linux
    export PATH=$HOME/arm-gnu-toolchain-11.3.rel1-x86_64-aarch64-none-linux-gnu/bin:$PATH
    cd $WORKDIR/ti-linux-kernel
    make ARCH=arm64 CROSS_COMPILE=aarch64-none-linux-gnu- -j$(nproc) dtbs
    ```

2. copy using:

    ```bash
    cp arch/arm64/boot/dts/ti/k3*am*var-som*.dtb $WORKDIR/rootfs/boot/dtb/
    ```

3. copy using scp to module:
    `scp arch/arm64/boot/dts/slice/k3-am625-var-som-slice-luxomed.dtb root@192.168.1.113:/boot/dtb/k3-am625-var-som-symphony.dtb`


## N.B.: Get rid of dirty word in kernel:
```bash
$ git add
$ git commit -s -a -m "getting rid of -dirty"
```
