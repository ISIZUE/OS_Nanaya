
# デフォルト動作

default:
	../z_tools/make.exe run

#ファイル生成規則
Nanayaos.bin : Nanayaos.nas Makefile
	     ../z_tools/nask.exe Nanayaos.nas Nanayaos.bin Nanayaos.lst

Nanayaos.img : Nanayaos.bin Makefile
	../z_tools/edimg.exe  imgin:../z_tools/fdimg0at.tek \
		wbinimg src:Nanayaos.bin len:512 from:0 to:0 imgout:Nanayaos.img

#コマンド

asm :
	../z_tools/make.exe -r Nanayaos.bin

img :
	../z_tools/make.exe -r Nanayaos.img

run :
	../z_tools/make.exe img
	copy Nanayaos.img ..\z_tools\qemu\fdimage0.bin
	../z_tools/make.exe -C ../z_tools/qemu

install :
	../z_tools/make.exe img
	../z_tools/imgtol.com w a: Nanayaos.img

clean :
	-del Nanayaos.bin
	-del Nanayaos.lst

src_only :
	../z_tools/make.exe clean
	-del Nanayaos.img
