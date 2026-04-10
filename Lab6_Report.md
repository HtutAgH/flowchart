graph TD
    Start([Start]) --> Init[Load num1 into AX]
    
    subgraph Max Logic
    Init --> Comp1{Compare AX, num2}
    Comp1 -- "JG (AX > num2)" --> Comp2{Compare AX, num3}
    Comp1 -- "JLE (AX <= num2)" --> Load2[Load num2 into AX]
    Load2 --> Comp2
    Comp2 -- "JG (AX > num3)" --> StoreMax[Store AX in max_num]
    Comp2 -- "JLE (AX <= num3)" --> Load3[Load num3 into AX]
    Load3 --> StoreMax
    end

    StoreMax --> Reset[Load num1 into AX]

    subgraph Min Logic
    Reset --> Comp3{Compare AX, num2}
    Comp3 -- "JL (AX < num2)" --> Comp4{Compare AX, num3}
    Comp3 -- "JGE (AX >= num2)" --> Load5[Load num2 into AX]
    Load5 --> Comp4
    Comp4 -- "JL (AX < num3)" --> StoreMin[Store AX in min_num]
    Comp4 -- "JGE (AX >= num3)" --> Load6[Load num3 into AX]
    Load6 --> StoreMin
    end

    StoreMin --> End([End])
