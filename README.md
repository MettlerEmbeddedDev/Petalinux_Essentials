# Petalinux Quick Start
Notes on required steps for creating/maintaining a custom PetaLinux project



###  boot images build directly from the BSP: 

1. Download the related Petalinux Board Support Package (Use the same version BSP as the tool) [Link](https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/embedded-design-tools.html)
2.
3. "https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/embedded-design-tools.html"
1. Petalinux-create -t project -s <path_to_bsp_file>.bsp -n <project_name>
2. cd to the Petalinux project directory
3. Petalinux-config
4. Petalinux-build
5. cd ./image/linux
6. petalinux-package --wic --images-dir images/linux/ --bootfiles "ramdisk.cpio.gz.u-boot,boot.scr,Image,system.dtb,system-zynqmp-sck-kr-g-revB.dtb" --disk-name "sda"
7. Write the image into an SD card through Balena Etcher or similar tool
