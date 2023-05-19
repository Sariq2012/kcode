File: code-001.asm
mov a, 2 
add a, 3
sub a, 5 
add a, 1
add a, 2 
sub a, 3
add a, 20

--------------------
File: code-002.asm
mov a, 103 
mov b, 7 
mov c,232
this:
mov [c], a
dec a 
dec b 
inc c 

cmp b, 0 
je Jeff_bezoz
jmp this 
Jeff_bezoz:
hlt

--------------------
File: code-003.asm
; ~((0xE2 ^ 0x2D) | 0x8C)

mov a, 0xE2
mov b, 0x2d
xor a, b 
mov c ,0x8c
or a, c
not a 

--------------------
File: code-004.asm
; ((0x2b & 0x6e) | (~(0xfe))) ^ 0xdb

mov a, 0x2b
mov b, 0x6e
and a, b 
mov c, 0xfe 
not c 
or a, c 
xor a, 0xdb

--------------------
File: code-005.asm
; ~(((0xA5 << 2) ^ 0xDB) & 0xBC)
mov a, 0xA5
shl a, 2
xor a, 0xDB
and a, 0xBC
not a

;one byte memory 
;machine code 

;0:06
;1:00
;2:A5	
;3:5d
;4:00
;5:02
;6:51
;7:00
;8:db
;9:49
;A:00
;B:bc
;C:52
;D:00

--------------------
File: code-006.asm
; (0xeb ^ 0x37) >> 3
mov a, 0xeb
xor a, 0x37
shr a, 3

--------------------
File: code-007.asm
; 1 2 3 4 5 6 7

push 1
push 2
push 3
push 4
push 5 
push 6
push 7

--------------------
File: code-008.asm
; one byte memory

;MaaT: Memory as a Table
;Program as a Table

;address: value(1-byte)
;    0      10
;    1      E2
;    2      D5


mov a, 2
mov b, 3
add a, b
not a

;address: value(1-byte)
; 0: 06
; 1: 00
; 2: 02
; 3: 06
; 4: 01
; 5: 03
; 6: 0A
; 7: 00
; 8: 01

;memory (2-byte)

;0: 06 00
;2: 02 06
;4: 01 03
;6: 0A 00
;8: 00 01

;memory (4-byte)
;0: 06 00 02 06
;4: 01 03 0A 00
;8: 00 01 00 00


;memory(instruction-size)
;0: 06 00 02
;3: 06 01 03
;6: 0A 00 01
;9: 52 00
 

--------------------
File: code-009.asm
; x86 assembly
mov eax, 0x2b3dec5e
mov ebx, 3
mov edx, 5
mov ecx, 7
add eax, ebx
add ecx, edx

; machine code

;0:  b8 5e ec 3d 2b          mov    eax,0x2b3dec5e
;5:  bb 03 00 00 00          mov    ebx,0x3
;a:  ba 05 00 00 00          mov    edx,0x5
;f:  b9 07 00 00 00          mov    ecx,0x7
;14: 01 d8                   add    eax,ebx
;16: 01 d1                   add    ecx,edx

--------------------
File: code-010.asm
; ABCD

mov a, 65
mov b, 66
mov c, 67
mov d, 68

push a
push b
push c
push d

pop a
pop b
pop c
pop d

--------------------
File: code-011.asm
; A = (0xE2 | 0x5D) ^ 0x2F
; B = (0xFE & 0x95)
; C = (~0x3F) << 1
; D = 0x8E >> 2
; A = B, B = A, C = D, D = C

mov a, 0xe2
or a, 0x5d
xor a, 0x2f

mov b, 0xfe
and b, 0x95

mov c, 0x3f
not c
shl c, 1

mov d, 0x8e
shr d, 2

push a
push b
pop b
pop a
push c
push d
pop c
pop d

--------------------
File: code-012.asm
mov a, 90
mov b, 232
mov c, 10

this:
mov [b], a
dec a
dec c
inc b
cmp c, 0
je best
jmp this
best:
hlt
 

--------------------
File: code-013.asm
mov a, 90
mov b, 232
mov c, 10

this:
cmp a, 88
je change_to_a

mov [b], a
jmp else

change_to_a:
mov [b], 97

else:
dec a
dec c

inc b
cmp c, 0
je best

jmp this
best:
hlt
 

--------------------
File: code-014.asm
mov a, 90
mov b, 232
mov c, 15
mov d, 0
this:
cmp d, 2
je write_space

mov [b], a
inc d
jmp else

write_space:
mov [b], 35
mov d, 0

else:
dec a
dec c

inc b
cmp c, 0
je best

jmp this
best:
hlt

--------------------
File: code-015.asm
;1: ((0x2E ^ 0xD3) | (0x73 & 0xCE) ^ 0x6E) << 5

mov a, 0x2e
xor a, 0xd3 
mov b, 0x73
and b, 0xce
or a, b
xor a, 0x6e
shl a, 5
 

--------------------
File: code-016.asm
;2: ((0x3D & 0x50) ^ ((~0x49) << 0x7E)) | 0x6E

mov a, 0x3d
and a, 0x50
mov b, 0x49
not b
shl b, 0x7e
xor a, b
or a, 0x6e 

--------------------
File: code-017.asm
; 3:((0x4f >> 5) & ((~0x17) << 4)) >> (~0xFC)

mov a, 0x4f
shr a, 5
mov b, 0x17
not b

shl b, 4
and a, b
mov c,0xFC
not c

shr a, c


--------------------
File: code-018.asm
; 4: ((0xA2 | 0xF3) ^ (~(0x3E & 0x2E))) << 0x02

mov a, 0xa2
or a, 0xf3
mov b, 0x3e
and b, 0x2e
not b
xor a, b
shl a, 0x02

--------------------
File: code-019.asm
; 5: ((~(~0x3E)) ^ (0x6D | (~0xDB))) | (1 << 1)

mov a, 0x3e
mov b, 0x6d
mov c, 0xdb
not c
or b, c
xor a, b
mov d, 1
shl d, 1
or a, d

--------------------
File: code-020.asm
; 5: ((~(~0x3E)) ^ (0x6D | (~0xDB))) | (1 << 1)
; 5: ((0x3E ^ (0x6D | (0x24))) | (2)


; solution #1
mov a, 0x3e
mov b, 0x6d
mov c, 0xdb
not c
or b, c
xor a, b
mov d, 1
shl d, 1
or a, d

; solution #2
mov a, 0x3e
mov b, 0x6d
or b, 0x24
xor a, b
or a, 2



--------------------
File: code-021.asm
; 6: ((0x3C ^ 0x24) & (0x26 ^ 0xEE)) << (~0xFE)
; 6: (0x18 & 0xC8) << (0x01)

;0011 1100
;0010 0100
;0001 1000:0x18

;1110 1110
;0010 0110
;1100 1000:0xC8


; solution #1
mov a, 0x3c
xor a, 0x24
mov b, 0x26
xor b, 0xee
and a, b
mov c, 0xfe
not c
shl a, c

; solution #2

mov a, 0x18
and a, 0xc8
shl a, 0x01

; solution #3
; 6: 0x08 << 0x01
mov a, 0x10

--------------------
File: code-022.asm
; 7: ((~0xDC) | 0x66) & (0x83)) >> (0xA5 ^ 0xA5)
; 7: ((~0xDC) | 0x66) & (0x83))

; 0010 0011: 0x23 
; 0110 0110: 
; 0110 0111: 0x67
; 1000 0011
; 0000 0011: 0x03


mov a, 0x23
or a, 0x66
and a, 0x83

--------------------
File: code-023.asm
MOV A, 1
MOV B, 3
this: MOV C, 7
MOV D, 5

PUSH 1
PUSH 2
that: PUSH 3
PUSH 4



;00:06 mov
;01:00 a
;02:01 b
;03:06 mov
;04:01 b
;05:03 3
;this->06:06 mov
;07:02 c08:07 7
;09:06 mov
;10:03 d
;11:05 5
;12:35 push
;13:01 1
;14:35 push
;15:02 2
;that->16:35 push
;17:04 4

; execution-path = [00, 03, 06 , 09, 12, 14,16]
		

--------------------
File: code-024.asm
mov a, 90
mov b,10
mov c,232
hi:
mov [c], a
inc c
dec b
dec a
cmp b, 0
je ooc
jmp hi
ooc:
hlt

--------------------
File: code-025.asm
MOV A, 10
MOV B, 1

CALL my_function

MOV D, C
HLT

my_function:
cmp a, 0
je eof

loop:
add b, 2
dec a
cmp a, 0
je eof
jmp loop
eof:
mov b, c
ret

--------------------
File: code-026.asm
MOV A, 10
MOV B, 232
mov c, 90
CALL print_10_char

HLT

print_10_char:
cmp a, 0
je eof

loop:
mov [b], c
add b, 1
dec a
dec c
cmp a, 0
je eof
jmp loop
eof:
mov b, c
ret

--------------------
File: code-027.asm
MOV A, 10
MOV B, 232
mov c, 57
CALL print_10_dig

HLT

print_10_dig:
cmp a, 0
je eof

loop:
mov [b], c
add b, 1
dec a
dec c
cmp a, 0
je eof
jmp loop
eof:
mov b, c
ret

--------------------
File: code-028.asm
MOV A, 10
MOV B, 232
mov c, 48
CALL print_10_dig

HLT

print_10_dig:
cmp a, 0

je eof

loop:
mov [b], c
add b, 1
mov [b], 32
add b, 1

dec a
inc c
cmp a, 0
je eof
jmp loop
eof:
mov b, c
ret

--------------------
File: code-029.asm
MOV A, 10
MOV B, 232
mov c, 48
CALL print_10_dig

HLT

print_10_dig:
cmp a, 0

je eof

loop:
mov [b], c
add b, 1
mov [b], 32
add b, 1

dec a
inc c
cmp a, 0
je eof
jmp loop
eof:
mov b, c
ret


;00:06 mov
;01:00 a
;02:0a 10
;03:06 mov
;04:01 b
;05:e8 232
;06:06 mov
;07:02 c
;08:30 48
;09:38 call
;10:0c print_10_dig
;11:00 hot
;print_10_dig->12:17 cmp 
;13:00 a
;14:00 0
;15:25 je
;16:28 eof
;loop->17:05 mov
;18:01 [b]
;19:02 c
;20:0d add
;21:01 b
;22:01 1
;23:08 mov
;24:01 [b]
;25:20 32
;26:0d add
;27:01 [b]
;28:01 1
;29:13 dec
;30:00 a
;31:12 inc
;32:02 c
;33:17 cmp
;34:00 a
;35:00 0
;36:25 je
;37:28 eof
;38:1f jmp
;39:11 loop
;eof->40:01 mov
;41:01 b
;42:02 c
;43:39 ret

--------------------
File: code-030.asm
; value = 2 + 3 * 5 - 6

mov a, 3
mul 5
add a, 2
sub a, 6

; value = 24 / 2 - 6 * 3 - 8

mov a, 24
div 2
mov b, a
mov a, 6
mul 3 
sub b, a
sub b, 8

--------------------
File: code-031.asm
; value = 65
; if value == 65 :
;    print('A')
; else:
;    print('B')

mov a, 65
mov b, 232
cmp a, 65
je print_a

mov [b], 66
hlt
print_a:
mov [b], 65
hlt

--------------------
File: code-032.asm
; From C to Assembly

;#include <stdio.h>

;int main() {
;  int time = 20;
;  if (time < 18) {
;    printf("A");
;  } else {
;    printf("B");
;  }
;  return 0;
;}
mov b, 232
mov a, 20
cmp a, 18
jb print_if
mov [b], 66
hlt
print_if:
mov [b], 65

hlt

--------------------
File: code-033.asm
; From PHP to Assembly

;<?php
;$t = 100;

;if ($t < 100) {
;  echo "A";
;} elseif ($t == 100) {
;  echo "B";
;} else {
;  echo "C";
;}
;?>

mov a, 100
mov b, 232
cmp a, 100
jb print_a
cmp a, 100
je print_b
mov [b], 67
hlt
print_a:
mov [b], 65
hlt

print_b:
mov [b], 66
hlt



--------------------
File: code-034.asm
; From Java to Assembly

;print=System.out.println

;int t = 22;
;if (t < 10) {
;  System.out.println("A");
;} else if (t > 25) {
;  System.out.println("B");
;} else {
;  System.out.println("C");
;}

mov a, 22
mov b, 232
cmp a, 10
jb print_a
cmp a, 25
ja print_b
mov [b], 67
hlt
print_a:
mov [b], 65
hlt
print_b:
mov [c], 66
hlt

--------------------
File: code-035.asm
mov a, 50
div 2
add a, 1

mul 2
add a, 10
shr a, 2
and a, 24

--------------------
File: code-036.asm
mov a, 20
mov b, 64
sub b, 16
add b, 32
div 5
shr b, a
mov a, 64
mul 2
xor b, a

--------------------
File: code-037.asm
;(((6 + 2 - 4 * 3) + 4) << 1) ^ (16 * 4 + 16)
mov a, 4
mov b, 6
mul 3
add b, 2
sub b, a

add b, 4
shl b, 1



mov a, 16
mul 4
add a, 16
xor a, b  

--------------------
File: code-038.asm
;((1 + 2 + 3 - 1 * 2) ^ ((5 + 1) / 2) >> (8 | 12)
mov a, 2
mov b, 1
mul 1
sub a, 3
add a, 2
add b, a

mov a, 5
add a, 1
mov c, 2
div c

xor b, a
mov d, 8
or d, 12
shr b, d



--------------------
File: code-039.asm
;#include <stdio.h>

;int main()
;{
;    int value = 0;
;    for(int i = 1; i <= 10; i++){
;        value = value + 1;
;    }

;   return 0;
;}

mov a, 0 
mov b, 1 
for_loop:
cmp b, 10
ja oout_of_loop
inc a
inc b    
jmp for_loop
oout_of_loop:
hlt

--------------------
File: code-040.asm
;#include <stdio.h>

;int main()
;{
;    int value = 0;
;    for(int i = 1; i <= 10; i++){
;        for(int y = 1; y <= 5; y++){
;            value = value + i + y;
;        }
;    }

;    return 0;
;}


mov a, 0 
mov b, 1
mov c, 1 
fora:
cmp b, 10
ja out_of_loop
 
forb:
cmp c, 5
ja return_to_loop
add a, b 
add a, c
inc c
jmp forb
return_to_loop:
inc b
jmp fora

out_of_loop:
hlt

--------------------
File: code-041.asm
;#include <stdio.h>

;int main()
;{
;    int value = 0;
;    int sum = 0;
;    while(value <= 7){
;        sum++;
;        value++;
;    }

;    return 0;
;}

mov a, 0
mov b, 0
while:
cmp a, 7
ja out_of_loop
inc a 
inc b 
jmp while
out_of_loop
hlt

--------------------
File: code-042.asm
mov a,  00000010b 
mov b,  00000110b
mov c,  00001100b
or a, 0x26
and b, 0x6d
xor c, 0x24

--------------------
File: code-043.asm
MOV A, 00000000b
mov b, 00010000b
mov c, 0
loop:
xor a, b
shl b, 1
inc c
cmp c, 4
je out_loop
jmp loop
out_loop:
hlt

--------------------
File: code-044.asm
MOV A, 11111111b
mov b, 00000001b
mov c, 0
mov d, 0
loop:
push a
and a, b
cmp a, 0
jne one
pop a

inc c
shl b, 1
cmp c, 8
je out_loop

jmp loop
one:
shl b, 1
inc c
inc d
pop a
cmp c, 8
je out_loop
jmp loop
out_loop:
hlt

--------------------
File: code-045.asm
JMP code
;data

array: db 0x0A
       db 0x0B
       db 0x0C
       db 0x0D
       db 0x0E
       db 0x0F

tmp: db 0x00


code:

;A = 0x0D
;B = 5
;C = 0x0F
;D = 3

mov b, array
add b, 3

mov d, array 
inc d

mov a, array
add a, 3
mov a, [a]
mov c, array
add c, 5
mov c, [c]
hlt

 

--------------------
File: code-046.asm
sub sp, 6
mov [sp+1], 0x35
mov [sp+4], 0x0f
mov a, [sp+1]
mov [sp+3], a
add sp, 6
hlt

--------------------
File: code-047.asm
;1.input -> process -> output
;2.input -> process
;3.process->output
;4.process

; create the process(function) 1
; call it N

;call:

;1-input
mov a, 8
mov b, 8
;2-process
call sum
;3-output
mov c, d

mov a, 53
mov b, 1
call sum
mov c, d
hlt






sum:
 add a, b
 mov d, a
 ret

--------------------
File: code-048.asm
	mov a, 5
	mov b, 9

	call my_stack
	hlt

my_stack:
	sub sp, a
	mov [sp+1], b
        add sp, a
	ret 

--------------------
File: code-049.asm
;msg = "welcome to python"
;print(msg)

jmp beg_code
msg: db "welcome to python"
      db 0
beg_code:
mov b, 232
mov a, msg
loop:
mov c, [a]
mov [b], c
inc b
inc a
cmp c, 0
je end_code
jmp loop 

end_code:
hlt

--------------------
File: code-050.asm
;a = 33
;b = 200

;if b > a:
;  print("b is greater than a")

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;

jmp bg_code
;data center
msg: db "b is greater than a"
     db 0
val2: db 4
bg_code:

mov b, 7
cmp b, [val2] 
jbe end_code

mov c, 232
mov d, msg
loop:
mov a, [d]
cmp a,0
je end_code
mov [c], a

inc d
inc c


jmp loop
end_code:
hlt

--------------------
File: code-051.asm
jmp code
message: db "Visual Studio Code>Pycharm"
         db 0
code:
mov a, message 
call len
   HLT


len:
mov c, 0
loop:
   mov d, [a]
   cmp d, 0
   je end_of_loop
   inc c
   inc a
   jmp loop
   end_of_loop:
   RET

--------------------
File: code-052.asm
 ;unsigned int result = 32;
 ;result = (result << 2) + 4;
 ;result = (result >> 1) - 2;
 ;result = result | 1;
 ;result = result & 0xFF;
 ;result = result ^ result;
 ;result = ~(result);

mov a, 32
shl a, 2
add a, 4
shr a, 1
sub a, 2
or a, 1
and a, 0xff
xor a, a
not a

mov a, 32
shl a, 2
add a, 4
shr a, 1
sub a, 2
or a, 1
mov a, 0xff

--------------------
File: code-053.asm
;int result = 0;
;int value = 175;

;if(value < 200){
;    result = 1;
;}else{
;    result = -1;
;}

mov a, 0
mov b, 175
cmp b, 200
jb result
dec a
hlt
result:
mov a, 1
hlt

--------------------
File: code-054.asm
;/* Convert the following C code to Assembly code. */
;#include <stdio.h>

;int main(){
;    int sum = 0;
;    for(int i = 15; i >= 1; i--){
;        sum += i;
;    }
;    return 0;
;}

mov a, 0
mov b, 15
loop:
cmp b, 0
je end_code
add a, b
dec b
jmp loop

end_code:
hlt

--------------------
File: code-055.asm
;int sum = 0;
;while(sum < 32){
;    sum = sum + 1;
;}

mov a, 0
loop:
cmp a, 32
je end_code
inc a 
jmp loop
end_code:
hlt

--------------------
File: code-056.asm
;<?php
;$sum = 0;
;for ($x = 0; $x <= 10; $x++) {
;  $sum = $sum + $x;
;}

;?>

mov a, 0
mov b, 0
loop:
cmp b, 11
je end_code
add a, b
inc b
jmp loop
end_code:
hlt

 

--------------------
File: code-057.asm
;unsigned char value = 0x4B;
;unsigned char result = 0x00;

;if(value == 0x1B){
;    result = 0x01;
;}else if(value == 0x2B){
;    result = 0x02;
;}else if(value == 0x3B){
;    result = 0x03;
;}else if(value == 0x4B){
;    result = 0x04;
;}else{
;    result = 0x0A;
;}
mov a, 0x4b
mov b, 0x00
cmp a, 0x1b
je equal1
cmp a, 0x2b
je equal2 
cmp a, 0x3b
je equal3
cmp a, 0x4b
je equal4
mov a, 0x0a
hlt
equal1:
mov a, 0x01
hlt
equal2:
mov a, 0x02
hlt
equal3:
mov a, 0x03
hlt
equal4:
mov a, 0x04
hlt

--------------------
File: code-058.asm
;#include <stdio.h>

;int sum(int first, int second){
;    return first + second;
;}

;int main(){
;    int result = sum(1, 2);
;    return 0;
;}
main:
 mov a, 1
mov b, 2
call sum
mov c, a
sum:
add a, b
ret

--------------------
File: code-059.asm
;/* Convert the following C code to Assembly code.*/
;#include <stdio.h>

;int main(){
;    int vals [] = {1, 2, 3, 4, 5};
;    int vals_len = 5;
;    for(int i = 0; i < vals_len; i++){
;       printf("%d\n", vals[i]);
;    }
;    return 0;
;}
jmp main
vals: db 1
      db 2
      db 3
      db 4
      db 5
tmp: db 0
main:
mov a, 0
mov b, 232
mov c, vals
loop:
cmp a, 5
je end_doe
mov d, [c]
add d, 48
mov [b], d
inc a
inc b
inc c
jmp loop
end_doe:
hlt

--------------------
File: code-060.asm
;/* Convert the following C code to Assembly code. */
;#include <stdio.h>

;int main(){
;    int sum = 0;
;    for(int i = 1; i <=10; i++){
;        if((i % 2) == 0){
;            sum += i;
;        }
;    }
;    return 0;
;}
main:
mov a, 0
mov b, 1
loop:
cmp b, 10
ja end_code 
mov c, b
and c, 1
cmp c, 1
jne sum 
jmp x 
sum:
add a, b
x:
inc b
jmp loop
end_code:
hlt

--------------------
File: code-061.asm
sub sp, 10
mov [sp+2], 0xab
mov [sp+4], 0xff
mov [sp+8], 0x9c

--------------------
File: code-062.asm
mov a, 10
mov b, 20
mov c, 30 
mov d, 40 
push a
push b
push c
push d
pop a
pop b
pop c
pop d
hlt

--------------------
File: code-063.asm
;for number in [1, 2, 3, 4, 5] {
;    print(number)
;}
mov a, 1
mov b, 232
mov d, 1
loop:
cmp d, 5
ja end_code
mov c, a
add c, 48
mov [b], c
inc b
inc d
inc a
jmp loop
end_code:
hlt

--------------------
File: code-064.asm
JMP start

this: db 10
here: db 88

that: db 10
      db 20
      db 30
      db 40
      db 50
      db 60
      db 70

start:
mov d, that
add d, 4
hlt

--------------------
File: code-065.asm
JMP start

this: db 10
here: db 88

that: db 10
      db 20
      db 30
      db 40
      db 50
      db 60
      db 70

start:
mov b, that
add b, 3
mov a, b
add a, 3
mov c, [a]
hlt

--------------------
File: code-066.asm
JMP start

this: db 10
here: db 88

that: db 10
      db 20
      db 30
      db 40
      db 50
      db 60
      db 70

start:
mov a, that
mov b, that
add a, 2
mov [a], 60
add b, 5
mov [b], 30
hlt

--------------------
File: code-067.asm
JMP start

this: db 10
here: db 88

that: db 10
      db 20
      db 30
      db 40
      db 50
      db 60
      db 70

start:
mov a, that 
mov b, that 
mov c, [this]
Inc a
mov [a], c 

add b, 3
mov c, [here]
mov [b], c
hlt

--------------------
File: code-068.asm
jmp start
ages: db 1
      db 2
      db 3
      db 4 
      db 5

start:
mov a, ages
mov b, 232

loop:

 mov  c, [a]
 add c, 48
 mov [b], c
 inc b
 inc a
 cmp c, 53
 je end_code
 jmp loop
end_code: 
hlt

--------------------
File: code-069.asm
mov a, 49 ; var i
mov b, 53 ; var n
mov c, 232
loop:
cmp a, b
ja end_code
mov [c], a
inc a
inc c
jmp loop
end_code:
hlt

--------------------
File: code-070.asm
jmp start
positive: db "Positive number"
          db 0
zero: db "Zero"
      db 0
negative: db "Negative number" 
          db 0        
start:
mov a, 0
mov b, 232
cmp a, 0
ja to_positive
cmp a, 0
je to_zero
jmp to_negative
to_positive:
mov d, positive 
jmp loop
to_zero:
mov d, zero
jmp loop
to_negative:
mov d, negative
jmp loop

loop:
mov c, [d]
mov [b], c
inc d
inc b
cmp c, 0
je end_code
jmp loop
end_code:
hlt

--------------------
File: code-071.asm
main:
mov a, 5
call find_square
mov d, a
hlt

find_square:
   mul a
   ret 

--------------------
File: code-exam-01.asm
; unsigned char value = (((0x7E << 1) & 0x4B) | 0x8C) ^ 0xDB
mov a, 0x7e
shl a, 1
and a, 0x4b
or a, 0x8c
and a, 0xdb

--------------------
File: code-exam-02.asm
;void main() {
;  print('Welcome to Dart')
jmp main_code
array:db "Welcome to Dart"

main_code:
mov a, array
mov b, 232
mov d, [array]
hello:
mov d, [a]
cmp d, 0
je end_code
mov [b], d
inc b
inc a
cmp a, 17
je end_code
jmp hello
end_code:
hlt

--------------------
File: code-exam-03.asm
; public static void main(String[] args) {

;        int testscore = 76;
;        char grade;
;
;        if (testscore >= 90) {
;            grade = 'A';
;        } else if (testscore >= 80) {
;           grade = 'B';
;       } else if (testscore >= 70) {
;            grade = 'C';
;        } else if (testscore >= 60) {
;            grade = 'D';
;        } else {
;            grade = 'F';
;        }
;        System.out.println(grade);
;    }
mov a, 76
mov b, 232

cmp a, 90
jae end_code0


cmp a, 80
jae end_code1

cmp a, 70
jae end_code2

cmp a, 60
jae end_code3


cmp a, 60
jb end_code4

end_code0:
mov [b], 65
hlt



end_code1:
mov [b], 66
hlt



end_code2:
mov [b], 67
hlt




end_code3:
mov [b], 68
hlt




end_code4:
mov [b], 70
hlt

--------------------
File: code-exam-04.asm
;void main() {
;  for (int i = 0; i < 5; i++) {
;    print(i);
;  }
;}
mov a, 48
mov b, 232

loop:
mov [b], a
inc b
inc a
inc d
cmp d, 5
je end_code

jmp loop

end_code:
hlt

--------------------
File: code-exam-05.asm

jmp main
print:db "yes"
      db 0

main:
mov d, 232

mov a, 10
call isEven 
cmp b, 1
je print_yes
print_yes:
mov c, print
mov a, [c]
mov [b], a 
inc c
inc b
cmp a, 0
je end_code
jmp print_yes


hlt 
isEven:
and a, 1
cmp a, 0
je result
mov b, 0
ret 
result:
mov b, 1
ret
end_code:
hlt


--------------------
File: code-exam-2-01.asm
;unsigned int result = 64; A 
;result = (result >> 2) + 4;
;result = (result << 1) - 2;
;result = result | 1;
;result = result & 0xFF;
;result = result ^ result;
;result = ~(result);
mov a, 64
shr a, 2
add a, 4
shl a, 1
sub a, 2
or a, 1
xor a, a
not a

--------------------
File: code-exam-2-02.asm
;int sum = 0;
;while(sum < 16){
;    sum = sum + 1;
;}

mov a, 0
loop:
cmp a, 16
ja end_code
inc a
jmp loop
end_code:
hlt

--------------------
File: code-exam-2-03.asm
 ;int vals [] = {1, 2, 3, 4, 5};
 ;int vals_len = 5;
 ;for(int i = 0; i < vals_len; i++){
 ;      printf("%d\n", vals[i]);
 ;}


jmp start
vals: db 1
      db 2
      db 3
      db 4
      db 5
start:

mov c, vals ; aray
mov b, 232 ; number of screen
mov d, 0 ; i

loop:

mov a, [c]
cmp d, 4
ja end_code
add a, 48
mov [b], a
inc b
inc c 
inc d 
jmp loop 
end_code:
hlt

--------------------
File: code-exam-2-04.asm
;unsigned char value = 0x2B;
;unsigned char result = 0x00;

;    if(value == 0x1B){
;        result = 0x01;
;    }else if(value == 0x2B){
;        result = 0x02;
;    }else if(value == 0x3B){
;        result = 0x03;
;    }else if(value == 0x4B){
;        result = 0x04;
;    }else{
;        result = 0x0A;
;    }
mov a, 0x2b ; value
mov b, 0x00 ; result
cmp a, 0x1b
je result_1
cmp a, 0x2b
je result_2
cmp a, 0x3b 
je result_3
cmp a, 0x4b 
je result_4
mov b, 0x0a
hlt
result_1:
mov b, 0x01
hlt
result_2:
mov b, 0x02
hlt
result_3:
mov b, 0x03
hlt
result_4:
mov b, 0x04
hlt

--------------------
File: code-exam-2-05.asm
;#include <stdio.h>

;int sum(int first, int second){
;    return first + second;
;}

;int main(){
;    int result = sum(1, 2);
;    return 0;
;}
jmp main
; a=first_num
;b=second_num
;c= result
sum:
mov c, a
add c, b
ret 


main:
mov a, 1
mov b, 2
call sum 

--------------------
File: 001_mark_down_class var_vs_instance_var.md
# Mark down class variable vs instance variable
On `OOP` we use 2 types of variable, `class variable` and `instance variable`
- `Class variable`: Class variable is a variable that gets defined inside the class yet outside of any __init__ function yet we only **define it once** Calling the class variable you need to use the name of the class.
- `Instance variable` is a variable that is defined inside the init function and it is linked with the **self keyword** ontop of that the instance variable get called many times
### example of instance variable and class variable:
```python
#Creating the class
Class Sudent: 
 #Creating the class variable
s1 = Khalid 
def __init__(self , grade , age):
   #Creating the instance variable#
   self.grade = grade
   self. age = age
   
 def print_students(self)
    print("the student name is", Student.s1 , " And his age is" self.age," and his grade is ",self.grade)
    
#Creating the instance - object
k1 = Student(13 , 100)
k1.print_students()
 

--------------------
File: 002_oop_course_section_1.py
#Chapter 2:
#Object-Oriented Programming (OOP) Essentials
class Car:
    # Create a class variable
    NoOfTires = 4
    # creating the class initlizer
    def __init__(self): #without attributes
        self.make = "ford"
        self.model = "moustage"
        self.year = 2010
        self.color = "blue"
        self.MoonRoof = True
        self.EngineRunning = False
    # Method
    def StartTheEngine(self):
        self.EngineRunning = True

    def StopTheEngine(self):
        self.EngineRunning = False

class MyCar: #with attrubutes and upgraded
     def __init__(self , make , model , year , color , MoonRoof = False):#(if u want to pass a paramter it has to be in the end if i add a other one it will raise a eror):
        # if you delete the value of the instance variable and make it "" u cant pass objects and when you print it it will be blank
        self.make = make
        self.model = model
        self.year = year
        self.color = color
        self.MoonRoof = MoonRoof #if you pass true it will be True and if u pass false it will pas true yet if u dont pass anything it will be false because the defult val is false 
        self.EngineRunning =  False
    # Method
    
     def StartTheEngine(self):
        self.EngineRunning = True

     def StopTheEngine(self):
        self.EngineRunning = False

def main():
    print("Hello from the main method") # that is outside the class
    # creating the objects
def car1_create():
    print("Accsesing the car1 variable")
    car1 = MyCar("Ford","mustang",2010,"Blue")
    car2 = MyCar("Tesla,model 3",2020,"Blue", True) 
    model1 = car1.model #the car1.make the "make" is a attribute
    print(model1) # this is a way to accses a attrbiue yet there is a easir way
    #print(car1.model)
    # accesising the car1 attrbiute:
    print(car1.make, car1.model, car1.year, car1.color, car1.MoonRoof )
 
if __name__ == '__main__':
    main()       
    car1_create()
# create a simple calculater app the with oop
class calc:
    prceantge1 = 110
    prceantge2 = 120
    prceantge3 = 130
    prceantge4 = 140
    prceantge5 = 150
    def __init__(self , num1 , num2):
        self.num1 = num1
        self.num2 = num2

    def addtion(self):
        print(self.num1 + self.num2)
    
    def sub(self):
        print(self.num1 + self.num2)
    
    def mult(self):
        print(self.num1 * self.num2)

    def div(self):
        print(self.num1)

question1 = calc(10,40)
question1.addtion()

#create a project that helps the hr team to  analize a employe bounouse + vaction 
class FinmanceEmployesWage:
    def __init__(self, Base_Salary , bounse_range , vaction , retirment_funds  ):
        self.Base_Salary = Base_Salary
        self.vaction = vaction
        self.retirment_funds = retirment_funds
        self.bounse_range = bounse_range
  
     
    def bounse(self):
        bounses1 = 1 + self.bounse_range / 100
        self.Base_Salary = self.Base_Salary * bounses1
        salary_after_bounse = self.Base_Salary
    def retirment_funds(self):
        if self.retirment_funds == 0:
            pass
        retirment_fund = 1 - self.retirment_funds / 100
        self.Base_Salary = self.Base_Salary * retirment_fund
             
    def print_all(self):
        print("-------------------------------------------------------------------------")
        print("Youre total yearly salary is "+ self.Base_Salary)
        print("Youre vaction for this year is "+ self.vaction)
      
print("                        Yearly Finance")
print("-------------------------------------------------------------------------")
Salary = int(input("Please enter: youre  base salary"))
Bounse = int(input("Please enter: youre anual bounse"))
Vaction = int(input("Please enter: total vaction hours"))
RetirmentFunds = int(input("Please enter: total funds to the retirment funds"))
Year = int(input("how many years you have been working for this company if less then one year enter 0"))

if Salary == 0: 
   print("-------------------------------------------------------------------------")
   raise ValueError("Youre yearly salary shoud be btween 45000 to 125000") 


if Bounse == 0: 
   print("-------------------------------------------------------------------------")
   raise ValueError("Youre yearly bounse shoud be btween 10 to 20 precent") 


if Vaction == 0: 
   print("-------------------------------------------------------------------------")
   raise ValueError("Youre yearly vaction  shoud be atleast  96 hours") 

def vaction_1(vac):
        op1 = 1 + 110 / 100
        vac1 = vac * op1
        return vac1
      
def vaction_2(vac):
        op2 = 1 + 120 / 100
        vac2 = vac * op2
        return vac2
      
     
def vaction_3(vac):
        op3 = 1 + 130 / 100
        vac3 = vac * op3
        return vac3
      
     
    
def vaction_4(vac):
        op4 = 1+ 140 / 100
        vac4 = vac * op4
        return vac4
      

     
def vaction_5(vac):
        op5 =  1 + 150  / 100
        vac5 = vac * op5
        return vac5
      


employee_1 = FinmanceEmployesWage(Salary,Bounse,Vaction,RetirmentFunds)
if Year == 1:
    employee_1.vaction_1(Vaction)
elif Year == 2:
    employee_1.vaction_2(Vaction)
elif Year == 3:
    employee_1.vaction_3(Vaction)
elif Year == 4:
    employee_1.vaction_4(Vaction)
elif Year == 5:
    employee_1.vaction_5(Vaction)

employee_1.bounse()
employee_1.retirment_funds()
employee_1.print_all()




--------------------
File: 003_ : 003_Programming_(OOP)_Essentials.py
 #Chapter 3:
#Object-Oriented Programming (OOP) Essentials
class Car:
    # Create a class variable
    NoOfTires = 4
    # creating the class initlizer
    def __init__(self): #without attributes
        self.make = "ford"
        self.model = "moustage"
        self.year = 2010
        self.color = "blue"
        self.MoonRoof = True
        self.EngineRunning = False
    # Method
    def StartTheEngine(self):
        self.EngineRunning = True

    def StopTheEngine(self):
        self.EngineRunning = False

--------------------
File: 004_adding_attrubutes.py
   self.EngineRunning = False

class MyCar: #with attrubutes and upgraded
     def __init__(self , make , model , year , color , MoonRoof = False):#(if u want to pass a paramter it has to be in the end if i add a other one it will raise a eror):
        # if you delete the value of the instance variable and make it "" u cant pass objects and when you print it it will be blank
        self.make = make
        self.model = model
        self.year = year
        self.color = color
        self.MoonRoof = MoonRoof #if you pass true it will be True and if u pass false it will pas true yet if u dont pass anything it will be false because the defult val is false 
        self.EngineRunning =  False
    # Method
    
     def StartTheEngine(self):
        self.EngineRunning = True

     def StopTheEngine(self):
        self.EngineRunning = False
    # destructer this function gets called autmaticly when the objects get deleted
     def __del__(self):
         print("DEstructer invoked".format(self.make, self.model))
        
    
def main():
    print("Hello from the main method") # that is outside the class
    # creating the objects
def car1_create():
    print("Accsesing the car1 variable")
    car1 = MyCar("Ford","mustang",2010,"Blue")
    car2 = MyCar("Tesla,model 3",2020,"Blue", True) 
    model1 = car1.model #the car1.make the "make" is a attribute
    print(model1) # this is a way to accses a attrbiue yet there is a easir way
    #print(car1.model)
    # accesising the car1 attrbiute:
    print(car1.make, car1.model, car1.year, car1.color, car1.MoonRoof )
    del car1
    del car2  # if you tery to do any commands on these var it will be a eror because it is derleted 100%
if __name__ == '__main__':
    main()       
    car1_create()

--------------------
File: 005_simple_calc.py

# create a simple calculater app the with oop
class calc:
    prceantge1 = 110
    prceantge2 = 120
    prceantge3 = 130
    prceantge4 = 140
    prceantge5 = 150
    def __init__(self , num1 , num2):
        self.num1 = num1
        self.num2 = num2

    def addtion(self):
        print(self.num1 + self.num2)
    
    def sub(self):
        print(self.num1 + self.num2)
    
    def mult(self):
        print(self.num1 * self.num2)

    def div(self):
        print(self.num1)

question1 = calc(10,40)
question1.addtion()

--------------------
File: 006_emmployee_salary_finacnce.py

#create a project that helps the hr team to  analize a employe bounouse + vaction 
class FinmanceEmployesWage:
    def __init__(self, Base_Salary , bounse_range , vaction , retirment_funds  ):
        self.Base_Salary = Base_Salary
        self.vaction = vaction
        self.retirment_funds = retirment_funds
        self.bounse_range = bounse_range
  
     
    def bounse(self):
        bounses1 = 1 + self.bounse_range / 100
        self.Base_Salary = self.Base_Salary * bounses1
        salary_after_bounse = self.Base_Salary
    def retirment_funds(self):
        if self.retirment_funds == 0:
            pass
        retirment_fund = 1 - self.retirment_funds / 100
        self.Base_Salary = self.Base_Salary * retirment_fund
             
    def print_all(self):
        print("-------------------------------------------------------------------------")
        print("Youre total yearly salary is "+ self.Base_Salary)
        print("Youre vaction for this year is "+ self.vaction)
      
print("                        Yearly Finance")
print("-------------------------------------------------------------------------")
Salary = int(input("Please enter: youre  base salary"))
Bounse = int(input("Please enter: youre anual bounse"))
Vaction = int(input("Please enter: total vaction hours"))
RetirmentFunds = int(input("Please enter: total funds to the retirment funds"))
Year = int(input("how many years you have been working for this company if less then one year enter 0"))

if Salary == 0: 
   print("-------------------------------------------------------------------------")
   raise ValueError("Youre yearly salary shoud be btween 45000 to 125000") 


if Bounse == 0: 
   print("-------------------------------------------------------------------------")
   raise ValueError("Youre yearly bounse shoud be btween 10 to 20 precent") 


if Vaction == 0: 
   print("-------------------------------------------------------------------------")
   raise ValueError("Youre yearly vaction  shoud be atleast  96 hours") 

def vaction_1(vac):
        op1 = 1 + 110 / 100
        vac1 = vac * op1
        return vac1
      
def vaction_2(vac):
        op2 = 1 + 120 / 100
        vac2 = vac * op2
        return vac2
      
     
def vaction_3(vac):
        op3 = 1 + 130 / 100
        vac3 = vac * op3
        return vac3
      
     
    
def vaction_4(vac):
        op4 = 1+ 140 / 100
        vac4 = vac * op4
        return vac4
      

     
def vaction_5(vac):
        op5 =  1 + 150  / 100
        vac5 = vac * op5
        return vac5
      


employee_1 = FinmanceEmployesWage(Salary,Bounse,Vaction,RetirmentFunds)
if Year == 1:
    employee_1.vaction_1(Vaction)
elif Year == 2:
    employee_1.vaction_2(Vaction)
elif Year == 3:
    employee_1.vaction_3(Vaction)
elif Year == 4:
    employee_1.vaction_4(Vaction)
elif Year == 5:
    employee_1.vaction_5(Vaction)

employee_1.bounse()
employee_1.retirment_funds()
employee_1.print_all()




--------------------
File: 007_public_acces_modfire.py
# public acces modfire

class PublicAcaccesModfire:
    def __init__(self, first_name, last_name, base_salary, bounse , precentge):
        self.first_name = first_name
        self.last_name = last_name
        self.base_salary = base_salary
        self.bounse = bounse
        self.precentge = precentge
    def get_monthly_gross(self):
        return self.base_annual_salary / 12
    
    def get_statered_anual_bounse_amount(self):
         return self.base_annual_salary * (self.bounse_percentage/100)
    
def main ():
    print("hello from main")
    employee1 = PublicAcaccesModfire("kara","smith",1000,2000) # this is public because we can accese it when we do employee1.

if __name__ == "__main__":
    main()






--------------------
File: 008_PrivateAcccessModfires
class PrivateAcccessModfires:
    #somtimes you dont want the user to modfiy the instance var so you use the PrivateAcccessModfires 
    def __init__(self, first_name, last_name, base_salary, precentge):
        self.first_name = first_name
        self.last_name = last_name
        self.base_salary = base_salary
        self.precentge = precentge
        #we will create one private instance var called bounses
        self.bounse = 10
    def get_monthly_gross(self):
        return self.__base_annual_salary / 12
    
    def get_statered_anual_bounse_amount(self):
         return self.base_annual_salary * (self.__bounse / 100)
    
    # crating a private method
    def __private_method(self):#add 2 __ before the name of the method yet there is certain namews u cant like str len etc
           return 111-222-333
def main ():
    print("hello from main")
    employee1 = PrivateAcccessModfires("kara","smith",1000,2000) # this is public because we can accese it when we do employee1.

if __name__ == "__main__":
    main() 




   
    

--------------------
File: 009_inhertains_part_1.py
class Employee: # we can to reffer to this class base  and parrent class
  def __init__(self,first_name,last_name,emp_id,yers_of_exp):
    self.first_name = first_name
    self.last_name = last_name
    self.emp_id = emp_id
    self.yers_of_exp = yers_of_exp
     
  
  def get_monthly_salary(self):
     pass
 
  def get_annual_bounse(self):
    pass
class FullTimeMangmentEmployee(Employee):
     mangment_bounse_precntage = 20
     def __init__(self,first_name,last_name,emp_id,yers_of_exp, annual_salary): # if you want to add more info you cfan like i will do in the following by adding the instance variable called annual_salary
        super().__init__(self,first_name,last_name,emp_id,yers_of_exp) # we can add the name of the class yet we added the supper function because when we change the name of the class we dont need to adjust it 1 by 1
        self.annual_salary = annual_salary

     def get_monthly_salary(self):
        return round(self.annual_salary / 12, 2)
     
     def get_annual_bounse(self):
        std_bounse = self.annual_salary * (FullTimeMangmentEmployee.mangment_bounse_precntage / 100)
        exp_bounse = std_bounse * (self.yers_of_exp / 100)
        return std_bounse + exp_bounse




--------------------
File: 010_inhertance_project.py
class PayrollProcessor:
   
   def __init__(self, payroll_date):
      self.payroll_date = payroll_date

   def print_payroolrequest(self, list_of_employees):
      print("Payroll Report:{} ".center(50,"-").format(self.payroll_date))#print(formate)

      for emp in list_of_employees:
           print("{}{} : {:.2f}".format(emp.first_name , emp.last_name, emp.get_monthly_salary()))
   def print_annual_bounse(self ,list_of_employees):
      print("Annual Bonuse Report : {}".center(50, "-").format(self.payroll_date))
      for emp in list_of_employees:
           print("{}{} : {:.2f}".format(emp.first_name , emp.last_name, emp.get_monthly_salary()))

class Employee: # we can to reffer to this class base  and parrent class
  def __init__(self,first_name,last_name,emp_id,yers_of_exp):
    self.first_name = first_name
    self.last_name = last_name
    self.emp_id = emp_id
    self.yers_of_exp = yers_of_exp
     
  def get_monthly_salary(self):
     pass
 
  def get_annual_bounse(self):
    pass
 
class FullTimeMangmentEmployee(Employee):
     mangment_bounse_precntage = 20
     def __init__(self,first_name,last_name,emp_id,yers_of_exp, annual_salary): # if you want to add more info you cfan like i will do in the following by adding the instance variable called annual_salary
        super().__init__(first_name,last_name,emp_id,yers_of_exp) # we can add the name of the class yet we added the supper function because when we change the name of the class we dont need to adjust it 1 by 1
        self.annual_salary = annual_salary

     def get_monthly_salary(self):
        return round(self.annual_salary / 12, 2)
     
     def get_annual_bounse(self):
        std_bounse = self.annual_salary * (FullTimeMangmentEmployee.mangment_bounse_precntage / 100)
        exp_bounse = std_bounse * (self.yers_of_exp / 100)
        return std_bounse + exp_bounse


class FullTimeSalryiedEmployee(Employee):
     employee_bounse = 5
     def __init__(self,first_name,last_name,emp_id,yers_of_exp, annual_salary): # if you want to add more info you cfan like i will do in the following by adding the instance variable called annual_salary
        super().__init__(first_name,last_name,emp_id,yers_of_exp) # we can add the name of the class yet we added the supper function because when we change the name of the class we dont need to adjust it 1 by 1
        self.annual_salary = annual_salary

     def get_monthly_salary(self):
        return round(self.annual_salary / 12, 2)
     
     def get_annual_bounse(self):
        emp_std_bounse = self.annual_salary * (FullTimeSalryiedEmployee.employee_bounse / 100)
        emp_exp_bounse = emp_std_bounse * (self.yers_of_exp / 100)
        return emp_std_bounse + emp_exp_bounse


class HourlyContractor(Employee):
     contracter_bounse_precentage = 0.00
     weekly_work_hour = 40
     def __init__(self,first_name,last_name,emp_id,yers_of_exp, hourly_rate): # if you want to add more info you cfan like i will do in the following by adding the instance variable called annual_salary
         super().__init__(self,first_name,last_name,emp_id,yers_of_exp) # we can add the name of the class yet we added the supper function because when we change the name of the class we dont need to adjust it 1 by 1
         self.hourly_rate = hourly_rate

     def get_monthly_sal(self):
        return round((HourlyContractor.weekly_work_hour * 4)* self.hourly_rate)
     
class HourlyEmployee(Employee):
     contracter_bounse_precentage = 2
     weekly_work_hour = 40
     def __init__(self,first_name,last_name,emp_id,yers_of_exp, hourly_rate): # if you want to add more info you cfan like i will do in the following by adding the instance variable called annual_salary
         super().__init__(self,first_name,last_name,emp_id,yers_of_exp) # we can add the name of the class yet we added the supper function because when we change the name of the class we dont need to adjust it 1 by 1
         self.hourly_rate = hourly_rate

     def get_monthly_sal(self):
        std_bounse = (HourlyEmployee.weekly_work_hour * 4) * self.hourly_rate * 12 * (self.employee)
        exp_bounse = std_bounse * (self.yers_of_exp / 100)
        return round((HourlyEmployee.weekly_work_hour * 4)* self.hourly_rate)


class FullTimeSalariedSalesEmployee(FullTimeSalryiedEmployee):
    emp_bounse_precenatge = 3
    weekly_work_hours = 40
    
    def __init__(self,first_name,last_name,emp_id,yers_of_exp , annual_salary , commestion_precntage): 
       super().__init__(first_name,last_name,emp_id,yers_of_exp, annual_salary)
       self.annual_salary = annual_salary
       self.commestion_precntage = commestion_precntage

    def get_monthly_salariyes (self):
       std_bounse = self.annual_salary * (self.yers_of_exp / 100)
       exp_bounse = std_bounse * (self.yers_of_exp)
       return round(std_bounse + exp_bounse)
    


mangment_employee_1 = FullTimeMangmentEmployee("aljawharah","alqhatani", 1001, 5, 1097)
salaried_employee_1 = FullTimeSalryiedEmployee("khalid" , "alqhatani" , 1010, 6 , 12000)
sales_employee_1 = FullTimeSalariedSalesEmployee("sari" , "alqhatani" , 1010, 8, 12000, 5)

list_of_employees = [mangment_employee_1 , salaried_employee_1 , sales_employee_1 ]
payroll = PayrollProcessor("07/01/2023")
payroll.print_payroolrequest(list_of_employees)

--------------------
File: 011_rock_paper_sizzors.py
import random
print("Rock Papper scissors Game")
class Computer:
 x = ""
 def __init__(self,amount_rounds):
   self.amount_rounds = amount_rounds

class User(Computer):
  def __init__(self , amount_rounds, user_choice = ""):
     super().__init__(amount_rounds)
     self.user_choice = user_choice

  def check_winner(self):
      user_score = 0
      computer_score = 0
      for round in range (0 , self.amount_rounds):
         game = ["rock","paper","scissors"]
         Computer.x = random.choice(game)

         user_choice = input("Rock Paper or Scissors")
         self.user_choice = user_choice
    
         if self.user_choice == Computer.x:
            print("You:", self.user_choice, "| Computer:", Computer.x)
            print("this round is a tie")

         elif self.user_choice == "rock" or self.user_choice == "Rock" and Computer.x == "scissors" or Computer.x =="scissors":
            print("You:", self.user_choice, "| Computer:", Computer.x)
            print("You won this round!")  
            user_score = user_score + 1

         elif self.user_choice == "rock" or self.user_choice == "Rock" and Computer.x == "paper" or Computer.x == "Paper":
            print("You:", self.user_choice, "| Computer:", Computer.x)
            print("You lost this round!")  
            computer_score = computer_score + 1

         elif self.user_choice == "paper" or self.user_choice == "Paper" and Computer.x == "rock" or Computer.x =="rock":
            print("You:", self.user_choice, "| Computer:", Computer.x)
            print("You won this round!")  
            user_score = user_score + 1

         elif self.user_choice == "paper" or self.user_choice == "Paper" and Computer.x == "scissors" or Computer.x == "Scissors":
            print("You:", self.user_choice, "| Computer:", Computer.x)
            print("You lost this round!")  
            computer_score = computer_score + 1

         elif self.user_choice == "paper" or self.user_choice == "Paper" and Computer.x == "rock" or Computer.x =="rock":
            print("You:", self.user_choice, "| Computer:", Computer.x)
            print("You won this round!")  
            user_score = user_score + 1

         elif self.user_choice == "scissors" or self.user_choice == "Scissors" and Computer.x == "paper" or Computer.x == "Paper":
            print("You:", self.user_choice, "| Computer:", Computer.x)
            print("You lost this round!")  
            computer_score = computer_score + 1

         elif self.user_choice == "scissors" or self.user_choice == "Scissors" and Computer.x == "rock" or Computer.x == "Rock":
            print("You:", self.user_choice, "| Computer:", Computer.x)
            print("You lost this round!")  
            computer_score = computer_score + 1
      if user_score > computer_score:
         print("[game summary] Your points:",user_score,"| computer points",computer_score,"\n You won")
      elif user_score < computer_score:
            print("[game summary] Your points:",user_score,"| computer points",computer_score,"\n You lost")
      else:
            print("[game summary] Your points:",user_score,"| computer points",computer_score,"\n It was a tie")




rounds = int(input("How many rounds would you like to play"))

computer_choise = User(rounds)
computer_choise.check_winner()




                  
         

--------------------
File: 012_math_module.md
# Math module 
there are bunch of commands we  will focuse on we will curntly work on ceill floor trunc and factorial and sqrt hypot
## example
```python
print(math.ceill(3.6)) # the output is 4
print(math.floor(3.6)) # the output is 3
print(math.trunc(3.6)) # the output is 3
print(math.factorial(3) # the output is 6
print(math.sqrt(16)) # the output is 4
print(math.hypot(3,4)) # the output is 5
```
### Ceil()
#### ceil always round to the number next to it never down
### floor()
#### floor always round to the number next to it never up
###  trunk() 
#### trunk always remove the decimle point and never rounds up 
### factorial()
#### it multipliyes all numbers smaller then the number example factorial of 4 is 4 * 3 * 2 *1
### sqrt()
#### is the square root of a number
### hypot()
#### when you have a triangle you give it the to smaller angles and it will give you the larger one

--------------------
File: 013_random_modules.md
# Random Modules
 the most used function in the random module is caled random 
## example
```python
import random 
print(random.random) 
```
### you can detriment the seed by the seed function 
## example
```python
random.seed(0)
print(random.random) 
```
### now the seed is zero it cant change
### but sometimes i want to chiose a specfice number or word from a list i can use the seed function
  
## example
```python
numbers =  [1,2,3,4]
names = ["khalid","Aljawahrah","sari"]
print(random.choise(numbers))
print(random.choise(names))
```
### yet somtimes i want a charcter from a long string or number from a huge num i can still use the choise func 
## example
```python
random.choise("Iamkhalidandiamsmart")
random.choise(123456789)
```
### the choice function return duplicates yet somtimes you dont wnat that you can use the sample function 
## example
```python 
names = ["khalid","Aljawahrah","sari"]
print(random.sample(names , 2)
```
### this will give me a uniq person 100% and return this in a new list when you add a number larger then the numbers in the list it will return a eror

--------------------
File: 014_platform_module.md
# Platform module
platform showes you youre operating system (OS) and python version and the hardware you are using
there a lot of command yet we will focuse on now is the platform command, the platfortm command showes you the platform you are using
## Example
```python
import platform
print(platform.platform())
``` 
## this will output youre full OS
yet some times you will not need al of that information so you could use the system command
## Example
```python
print(paltform.system())
```
### Somtimes you don't care about the OS and you want the hardeware you could use the matchine command
## Example
```python
print(paltform.machine())
``` 
## this will output youre matchine type
what if you want the proccer you could use the processor command
## Example
```python
print(paltform.processor())
``` 
### what if you dont care about the devise and what information about the version of python you are usiing you could use the implementaion command
## Example
```python
print(paltform.python_implementaion)
```
### this will output the version of python that you are using
some times you dont want the python version as a string you want it as a tuple you could use the version_tuple command
### Example
```python
 print(platform.python_version_tuple())
```
### this will output he python version not as a string yet as a tuple


--------------------
File: Git.md
# Git
# Table of Contents
1. [Interduction to git](#example)
2. [interduction to the git init command](#example2)
3. [interduction to the git status command](#third-example)
4. [interduction to the git add command](#fourth-examplehttpwwwfourthexamplecom)
5. [interduction to the git log command](#fith-example)

## Interduction to git
 `Git` is a way to track changes it a computer file-folder what ever you what and `git` is generally used for `source code management` in software development
## The git init command
The `git init` basicliy creates a new `Git repository ` 
## The git status command
the `git status` command basicliy showes you what is the `state of the file`
## the git add command
the `git add` command marks changes to be included in the next commit
## the git log command 
the `git log` command showes you the history of the `repository's-folder`

# Examples

--------------------
File: projrct.py

# Create a class Book with attributes like title, author, and status (available or borrowed). Use encapsulation (private attributes) and provide getter and setter methods for the attributes.
# Create a class Borrower with attributes like name, borrowed_books (a list to store books the borrower has borrowed). Again, use encapsulation and provide getter and setter methods.
# Create an abstract class Library that has methods like add_book, add_borrower, borrow_book, and return_book. The methods should be declared but not implemented.
# Create a class LibrarySystem that inherits from the Library abstract class. Implement the methods defined in the Library class. Use composition to manage the relationship between books and borrowers.
# Make sure to use proper access modifiers (public, private, and protected) for attributes and methods.
# Tips:

# Break down the project into smaller tasks and focus on one task at a time.
# Use comments to describe what each class and method does.
# Test your code frequently to ensure everything works as expected.
# This project will help cover the following topics:

# Polymorphism
# Abstract classes
# Public, private, and protected access modifiers
# Encapsulation
# Composition and aggregation
# By working on this project, the student will have a better understanding of the OOP concepts that need more study or haven't been covered yet in the PCAP exam preparation.
class Library:
    def __init__(self, user_option,title,author,name,borrowed_book =  {}):
        self.__user_option = user_option
        self.__title = title
        self.__author = author
        self.__name = name
 
      
class Borrower(Library):
         def __init__(self, user_option,title,author,name,borrowed_book = []):
            super().__init__(user_option,title,author,name,borrowed_book = [])
      

         def Show_bowwerd_book(self):
            if self.borrowed_book == 0:
                print("You did not borrow any books")
            else:
                print("--Youre name is", self.name , "and you have borrowed",len(self.borrowed_book) , "and they are \n", self.borrowed_book )

class Add_Book(Library):
    def __init__(self, user_option,title,author,name,borrowed_book = []):
            super().__init__(user_option,title,author,name,borrowed_book = [])

    def book_adder(self):
          self.borrowed_book[self.__title,self.__author] 

class Ret_Book(Library):
    def __init__(self, user_option,title,author,name,borrowed_book = []):
        super().__init__(user_option,title,author,name,borrowed_book = [])
 
    def delete_book(self):
          self.borrowed_book.pop(self.__author)
    

option = input ("what do you want")
if option == " add a book":
     user_1 = Add_Book
     user_1.book_adder()
elif option == "view books":
     user_1 = Borrower
     user_1.Show_bowwerd_book
     Ret_Book()
elif option == "return a book":
     user_1 = Ret_Book
     user_1.delete_book

else:
     raise ValueError("This option is not curntly avalible")

--------------------
File: strings_and_random_projeect_015
import random
import string
print("-- Password genrator --")
def password_genrator(length,digit,use_spe_char):
        random_pass = []
        cmp_lenght = length - 1
        if use_spe_char == "y" and digit == "y":
              for lenth in range(0,length):
              
                special_char = random.choice("!@#$%^&*()_+")
                random_pass.append(special_char)

                number_random = str(random.randint(0, 9)) 
                random_pass.append(number_random)

                alqhabet_random = random.choice(string.ascii_letters)
                random_pass.append(alqhabet_random)
                random.shuffle(random_pass)
                "".join(random_pass)
                if lenth == cmp_lenght:
                   return random_pass
        elif use_spe_char == "y" and digit == "n":                    
                for lenth in range(1,length):
                    special_char = random.choice("!@#$%^&*()_+")
                    random_pass.append(special_char)

                    alqhabet_random = random.choice(string.ascii_letters)
                    random_pass.append(alqhabet_random)
                    
                    random.shuffle(random_pass)
                    "".join(random_pass)
                    return random_pass
 
        elif use_spe_char == "n" and digit == "y":                    
                for lenth in range(1,length):
                    number_random = str(random.randint(0, 9)) 
                    alqhabet_random = random.choice(string.ascii_letters)

                    random.shuffle(random_pass)
                    "".join(random_pass)
                    if lenth == length:
                        return random_pass

      

while True:
    option = input("Choose option: \n 1: genrator password \n 2: exit the program \n Your choice:")
    if option == "1":
        pass_len = int(input("Provide password length"))
        digits = input("use digits (y/n)")
        use_spe_char = input("use spetial charchter (y/n)")
        password_genrator(pass_len,digits,use_spe_char)
        print("Genrated password: ", random_pass)

    elif option == "2":
        print("Bye!")
        break
    else:
        raise ValueError("Please enter a correct value")

--------------------
File: Budget_Tracker.py
output_file = open("extension.bin", "w", encoding="UTF-8")


Rent=float(input("What is youre Rent:"))
Utilities=float(input("What is youre Utilities amount"))
Groceries=float(input("What is youre Groceries amount"))
Transportation=float(input("What is youre Transportation amount"))
Entertainment=float(input("What is youre Entertainment amount"))
list_of_expnses={"Rent": Rent,
                "Utilities":Utilities,
                "Groceries":Groceries,
                "Transportation":Transportation,
                "Entertainment":Entertainment,
                # List of erxpnses
}
if Rent > 0 : 
    raise ValueError ("you cant use negative number") # eror checking for the list

elif Utilities > 0 :
   raise ValueError ("you cant use negative number") 

elif Groceries > 0 :
   raise ValueError ("you cant use negative number") 
elif Transportation > 0 :
   raise ValueError ("you cant use negative number") 
elif Entertainment > 0 :
   raise ValueError ("you cant use negative number") 
source_of_income=int(input("How many sorces of income do you have? "))

list_of_income={} 

for income in range (0 , source_of_income):
    income = income + 1 # That is the loop that is incharge of giving us the expnses and income 
    job="What is youre" ,  income , "source of income"
    user=input(job)
    monthly_wage="How much do you earn on youre " , income , " source of income" 
    monthly_wage_1=int(input(monthly_wage))
    if monthly_wage_1 > 0 :
            raise ValueError("You cannot enter a a value that is negtive")

    list_of_income[user] = monthly_wage_1
total_expnse = Rent + Utilities + Groceries + Transportation + Entertainment
print(list_of_expnses, file=output_file)
print(list_of_income, file=output_file)
output_file.close()

print(list_of_expnses)
print(list_of_income)
budget=int(input("what is youre total budget"))
print("Your total expenses are", total_expnse, "and your budget is", budget) 
if budget==total_expnse:
  print("Youre budget is equal to expnses")

elif budget > total_expnse:
  print("Youre budget is fewer then expnses")

elif budget < total_expnse:
  print("Youre budget is greater then total expnses")

elif total_expnse == 0:
    raise ValueError("You cannot enter a a value that is equal to zero")
elif total_expnse < 0:
       raise ValueError("Total expnses cannot be a  negative  number")

--------------------
File: FIFA_Player_Stats_Analyzer.py
kylian_mbappe = ["kylian mbappé", 24 , " france" , " psg", 91 ]
kylian_mbappe_states = ["kylian mbappé", "PAC", 97 , "SHO", 89 ,"PAS" , 80 , "DRI", 92 , "DEF" , 36 , "PHY", 76]
neymar=["neymar", 31 , " brazile" , " psg", 89 ]
neymar_states =['PAC', 87 , 'SHO', 83 , 'PAS', 85 ,  'DRI', 93 , 'DEF', 37 , 'PHY', 61]
salem_aldawsery = ["salem aldawsery", 31 , "saudi arabia" , "alhilal" , 76]
salem_aldawsery_states =['PAC', 84 , 'SHO', 73 , "PAS", 69 , "DRI" , 81 , "DEF", 52 , "PHY" , 79 ]
amount_time = int(input("how many times do you want to run the app"))


for x in  range (0, amount_time):
 user_info = input("what do you want to compare or searech a player")
 if user_info == "search a player":
      player = input("what player do u want to search")
      if player == "kylian mbappé":
          print(kylian_mbappe)
      elif player == "salem_aldawsery":
          print(salem_aldawsery)
      elif player == "neymar":
          print(neymar)
      else:
        print("sorry we dont have this player availbel")



 if user_info == "compare":
     player_1_cmp = input("how is player 1")
     if player_1_cmp == "salem aldawsery":
         print(salem_aldawsery_states)
     elif player_1_cmp == "kylian mbappé":
         print(kylian_mbappe_states)
     elif player_1_cmp == "neymar":
         print(neymar_states)
     else:
         print("we dont have this player availbel")



     player_2_cmp = input("how is player 2")
     if player_2_cmp == "salem aldawsery":
         print(salem_aldawsery_states)
     elif player_2_cmp == "kylian mbappé":
         print(kylian_mbappe_states)
     elif player_2_cmp == "neymar":
         print(neymar_states)
     else:
         print("we dont have this player availbel")


--------------------
File: Personal_Finance_Management_Application.py
import json
import csv
import datetime
import re
from modles import Transaction , Statement , statemen_from_json, transaction_from_json,transaction_amount,ending_balance
data = {}
transactions = []
Statements = []

try:
    with open('transactions.json') as json_file:
        data =  json.load(json_file)
        for info in data["Transaction"]:
            transactions.append(transaction_from_json(info))

except:
    print("Exception")
def getFloat(amount_str):
    amount_str = amount_str.split(".")
    amount = ""
    for num in amount_str:
        amount = amount + num
    amount = amount.split(",")
    amount = float(amount[0] + "." + amount[1])
    return amount
with open("export.csv") as csv_file:
    csv_reader = csv.reader(csv_file, delimiter = ',')
    line_count = 0
    for row in csv_reader:
        if line_count == 0:
            print("skipped")
        else:
            line_count = line_count + 1
            if len(row) > 0:
                date = datetime.datetime.strptime(row[0],"%Y-%M-%d").date()
                account_num = row[1].split(" ")
                account_num = account_num[len(account_num)-1]
                name = row[1].replace(account_num, "")
                transaction = Transaction(
                    name,
                    transaction_amount,
                    date,
                    account_num,
                    ending_balance

                )
                exists = False
                for transfer in transactions:
                    if transfer.date == transaction.date:
                         if transfer.name == transaction.name:
                              if transfer.amount == transaction.amount:
                                   exists = True
                if exists != True:
                    transactions.append(transaction)


        
with open('transactions.json', 'w') as json_file:
     data = {}
     data ["Transactions"] = []
     for transfer in transactions:
          data ["Transactions"] .append(transfer.serialize())
     json.dump(data, json_file, sort_keys=True, indent=4)

--------------------
File: To_do_list.py
                                           #requarments
# Project: To-Do List Application
# The goal of this project is to create a simple application that helps the user manage their to-do list. The application should have the following features:
# 1. Task input: The user should be able to enter the tasks they need to complete.done
# 2. Task display: The user should be able to view a list of all the tasks they have entered.done
# 3. Task completion: The user should be able to mark a task as complete.
# 4. Task deletion: The user should be able to delete a task from the list.
# 5. Task prioritization: The user should be able to assign a priority level (high, medium, low) to each task, and the tasks should be displayed in order of priority.
# 6. Saving and loading data: The application should save the data entered by the user to a file, so that it can be loaded later.
# To fulfill these requirements, you will need to use the following Python concepts and features:
# * Variables and data types (e.g. integers, strings, lists)
# * Input and output (e.g. using the input function and printing results)
# * Control structures (e.g. if statements, loops)
# * Functions and modules
# * File input/output (e.g. using the open and write functions)
# * Data structures (e.g. lists, dictionaries)
#code :
import os
import pickle

loaded_data=[]
taskes_high_priority = []
task_medium_prioriy = []
task_low_priority = []
all_task = []
while True:
    options = input("what do you want to do enter as a task or veiw youre taskes or mark a task as complete if you want to stop the app press q :")
    if options == "q":
         print("Thank you for using the app i hope you had a great time")
         break
    if options == "enter a new task":
          priority = input ("Is the task high priority or medium priority or low priority    :")
          if priority == "high":
               high_priority_task = input ("what is the task that you want to add")
               taskes_high_priority.append(high_priority_task)
               all_task.append(high_priority_task)
          if priority == "medium":
                medium_priority_task = input ("what is the task that you want to add")
                task_medium_prioriy.append(medium_priority_task)
                all_task.append(medium_priority_task)
          if priority == "low":
                low_priority_task = input ("what is the task that you want to add")
                low_priority_task.append(low_priority_task)
                all_task.append(low_priority_task)  
          elif priority == "q":
             print("Thank you for using the app i hope you had a great time")
             break             
          

    if options == "veiw taskes":
      veiw_task_priortey = input ("what taskes do you want to veiw all taskes or high priorty taskes or medium priorty taskes or low priorty task")
      if veiw_task_priortey == "all taskes":
           print(all_task)
      elif veiw_task_priortey == "high priorty taskes":
           print (high_priority_task)
      elif veiw_task_priortey == "medium priorty taskes":
           print(medium_priority_task)
      elif veiw_task_priortey == "low priorty taskes":
           print(low_priority_task)
      else:
           raise ValueError ("sorry we dont have", veiw_task_priortey,"please enter a neiw value")
    elif options == "mark a task as complete":
        complete_task_number = 0
        complete_task_number = int(input("witch task do you want to mark as complete    :"))
        complete_task_number = complete_task_number - 1
        del all_task[complete_task_number]
    else:
         raise ValueError ("sorry we dont have this option avalible please add a other one")
data_file = "data.txt"
if os.path.exists(data_file):
    with open(data_file, "rb") as file:
        loaded_data = pickle.load(file)
# Save tasks to the file:


--------------------
File: calculator.py
# ####
# 1. Create a simple calculator in Python.
# 2. The calculator should be able to perform basic arithmetic operations such as addition, subtraction, multiplication, and division.
# 3. The user should be able to input two numbers and choose the operation they want to perform.
# 4. The calculator should display the result of the calculation.
# 5. You can add extra features like performing square root, percentage, etc.
# This project will cover the following areas of PCEP (Python Certified Entry-Level Programmer):
# * Input and Output
# * Data Types
# * Variables
# * Operators
# * Conditional statements
# * Loops
# The project will help you strengthen your understanding of basic concepts in Python and also improve your problem-solving skill
import math
print("Welcome to the calculator")
while True:
    opreator = input("what is youre opreation")
    if opreator == "√": 
        squar_root=input("what number do you wnat to preform the square root operator on")
        print (math.sqrt(squar_root))
    else:
        number_1 =int(input("what is youre first nuber"))
        number_2 =int( input("what is youre second nuber"))
        if number_1 or number_2 < 0 :
             raise ValueError ("sory we dont suport negative numbers please enter a postive number")
           
        elif opreator == "+" :
             print(number_1 + number_2)
        elif opreator == "*":
            print(number_1 * number_2)
        elif opreator == "/":
            print(number_1 / number_2)
        elif opreator == "%":
             print(number_1 / number_2 * 100)
        else:
               raise ValueError("sory the opreator you entered is invalid")
 

--------------------
File: introduction-to-markdown.md
# Introduction to Python
In this course I will learn the basics of OOP programming.

## First Step
In the first **step** I will _learn_ how to create a new class in Python. To create a class, write the following Python code.
```python
class Student:
    def __init__(self, first_name, last_name):
        self.first_name = first_name
        self.last_name = last_name

std = Student("Sari", "Naif")

```

--------------------
File: stock _analsis.py





#Project: Stock Market Data Analysis and Visualization
# Requirements:
# 1. Implement a command-line application that retrieves stock market data from an API (e.g., Alpha Vantage or Yahoo Finance) and stores the data in a local file (CSV or JSON format).
# 2. Use loops, list comprehensions, and functions effectively.
# 3. Implement error handling for potential issues, such as invalid API responses or incorrect user input.
# 4. Use an external library (e.g., matplotlib) to create graphs and visualizations of the stock market data.
# 5. Analyze the data and provide insights, such as average price, trends over time, and price comparisons between different stocks.
# Tips:
# 1. Create functions to retrieve stock market data for a given stock symbol and time range (e.g., past week or month).
# 2. Use the requests library to interact with the API and the json or csv library to parse the API responses and store the data in a local file.
# 3. Create functions to calculate statistics (e.g., mean, median, and mode) for the retrieved stock market data.
# 4. Use the matplotlib library to create graphs and visualizations, such as line graphs for stock prices over time or bar graphs for price comparisons between different stocks.
#############################################################
#CODE
#############################################################
#Caling the libaryis
import json
import requests
import datetime as dt
from matplotlib import pyplot as plt
from bs4 import BeautifulSoup
from matplotlib import style
from pandas_datareader import data as pdr

#Gets ticker symbol 
stock_code = input ("Enter the name of the stock")
url = "https://s.yimg.com/aq/autoc"
parameters = {'query': stock_code, 'lang': 'en-US'}
response = requests.get(url = url, params = parameters)
data = response.json()
company_code = data['ResultSet']['Result'][0]['symbol']
#Create the graph
def graph_generator ():
   start = dt.datetime(2019 , 1, 1)
   end  =  dt.datetime(2023, 3, 24)
   stock_graph = pdr.DataReader(company_code, "yahoo",start,end)
   style.use("ggplot")
   stock_graph["Close"].plot(figsize=(8,8), label = company_code)
   plt.show()


def web_contetnt_html(web_content,class_path, value):
    web_content.find_all(value)
    try: 
        if value != "None": 
            spans = web_contetnt_html[0].find_all(value)
            texts = [spans.get_text() for span in spans]
        else:
            texts = []
    except IndexError:
        texts=[]

    return texts , web_content


def main():
    for stock_code in Stock :
      stock_price,change,volume,latest_pattern , one_year_target, Error = real_time_price(stock_code)


# function to get the stocks 
def real_time_price(stock_code):
    url = "https://finance.yahoo.com/quote/" + stock_code +"?p=" + stock_code +"&.t.src=fin-srch"
    try:
       response = requests.get(url)
       web_content = BeautifulSoup(response.text, "lxml")
       texts  = web_contetnt_html(web_content, "D(ib) Mend(20px)", "fin-streamer")
       print(texts)
       price , change = texts[0], texts[1] +""+texts[2]
       web_contetnt_html(web_content, "", "fin-streamer")
       return change , volume , latest_pattern , one_year_target , stock_code
    except (ConnectionError):
         price , change , volume , latest_pattern, one_year_target = [], [], [] ,[]
         raise ConnectionError("There is a connection error please try again latter")
    
Stock = ["ES=F", "AAPL"]
main()
graph_generator()
data = {
    "stock_symbol":"AAPL",
    "start_date": "2019 , 1, 1",
    "end_date":"2023, 3, 24",
    "open":"123.3600",
    "high":"125.3600",
    "low":"122.880",
    "close":"125.2900",
    "volume":"3809264"
}

with open("data.json", "w") as json_file:
    json.dump(data, json_file)

















--------------------
File: wether_forcast_app.py


import requests
from datetime import datetime






location = input("enter city name")


if location is None:
   raise ValueError("please enter a city")
api_key = "c6af695e45b0d90e5778bdc480c6a4dd"
api_link  =f" https://api.openweathermap.org/data/2.5/weather?q={location}&appid={'c6af695e45b0d90e5778bdc480c6a4dd'}"
complete_api_link = f"https://api.openweathermap.org/data/2.5/forecast?q={location}&appid={'c6af695e45b0d90e5778bdc480c6a4dd'}"



if ['cod'] == 404 :
   raise ValueError("sorry invalid city please add a other city")


api_response = requests.get(api_link)
api_data = api_response.json()


temp_city =((api_data["main"]["temp"]-273.15))
weather_desc = api_data['weather'][0]["description"]
hmdt = api_data["main"]["humidity"]
wind_spd = api_data["wind"]["speed"]
date_time = datetime.now().strftime("%d %b %y | %I:%M:%S %p")




##eror checking#










print("------------------------------------------------------------")#this print statments is for desighn benfits
print("weather stats for -{} || {}".format(location.upper(), date_time))
print("------------------------------------------------------------")
print("current temperature is: {:.2f} deg C".format(temp_city))
print("current weather desc  :",weather_desc)
print("current hummdity  :",hmdt, "%")
print("current wind speed  :", wind_spd,"kmph")






--------------------
File: 001_Introduction_to_oop.py
class Company:
    def __init__(self, name, year):
        self.name = name
        self.year = year
 
class Computer:
    def __init__(self, name, color, ram, comp):
        self.name = name
        self.color = color
        self.ram = ram
        self.company = comp

class Person:
   def __init__(self, f_name , l_name, age, cmp): # Constructor
        self.first_name = f_name
        self.last_name = l_name 
        self.age = age
        self.computer = cmp

aljawharah = Person("aljawharah", "alqahtani", "14", Computer("macbook", "blue", 128, Company("khalid_law", 1876) ))
print(aljawharah.first_name)
print(aljawharah.last_name)
print(aljawharah.age)
print(aljawharah.computer.name)
print(aljawharah.computer.color)
print(aljawharah.computer.ram)
print(aljawharah.computer.company.name)
print(aljawharah.computer.company.year)




#khalid = Person("khalid", "alqhatani", 15, Computer("msi_titan_gt77", "black", 8192))
#print(khalid.computer.name)
#print(khalid.computer.ram)
#khalid = Person("Khalid", "Alqhatani", 15)
#print(khalid.first_name)
 

#msititan = Computer("msititan", "black", 128)
#msi_titan_gt77 = Computer("msi_titan_gt77", "mate_black", 128)
#print(msititan.name, msititan.color, msititan.ram)
#print(msi_titan_gt77.name, msi_titan_gt77.color,msi_titan_gt77.ram)

--------------------
File: 002_Calling_without_attributes_oop.py
class Student:
    def __init__(self, sid, name, age):
        self.sid = sid
        self.name = name
        self.age = age

naif = Student(10, "Naif", 20)
badr = Student(20, "Badr", 30)
khalid = Student(30, "khalid", 13)
sari = Student(106, "sari", 4) 
# class Student:
#     def __init__(self):
#         self.sid = 0
#         self.name = "Unknown"
#         self.age = 0

# naif = Student()
# naif.sid = 10
# naif.name = "Naif"
# naif.age = 20

# badr = Student()
# badr.sid = 20
# badr.name = "Badr"
# badr.age = 30

print(naif.name)
print(badr.name)
print(khalid.name)
print(sari.name)
 

--------------------
File: 003_Using_list_with_oop.py
class Student:
    def __init__(self, sid, name, age):
        self.sid = sid
        self.name = name
        self.age = age


students = [
    Student(1, "Khalid", 13),
    Student(2, "Sari", 10),
    Student(3, "Badr", 30)
]

for s in students:
    if s.sid == 2:
        continue
    print(s.sid, s.name, s.age)



--------------------
File: 004_Entring_the _list_while_using_oop.py
class Student:
    def __init__(self, sid, name, age):
        self.sid = sid
        self.name = name
        self.age = age


students = [
    Student(1, "Khalid", 13),
    Student(2, "Sari", 10),
    Student(3, "Badr", 30)
]

print(students[1].sid)
print(students[2].age)

students[0].age = students[1].age
students[1].name = "Naif"

--------------------
File: 005_Using_nested_list_while_using_oop_005
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age


# naif = Person("Naif", 10)

# for p in naif.name:
#     print(p)


p = [
    [Person("Naif", 10), Person("Badr", 20)],
    [Person("Sari", 30), Person("Nasser", 40)],
    [Person("Nora", 30), Person("Aljawhara", 35)]              
]

for x in p:
    for y in x:
        print(y.name, y.age)

--------------------
File: 006_String_formate_while_using_oop.py
class Student:
    def __init__(self, sid, name, age):
        self.sid = sid
        self.name = name
        self.age = age

students = [
    Student(10, "Khalid", 1024),
    Student(20, "Aljwhara", 512),
    Student(30, "Tawfiq", 4096)
]

for student in students:
    print("<"+str(student.sid)+">", "["+student.name+"]", "["+str(student.age)+"]")
 

--------------------
File: 007_if_statments_oop.py
# Python OOP Concept: Methods(actions)
# object: 1- attributes
#         2- actions



class Student:
    def __init__(self, sid, name, age):
        self.sid = sid
        self.name = name
        self.age = age
    
    def print_my_info(self):
        print(self.sid)
        print(self.name)
        print(self.age)
    
    def cmp_age(self, st):
        if self.age > st.age:
            print("self > st")
        elif self.age < st.age:
            print("self < st")
        else:
            print("self = age")


# naif = Student(10, "Naif", 20)
# badr = Student(20, "Badr", 30)

# naif.print_my_info() 
# badr.print_my_info()

# # naif.cmp_age(badr)
# # badr.cmp_age(naif)

# naif.cmp_age(Student(30,"Khalid", 20))


--------------------
File: 008_list_and_loop_oop.py
class Student:
    def __init__(self, sid, name, age):
        self.sid = sid
        self.name = name
        self.age = age
    
    def print_info(self):
        print(self.sid)
        print(self.name)
        print(self.age)

students = [
    Student(10,"Khalid",13),
    Student(20,"Wade",15),
    Student(30,"Aljawarah",12),
    Student(40,"Sari",9)
]

for student in students:
    student.print_info()
    print("--------------------")
    

--------------------
File: 009__functions_inside_methods_oop.py
class Student:
    def __init__(self, sid, name, age):
        self.sid = sid
        self.name = name
        self.age = age
    
    def print_info(self):
        print(self.sid)
        print(self.name)
        print(self.age)
    

def create_new_student():
    return Student(10, "Khalid", 13)

khalid = create_new_student() #.name
print(khalid)


--------------------
File: 010_adding_to_list_oop.py
class Group:
    def __init__(self):
        self.names = []

    def add_person(self, name):
        self.names.append(name) 

    def print_group(self):
        for p in self.names:
            print(p)

g = Group()
g.add_person("Khalid")
g.add_person("wadee")
g.add_person("abdullah")
g.add_person("sari")

g.print_group()
print("-----------------------")
s = Group()
s.add_person("mohammed")
s.add_person("sultan")
s.add_person("faisal")

s.print_group()

--------------------
File: 0116_inertince_oop.py
class Student:
    def __init__(self, first_name, last_name):
        self.first_name = first_name
        self.last_name = last_name
    
    def print_info(self):
        print(self.first_name, self.last_name)


class MathStudent(Student):
    def print_info(self): #override
        print("[", self.first_name, "]-> ", self.last_name)


m1 = Student("Khalid", "Alqahtani")
m2 = MathStudent("Sari", "Alqahtani")

m1.print_info()
m2.print_info()

--------------------
File: 011_nested_classes_while_ading_list.py
class Person:
    def __init__(self, first_name, last_name, age) :
        self.first_name = first_name
        self.last_name = last_name
        self.age = age

class Group:
    def __init__(self):
        self.names = []

    def add_person(self, name):
        self.names.append(name) 

    def print_group(self):
        for p in self.names:
            print(p.first_name , p.last_name , p.age)
            print("--------------------------------")

g = Group()
g.add_person(Person("Khalid", "Alqhatani", 13))
g.add_person(Person("wadee", "Altwlayle", 12))
g.add_person(Person("Sary", "alqhatani", 4))

g.print_group()

print(g.names[1].first_name)

--------------------
File: 012_caling_more_then_once_oop.py
class Group:
    def __init__(self):
        self.names = []
    
    def add_person(self, name):
        self.names.append(name)
    
    def start(self):
        print("--------------------------------------")
        return self
    
    def end(self):
        print("****************************************")
        return self
    
    def print_info(self):
        for name in self.names:
            print(name)
        return self
    
    def my_code(self):
        return "code"


my_group = Group()
my_group.add_person("one")
my_group.add_person("two")
my_group.add_person("three")

my_group.start().print_info().end().my_code()
my_group.start().start().start().print_info().print_info().end().end().my_code()

my_group.start()
my_group.print_info()
my_group.end()

--------------------
File: 013_inheritance_part1_oop.py
class Person:
  def __init__(self, fname, lname):
    self.firstname = fname
    self.lastname = lname

  def printname(self):
    print(self.firstname, self.lastname)


class Student(Person):
    def my_function(self):
        print("student")


class MathStudent(Student):
    def my_math_code(self):
        print("math function")


p = Person("Khalid", "Alqahtani")
s = Student("Sari", "Alqahtani")
m = MathStudent("Aljawharah", "Alqahtani")


p.printname()
s.printname()
m.printname()

# p.my_function()
s.my_function()
m.my_function()

p.my_math_code() # error error
s.my_math_code() # true true
m.my_math_code() # true true

p.firstname = "Khalid"
s.firstname = "Sari"
m.firstname = "Aljawharh"

--------------------
File: 014_ Inheritance_part2.py
 class Pen:
    def __init__(self, name, color, size):
        self.name = name
        self.color = color
        self.size = size

    def write(self, content):
        print("-->", content)
    


class Highliter(Pen):
    def my_highliter(self):
        pass

    def write(self, content):
        print("[[", content)
    
class Pencil (Highliter):
    def my_pencil(self):
        pass 

    def write(self, content):
        print("**", content)


p1 = Pen("Any", "red", 1)
p2 = Highliter("New", "blue", 2)
p3 = Pencil("xyz", "black", 1)

p1.write("Welcome to Python")
p2.write("Welcome to Python")
p3.write("Welcome to Python")


--------------------
File: 015_project_oop.py
class MyString:
    def __init__(self, string):
        self.value = string 
    
    def count_characters(self):
        return len(self.value)

    def count_x_character(self, charcter):
        return self.value.count(charcter)

    def get_first_character(self):
        return self.value[0]

    def get_last_character(self):
        return self.value[-1]

    def get_with_format(self, start, end):
        return start + self.value + end
        
    def print_characters(self):
        for char in self.value:
            print(char)

    def has_character(self, letter):
        return letter in self.value
    
    def is_alpha(self , char):
              if self.value[char].isalpha():
                return True
              else:
                return False
               

    def is_digit(self, index):
        return self.value[index] in "0123456789"

    def is_space(self, user_input):
        if  ' ' in self.value[user_input] == True:
            return True
        else:
            return False

   
x = MyString('We9lcome to Python')
print(x.count_characters())
print(x.count_x_character("e"))
print(x.get_first_character())
print(x.get_last_character())
print(x.get_with_format("<p>", "</p>"))
x.print_characters()
print(x.has_character("W"))
print(x.has_character("z"))
print(x.is_digit(2))
print(x.is_digit(9))
print(x.is_space(2))
print(x.is_space(8))
print(x.is_alpha(2))


# print(x.is_alpha(2))
# print(x.is_alpha(4))
# print(x.is_digit(2))
# MyString attributes(data):
  # value(string)

# MyString services(actions):
    # 01. count_characters
    # 02. count_x_character
    # 03. get_first_character
    # 04. get_last_character
    # 05. get_with_format
    # 06. print_characters
    # 07. has_character
    # 08. is_alpha 
    # 09. is_digit 
    # 10. is_space 
    # 11. has_space
    # 12. has_punctuation (Homework) J


--------------------
File: 016_override_oop.py
class Grade:
    def __init__(self, person, the_class, grade):
        self.person = person
        self.the_class = the_class
        self.grade = grade
   
    def print_info(self):
        print("the person is ", self.person, ",", self.person, " is in grade", self.the_class, " ,", self.person ,"'s grade is", self.grade)

class MyGrade(Grade):
    def print_info(self):
        print("the person is -> ", self.person, ",", self.person, " is in grade -> ", self.the_class, " ,", self.person ,"'s grade is ->", self.grade)
       
class FailedGrade(Grade):
    def print_info(self):
        print("the person is ", self.person, ",", self.person, " is in grade", self.the_class, " ,", self.person ,"failed because their grade is", self.grade)

o1 = Grade("Jojo", "class 9", 100)
o2 = MyGrade("Sari", "class 5", 100)
o3 = FailedGrade("Khalid", "class 0.01", 0)
o1.print_info()
o2.print_info()
o3.print_info()

--------------------
File: 017_inhertiance_overide.py
class Homework:
    def __init__(self,name,grade):
        self.name = name
        self.grade = grade
    
    def print_info(self):
        print("Homework: he name of the person is ", self.name , " and the grade is", self.grade)

class VeryEasyHomework(Homework):
    def print_info(self):
        print("VeryEasyHomework: The name is ", self.name , " and the grade is ", self.grade)

class EasyHomework(VeryEasyHomework):
    def print_info(self):
        print("EasyHomework: The name is ",self.name , "and the grade is" , self.grade)
    


home_work_1 = Homework("aljawahra", 21)
home_work_1.print_info()
home_work_2 = VeryEasyHomework("Khalid", 102)
home_work_2.print_info()
home_work_3 = EasyHomework("sari",-120)
home_work_3.print_info()

--------------------
File: 018_techer_abdullah_example_oop_018.py
class Student:
    def __init__(self, first_name, last_name):
        self.first_name = first_name
        self.last_name = last_name

    def print_info(self):
        print("Student: ", self.first_name, self.last_name)
    

class MathStudent(Student):
    def __init__(self, first_name, last_name, age):
        Student.__init__(self, first_name, last_name)
        self.age = age
    
    def print_info(self):
        print("MathStudent: ", self.first_name, self.last_name, self.age)


class AdvancedMathStudent(MathStudent):
    def __init__(self, first_name, last_name, age, address):
        MathStudent.__init__(self, first_name, last_name, age)
        self.address = address
    

    def print_info(self):
        print("AdvancedMathStudent: ", )


std = Student("Naif", "Saleh")
mstd = MathStudent("Badr", "Abdullah", 20)
astd = AdvancedMathStudent("Sari", "Alqahtani", 10, "KSA")

print(std.first_name)
print(mstd.first_name)
print(astd.first_name)

--------------------
File: 019_shape-inhertains_example_oop.py
class Shape:
    def __init__(self, shape_name):
        self.shape_name = shape_name

    def draw(self):
        print(self.shape_name)


class Rectangle(Shape):
    def __init__(self, height, width):
        Shape.__init__(self, "Rectangle")
        self.height = height
        self.width = width
       
    def draw(self):
        print(self.shape_name, self.height, "X", self.width)

class Triangle(Shape):
    def __init__(self, side):
        Shape.__init__(self, "Triangle")
        self.side = side

    def draw(self):
        print(self.shape_name, self.side )

class Circle(Shape):
    def __init__(self , radius):
        Shape.__init__(self,"Circle")
        self.radius = radius

    def draw(self):
        print(self.shape_name , self.radius)


r = Rectangle(50, 100)
r.draw()

t = Triangle(27)
t.draw()

c = Circle(360)
c.draw()

--------------------
File: 020_super_inhertins-overide-oop.py
class Shape:
    def __init__(self, shape_name):
        self.shape_name = shape_name

    def draw(self):
        print(self.shape_name)


class Rectangle(Shape):
    def __init__(self, height, width):
        super().__init__("Rectangle")
        self.height = height
        self.width = width
       
    def draw(self):
        print(self.shape_name, self.height, "X", self.width)

class Triangle(Shape):
    def __init__(self, side):
        super().__init__("Triangle")
        self.side = side

    def draw(self):
        print(self.shape_name, self.side )

class Circle(Shape):
    def __init__(self , radius):
        super().__init__("Circle")
        self.radius = radius

    def draw(self):
        print(self.shape_name , self.radius)


r = Rectangle(50, 100)
r.draw()

t = Triangle(27)
t.draw()

c = Circle(360)
c.draw()

--------------------
File: 021_question_oop.py
class Person:
    pass

class Student(Person):
    pass

class MathStudent(Student):
    pass



o1 = Person()
o2 = Student()
o3 = MathStudent()

print(isinstance(o3, Student))
print(isinstance(o3, Person))
print(isinstance(o3, MathStudent))

print(isinstance(o2, Person))
print(isinstance(o1, MathStudent))

print(isinstance(3, int))

print(isinstance(o1,(Person, Student))) # tuple
print(isinstance(o2,(Person, Student))) # tuple
print(isinstance(o3,(Person, Student))) # tuple

--------------------
File: 022_inhertains_oop.py
class Person:
    def __init__(self, first_name, last_name, age):
        self.first_name = first_name
        self.last_name = last_name
        self.age = age

class MyPerson(Person):
    def __init__(self, first_name, last_name, age, address):
        super().__init__(first_name, last_name, age)
        self.address = address

class Group:
    def __init__(self):
        self.names = []
    def add(self, person):
        self.names.append(person)

    def print_info(self):
        for person in self.names:
            if isinstance(person, MyPerson):
                print("[", person.first_name, "], ", person.last_name, person.age, person.address)
            elif isinstance(person, Person):
                print("[", person.first_name, "], ", person.last_name, person.age)




group = Group()

# o1 = Person("aljawharah", "LQAHTANI", 12939)
# group.add(o1)

group.add(Person("khalid", "alqahtani", 474))
group.add(MyPerson("khalid","alqhatani",13,"hittin 1378"))

group.print_info()


# o1 = Person("aljawharah", "LQAHTANI", 12939)
# o2 = MyPerson("aljawharah", "LQAHTANI", 12939, "abc")


# print(isinstance(o1, Person))
# print(isinstance(o2, Person))
# print(isinstance(o1, MyPerson))
# print(isinstance(o2, MyPerson))

--------------------
File: 023_class_var_vs_instense_var_oop_26.py
class Student:
    #class variable
    school_name = "My School"
    school_address = "KSA"
    num_of_student = 0

    def __init__(self, name, age):
        self.name = name #instance variable
        self.age = age
        Student.num_of_student = Student.num_of_student + 1


s1 = Student("Sari", 11) #instance object
s2 = Student("Kahlid", 13)
s3 = Student("Aljawharh", 15)

print(s1.name)
print(s2.name)
print(s3.name)

print(Student.school_name)
print(Student.school_address)

# instance variable vs class variable

print(Student.num_of_student)

--------------------
File: 024_calculate_insense_var_class_var_oop.py
# instance varaibles vs class variables
# num of instance and num of instance variables

class Person:
    student = "aljawharah"
    num_of_instance = 0
    num_of_instance_variables = 0 
    num_of_class_variables = 4

    def __init__(self, name, grade, theclass):
        self.name = name
        self.grade = grade
        self.theclass = theclass
        self.values = [1, 2, 3, 4]
        Person.num_of_instance = Person.num_of_instance + 1
        Person.num_of_instance_variables = Person.num_of_instance * 4

   
o1 = Person("Sari",99,6)
o2 = Person("aljawahra",48,3)
o3 = Person("khlid",100,6)

print( Person.num_of_class_variables)

print(Person.student)
print(Person.num_of_instance , Person.num_of_instance_variables)

--------------------
File: 025_dumber_oop.py
class App:
    def __init__(self, name, version):
        self.name = name
        self.version = version

    def __str__(self):
        return "The name is " + self.name + "and the version is " + str(self.version)

class Apps:
    def __init__(self):
        self.apps = []
    
    def add_app(self, app):
        if(isinstance(app, App)):
            self.apps.append(app)
        else:
            print("app argument must be an App object")
    
    def print(self):
        for app in self.apps:
            print(app.name, "(", app.version, ")")
    
    def __str__(self):
        result = ""
        for app in self.apps:
            result = result + app.name + " "
        
        return result
    
    def __len__(self):
        return len(self.apps)

    def __contains__(self, name):
        for app in self.apps:
            if app.name == name:
                return True
        return False

# abc = App("Python", 1)
apps = Apps()
apps.add_app(App("ScreenFlow", 1))
apps.add_app(App("Snagit", 2))

print("Snagit``````````" in apps)

apps()

--------------------
File: 026_dumber_oop.py
class Course:
    def __init__(self,instructor,subject,description):
        self.instructor  = instructor
        self.subject = subject
        self.description = description
        self.rating = 0

    def print(self):
        print(self.instructor , self.subject , self.description)
    
    def __str__(self):
        return self.subject + ", " + self.description + ", " + self.instructor

    def set_rating(self,rating):
        self.rating = rating


class Courses:
    def __init__(self):
        self.courses = []

    def add(self, course):
        self.courses.append(course)

    def __len__(self):
        return len(self.courses)

    def __contains__(self, subject):
        for course in self.courses:
            if subject == course.subject:
                return True
        return False

    def print(self):
        for course in self.courses:
            print(course) 

c = Courses()

c.add(Course("sari", "C", "long course"))
c.add(Course("aljawharah","python","good course"))
c.add(Course("khalid","html","very very easy"))

print(len(c))

print("Java" in c)
print("python" in c)

c.print()

--------------------
