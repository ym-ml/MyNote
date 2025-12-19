phase3.o:     file format elf32-i386


Disassembly of section .text:

00000000 <do_phase>:
   0:	55                   	           push   %ebp
   1:	89 e5                	       mov    %esp,%ebp
   3:	53                        	   push   %ebx
   4:	83 ec 24              	   sub    $0x24,%esp
   7:	65 a1 14 00 00 00      mov    %gs:0x14,%eax
   d:	89 45 f4             	       mov    %eax,-0xc(%ebp)
  10:	31 c0                	    xor    %eax,%eax
  12:	c6 45 df 00          	movb   $0x0,-0x21(%ebp)
  16:	c6 45 e0 01          	movb   $0x1,-0x20(%ebp)
  1a:	c6 45 e1 02          	movb   $0x2,-0x1f(%ebp)
  1e:	c6 45 e2 03          	movb   $0x3,-0x1e(%ebp)
  22:	c6 45 e3 04          	movb   $0x4,-0x1d(%ebp)
  26:	c6 45 e4 05          	movb   $0x5,-0x1c(%ebp)
  2a:	c6 45 e5 06          	movb   $0x6,-0x1b(%ebp)
  2e:	c6 45 e6 07          	movb   $0x7,-0x1a(%ebp)
  32:	c6 45 e7 08          	movb   $0x8,-0x19(%ebp)
  36:	c6 45 e8 09          	movb   $0x9,-0x18(%ebp)
  3a:	c6 45 e9 10          	movb   $0x10,-0x17(%ebp)
  ==3e:	0f b6 54 05 df       	movzbl -0x21(%ebp,%eax,1),%edx==
  ==43:	0f b6 92 00 00 00 00 	movzbl 0x0(%edx),%edx==
  *1.0x0是重定位之前的结果,可以先链接反汇编看一下
  2.movzbl是将八位扩展到32位,和后面的dl取后八位相对应*
  ==4a:	88 54 05 e9          	mov    %dl,-0x17(%ebp,%eax,1)==
  *这里实现了'查表',以一个赋值了的数组,查地址为0x0处的数组/字符串*
  
  4e:	83 c0 01             	add    $0x1,%eax
  51:	83 f8 0a             	cmp    $0xa,%eax
  54:	75 e8                	jne    3e <do_phase+0x3e>
  56:	c6 45 f3 00          movb   $0x0,-0xd(%ebp)   *当时考虑到了是'\0',并且计算地址,确实是*
  5a:	83 ec 0c             	sub    $0xc,%esp
  5d:	8d 5d e9             	lea    -0x17(%ebp),%ebx
  60:	53                   	    push   %ebx
  61:	e8 fc ff ff ff       	       call   62 <do_phase+0x62>
  66:	83 c4 08             	        add    $0x8,%esp
  69:	53                   	            push   %ebx
  6a:	68 00 00 00 00       	    push   $0x0
  6f:	e8 fc ff ff ff       	        call   70 <do_phase+0x70>
  74:	83 c4 10             	        add    $0x10,%esp
  77:	8b 45 f4             	        mov    -0xc(%ebp),%eax
  7a:	65 33 05 14 00 00 00 	xor    %gs:0x14,%eax
  81:	74 05                	        je     88 <do_phase+0x88>
  83:	e8 fc ff ff ff       	       call   84 <do_phase+0x84>
  88:	8b 5d fc             	       mov    -0x4(%ebp),%ebx
  8b:	c9                   	leave  
  8c:	c3                   	ret    

[^1]: 
