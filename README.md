# tinycr

```
$ ./build.sh
Crystal 0.12.0 [90eaec1] (Tue Feb 16 14:31:00 UTC 2016)

+ crystal build hello.cr --emit obj --prelude=empty --release
+ ld hello.o -o hello -s --static -nostdlib --gc-sections -T script.ld
+ objcopy -j combined -O binary hello hello.bin
+ nasm -f bin -o tinybin -D entry=0x400070 elf.s
+ chmod +x tinybin
+ hexdump -C tinybin
00000000  7f 45 4c 46 02 01 01 00  48 65 6c 6c 6f 21 0a 00  |.ELF....Hello!..|
00000010  02 00 3e 00 01 00 00 00  70 00 40 00 00 00 00 00  |..>.....p.@.....|
00000020  38 00 00 00 00 00 00 00  00 00 00 00 00 00 00 00  |8...............|
00000030  00 00 00 00 38 00 38 00  01 00 00 00 07 00 00 00  |....8.8.........|
00000040  00 00 00 00 00 00 00 00  00 00 40 00 00 00 00 00  |..........@.....|
00000050  00 00 40 00 00 00 00 00  92 00 00 00 00 00 00 00  |..@.............|
00000060  92 00 00 00 00 00 00 00  00 10 00 00 00 00 00 00  |................|
00000070  b8 01 00 00 00 bf 01 00  00 00 be 08 00 40 00 ba  |.............@..|
00000080  07 00 00 00 0f 05 b8 3c  00 00 00 31 ff 0f 05 31  |.......<...1...1|
00000090  c0 c3                                             |..|
00000092
+ wc -c
146
+ ./tinybin
Hello!
```
