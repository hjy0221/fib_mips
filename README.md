# fibonacci mips asm
📌 개요

이 프로그램은 MIPS 어셈블리로 구현된 피보나치 수(Fibonacci number) 계산 프로그램입니다.
사용자로부터 정수를 입력받아 재귀 호출(recursion)을 이용하여 해당 번호의 피보나치 값을 계산하고 출력합니다.

📁 파일 설명
main 함수

“Give a number:” 문구 출력

정수 입력받기

입력된 값을 fib 함수에 전달하여 결과 계산

반환된 피보나치 수를 출력

fib 함수

재귀적으로 피보나치 값을 계산

스택을 사용하여 $ra, $s0, $s1 레지스터를 보관

종료 조건:

fib(0) = 0

fib(1) = 1

🧮 알고리즘

피보나치 수열은 다음 점화식을 따른다:

F(0) = 0  
F(1) = 1  
F(n) = F(n-1) + F(n-2)


프로그램 역시 동일한 구조로 재귀 호출을 수행하며,
각 호출 시 스택 프레임을 구성하여 레지스터를 보존한 뒤 연산을 진행합니다.

🔧 실행 방법

MARS 또는 QtSpim을 실행합니다.

MIPS 어셈블리 파일을 열어 로드합니다.

프로그램을 실행하면 다음 메시지가 출력됩니다:

Give a number:


자연수를 입력하면 해당 피보나치 값이 출력됩니다.

🧵 스택 프레임 구조

fib 함수는 다음과 같이 총 12바이트를 스택에 저장합니다:

스택 오프셋	내용
0($sp)	$ra
4($sp)	$s0
8($sp)	$s1

재귀 호출이 끝나면 해당 값을 복구하고 jr $ra를 통해 호출한 곳으로 복귀합니다.

📄 주요 코드 설명
입력 요청 및 입력 받기
li $v0, 4
la $a0, str
syscall          # "Give a number: " 출력

li $v0, 5
syscall          # 정수 입력

피보나치 재귀 호출
addi $a0, $s0, -1
jal fib
add $s1, $zero, $v0    # fib(n-1) 저장

addi $a0, $s0, -2
jal fib                # fib(n-2)
add $v0, $v0, $s1      # fib(n-1) + fib(n-2)

종료 조건 처리
beq $s0, $zero, return0   # fib(0)
beq $s0, $t1, return1     # fib(1)

✔️ 실행 예시

입력:

5


출력:

5
