# Bandit Level 12 -> Level 13

## Objetivo
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)



### Datos de acceso
user: bandit12
password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4 
address: bandit.labs.overthewire.org
port: 2220

### Teoria
Un hexdump es una representación textual de los datos binarios de un archivo. En lugar de ver caracteres extraños o "basura", el hexdump muestra el valor de cada byte en formato hexadecimal (base 16, del 00 al FF).
Generalmente tiene tres columnas:

Offset (Dirección): Indica en qué posición del archivo estamos.

Valores Hexadecimales: El contenido real del archivo en bytes.

Representación ASCII: El intento de traducir esos bytes a texto (puntos . si no son imprimibles).

Identifica y Descomprime (Repetir según sea necesario):Usa file binario_original para ver qué es. Dependiendo de lo que te diga, usa el comando correcto:
- Si es GZIP: mv archivo archivo.gz $\rightarrow$ gunzip archivo.gz
- Si es BZIP2: mv archivo archivo.bz2 $\rightarrow$ bzip2 -d archivo.bz2
- Si es TAR: mv archivo archivo.tar $\rightarrow$ tar -xf archivo.tar

### Solución
<pre>
ssh -p 2220 bandit12@bandit.labs.overthewire.org

bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ mktemp -d
/tmp/tmp.JtiOX4854o
bandit12@bandit:~$ cp data.txt /tmp/tmp.JtiOX4854o
bandit12@bandit:~$ cd /tmp/tmp.JtiOX4854o
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data.txt
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file data.txt 
data.txt: ASCII text
bandit12@bandit:/tmp/tmp.JtiOX4854o$ cat data.txt 
00000000: 1f8b 0808 2e17 ee68 0203 6461 7461 322e  .......h..data2.
00000010: 6269 6e00 0134 02cb fd42 5a68 3931 4159  bin..4...BZh91AY
00000020: 2653 59b6 7680 8b00 001a ffff fadd cfd6  &SY.v...........
00000030: f2e7 f6bb b87f 57ee fff3 b7d7 8bfd fafe  ......W.........
00000040: bffe fdfd d9ef 3dff bfff bdff b001 3aa1  ......=.......:.
00000050: a40d 007a 9901 a000 1a01 a000 1934 7a80  ...z.........4z.
00000060: 6993 469a 6800 0068 1a00 0340 680d 0d00  i.F.h..h...@h...
00000070: 01a6 8794 188d 0c27 a8d3 4608 8006 4d01  .......'..F...M.
00000080: 8800 3268 c8d0 3434 0006 9a19 0f50 3400  ..2h..44.....P4.
00000090: 1840 6403 2064 0034 1934 c468 c862 6868  .@d. d.4.4.h.bhh
000000a0: c801 a000 68f5 0e9e a346 8343 4346 8698  ....h....F.CCF..
000000b0: 40d0 0686 864c 9b48 0000 0003 40d3 4d34  @....L.H....@.M4
000000c0: 3231 3261 0003 46d4 01ea 0000 1a00 d000  212a..F.........
000000d0: 0d00 0020 c002 3067 df82 0e7a a6f5 b39a  ... ..0g...z....
000000e0: 6472 0263 7c59 8eaf c404 a738 aece fe35  dr.c|Y.....8...5
000000f0: 1921 a104 6114 268f 7f45 0411 a3de efc3  .!..a.&..E......
00000100: 7905 de6d 2229 95e1 a0e0 0d61 13bd 457e  y..m").....a..E~
00000110: 5ea0 e955 1a0c c20c dbf5 853e 0177 370e  ^..U.......>.w7.
00000120: 073a 1fb3 2b32 57b7 0c16 1ae4 c817 ac62  .:..+2W........b
00000130: 94ca ed32 1d62 6acb 0e94 e932 2b6f 9702  ...2.bj....2+o..
00000140: 4480 2c49 9192 eab8 fc13 dd5d 4ebb 4495  D.,I.......]N.D.
00000150: a8c5 81d9 e2b8 e68d 291e e9e2 11ee cc35  ........)......5
00000160: 6460 63e7 fc6c 1575 7984 da54 8626 21d6  d`c..l.uy..T.&!.
00000170: 8888 2469 cb2e 4229 6f7a 9658 174a 2edd  ..$i..B)oz.X.J..
00000180: 2381 252f 2b81 5693 5f96 432d 4f17 25e8  #.%/+.V._.C-O.%.
00000190: 9129 100e 4ef1 83ca 11de 610d 7bb0 33f0  .)..N.....a.{.3.
000001a0: a3d7 a77c dab0 cfdb 4793 5bda b7a1 2573  ...|....G.[...%s
000001b0: 0ce4 d2f2 a221 1c83 5053 dd24 bacd f161  .....!..PS.$...a
000001c0: 22d9 f42b 903d 68c4 479e c021 f658 7a32  "..+.=h.G..!.Xz2
000001d0: 67c6 975e 8b25 7c28 2ad6 119e d5e6 dbcf  g..^.%|(*.......
000001e0: 2469 7a74 fa67 3ea2 235e 1500 6deb f009  $izt.g>.#^..m...
000001f0: 3ad0 ef6e 444d 15e9 fdc2 67bc 01f3 1764  :..nDM....g....d
00000200: 980e b3c6 045f ef4b ffd1 e529 4130 2141  ....._.K...)A0!A
00000210: ca03 5c28 dce0 5f73 ecec b637 d1fe 852f  ..\(.._s...7.../
00000220: f9eb 416b b5fd df54 8aa6 0b08 022d 7160  ..Ak...T.....-q`
00000230: 215d f790 ccb0 f047 9240 083c d2a6 c098  !].....G.@.<....
00000240: 04bf f8bb 9229 c284 85b3 b404 5856 1e5b  .....)......XV.[
00000250: 9034 0200 00                             .4...
bandit12@bandit:/tmp/tmp.JtiOX4854o$ xxd -r data.txt > file1
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file file1 
file1: gzip compressed data, was "data2.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 564
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data.txt  file1
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv file1 file1.gz
bandit12@bandit:/tmp/tmp.JtiOX4854o$ gunzip file1.gz 
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data.txt  file1
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file file1 
file1: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data.txt  file1
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv file1 file1.bz2
bandit12@bandit:/tmp/tmp.JtiOX4854o$ bzip2 -d file1.bz2 
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data.txt  file1
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file file1 
file1: gzip compressed data, was "data4.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv file1 file1.gz
bandit12@bandit:/tmp/tmp.JtiOX4854o$ gunzip file1.gz 
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data.txt  file1
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file file1
file1: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv file1 file1.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ tar -xf file1.tar 
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data5.bin  data.txt  file1.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv data5.bin data5.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data5.tar  data.txt  file1.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ tar -xf data5.tar 
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data5.tar  data6.bin  data.txt  file1.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file data6.bin 
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/tmp.JtiOX4854o$ bzip2 -d data6.bz2 
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data5.tar  data6  data.txt  file1.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file data
data: cannot open `data' (No such file or directory)
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv data6 data6.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ tar -xf data6.tar 
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data5.tar  data6.tar  data8.bin  data.txt  file1.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file data8.bin 
data8.bin: gzip compressed data, was "data9.bin", last modified: Tue Oct 14 09:26:06 2025, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv data8.gz
mv: missing destination file operand after 'data8.gz'
Try 'mv --help' for more information.
bandit12@bandit:/tmp/tmp.JtiOX4854o$ mv data8.bin data8.gz
bandit12@bandit:/tmp/tmp.JtiOX4854o$ gunzip data8.gz 
bandit12@bandit:/tmp/tmp.JtiOX4854o$ ls
data5.tar  data6.tar  data8  data.txt  file1.tar
bandit12@bandit:/tmp/tmp.JtiOX4854o$ file data8
data8: ASCII text
bandit12@bandit:/tmp/tmp.JtiOX4854o$ cat data8 
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
<pre>


**Flag: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn**