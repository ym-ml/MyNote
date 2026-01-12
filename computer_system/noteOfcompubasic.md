##1. jg a b

if b>a jump

## 2.
every function returns in the %eac (eg:sscanf,and now we know that in the C just return one value)

## 3.gbd:
	x/x $esp  把esp寄存器中的值当作地址,查看其指向的值
	p/x $esp 查看esp寄存器里面的值
## 4.
mov    $0x7ce38b9b,%eax
mov    %eax,0x804d118
push   $0x08048cd1  //利用ret,跳转到压入栈中的0x08048cd1  //ret将栈顶(ESP指向的位置)的值弹出到EIP(指令指针寄存器),即跳转到这个值,然后ESP加4
ret    

/* cookie:0x7ce38b9b */

## 5.
push %ebp
mov %esp,%ebp
push %ebx
sub $0x14,%esp

*%ebx的压栈导致esp下移了4,所以esp和ebp差了0x18*

