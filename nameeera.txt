.data
insert: .asciiz "Please enter the number of disks "
outcome: .asciiz "\nTotal number of moves are: "
.text   
la $a0,insert     
li $v0,4
syscall    
la $v0,5
syscall
move $a3,$v0
li $a2,2
loop:
li $a1,2
mult $a1,$a2
mflo $a2
sub $a3,$a3,1
bgt $a3,1,loop
sub $a3,$a2,1
la $a0,outcome
li $v0,4
syscall
move $a0,$a3
li $v0,1
syscall    