# Fibonacci in MIPS Assembly

[한국어](#한국어) · [English](#english)

## 한국어

사용자로부터 정수를 입력받아 재귀 호출로 피보나치 수를 계산하고 출력하는 MIPS 어셈블리 예제입니다.

### 동작

1. `Give a number:` 프롬프트를 출력합니다.
2. 정수를 입력받아 `fib` 함수에 전달합니다.
3. `fib(0) = 0`, `fib(1) = 1`을 종료 조건으로 재귀 계산합니다.
4. 계산된 값을 출력합니다.

### 실행하기

`fib.asm`을 MARS 또는 QtSPIM과 같은 MIPS 시뮬레이터에서 열어 실행하세요.

## English

A MIPS assembly example that reads an integer, calculates the corresponding Fibonacci number recursively, and prints the result.

### Flow

1. Print the `Give a number:` prompt.
2. Read an integer and pass it to the `fib` function.
3. Recurse using `fib(0) = 0` and `fib(1) = 1` as base cases.
4. Print the calculated value.

### Run

Open and run `fib.asm` in a MIPS simulator such as MARS or QtSPIM.
