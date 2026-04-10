```mermaid
graph TD
    A[Start] --> B[Set AX = 0, CX = num1]
    C[Add CX to AX] --> D[LOOP instruction: CX = CX - 1]
    D -- "CX != 0" --> C
    D -- "CX == 0" --> E[Store AX in my_sum]
    E --> F[End]
