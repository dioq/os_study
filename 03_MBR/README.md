
## MBR  介绍
MBR 全称 Master Boot Record 主引导记录,大小必须是 512 字节，主要作用是，告诉计算机到启动盘的哪一个位置去找操作系统。 </br>
主引导记录由三个部分组成：   </br>
![MBR](https://user-images.githubusercontent.com/15027024/226443650-54aa7b48-8ffa-4b4b-9957-1b20d3741c8b.png)
（1） 第1-446字节：bootstrap代码(446字节，用到的只有前面440字节)调用操作系统的机器码。    </br>
（2） 第447-510字节：分区表(64字节)（Partition table）。    </br>
（3） 第511-512字节：主引导记录签名（0x55和0xAA），通过这2字节的值判断该硬盘是不是真的可用于启动。    </br>

分区表的作用，是将启动盘分成若干个区。   </br>
MBR会加找到启动盘的活动分区(分区)，并且加载其中的代码，如果系统有bootloader，则加载bootloader。常见的bootloader有grub，lilo。    </br>
加载bootloader后，系统会提示选择哪个操作系统，对于装了多个操作系统的硬盘，bootloader会定位到正确的扇区加载内核镜像   </br>
所谓的加载无非就是拷贝代码到ram,然后jmp到目的地址开始执行代码    </br>
</br>
</br>
名词介绍:   </br>
启动盘  	可以是软盘也可以是硬盘   </br>