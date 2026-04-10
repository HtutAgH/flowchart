graph TD
    Start([Start]) --> InitMax[Load num1 into AX]
    InitMax --> CompMax1{Compare AX, num2}
    CompMax1 -- "AX > num2 (JG)" --> CompMax2{Compare AX, num3}
    CompMax1 -- "AX <= num2 (JLE)" --> LoadMax2[Load num2 into AX]
    LoadMax2 --> CompMax2
    CompMax2 -- "AX > num3 (JG)" --> StoreMax[Store AX in max_num]
    CompMax2 -- "AX <= num3 (JLE)" --> LoadMax3[Load num3 into AX]
    LoadMax3 --> StoreMax
    
    StoreMax --> InitMin[Load num1 into AX]
    InitMin --> CompMin1{Compare AX, num2}
    CompMin1 -- "AX < num2 (JL)" --> CompMin2{Compare AX, num3}
    CompMin1 -- "AX >= num2 (JGE)" --> LoadMin2[Load num2 into AX]
    LoadMin2 --> CompMin2
    CompMin2 -- "AX < num3 (JL)" --> StoreMin[Store AX in min_num]
    CompMin2 -- "AX >= num3 (JGE)" --> LoadMin3[Load num3 into AX]
    LoadMin3 --> StoreMin
    StoreMin --> End([End])
