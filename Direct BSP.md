###  Building image directly from the BSP: 

1. Download the related Petalinux Board Support Package (Use the same version BSP as the tool) ([Link](https://www.xilinx.com/support/download/index.html/content/xilinx/en/downloadNav/embedded-design-tools.html))
2. petalinux-create -t project -s <path_to_bsp_file>.bsp -n <project_name>
3. cd to the Petalinux project directory
4. petalinux-config
5. petalinux-build
6. cd ./image/linux
7. petalinux-package --boot --u-boot --force
8. petalinux-package --wic --images-dir images/linux/ --bootfiles "ramdisk.cpio.gz.u-boot,boot.scr,Image,system.dtb,system-zynqmp-sck-kr-g-revB.dtb" --disk-name "sda"
9. Write the image into an SD card through Balena Etcher or similar tool
