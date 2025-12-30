1. 
08048bc6 <phase_1>:
 8048bc6:	55                   	push   %ebp
 8048bc7:	89 e5                	mov    %esp,%ebp
 8048bc9:	83 ec 10             	==sub    $0x10,%esp==
 8048bcc:	68 64 a2 04 08       	push   $0x804a264
 8048bd1:	ff 75 08             	pushl  0x8(%ebp)
 8048bd4:	e8 d2 04 00 00       	call   80490ab <strings_not_equal>
 8048bd9:	83 c4 10             	==add    $0x10,%esp==     **这一步add是在恢复前面的sub**
 8048bdc:	85 c0                	test   %eax,%eax
 8048bde:	74 05                	je     8048be5 <phase_1+0x1f>
 8048be0:	e8 13 07 00 00       	call   80492f8 <explode_bomb>
 8048be5:	c9                   	leave  
 8048be6:	c3                   	ret

2. gdb   
   after use layout asm :
	ctrl+L clean the screen
	ctrl+X &o  determine to command which window (default is the asm)
	*and then use ctrl+p for the last command  
	ctrl+F/B for cursor :front or Behind*
   d :delete all the breakpoints    /    can alse chose one
3. cmp a ,b
   jg ....   if b>a ,then jump
   ==计算的是b-a,所以都是b相对于a的关系==