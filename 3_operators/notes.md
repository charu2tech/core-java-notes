1) Explain about different types of operators? <br>
   a) Assignment operator. <br>
   b) Arithmatic Operators. +, -, *, /, % <br>
   c) Unary Operators: +, -, ++, --, ! <br>
   d) Equality Operator: ==, !=, >, >=, <, <= <br>
   e) Conditional Operator: &&, || <br>
   f) Terenary Operator:  ?: <br>
   g) instanceof <br>
   h) Bitwise Operators: ~, <<, >>, >>>, &, ^, | <br>

2) Explain about Conditional statements? <br>
   a) if, if else, while, do...while, for, switch <br>
   b) break, continue, return <br>

3) What is yield statement? <br>
    eg1: new switch syntax. no need to add break if we use -> symbol<br>
    int quarter = ...; // any value <br>
    String quarterLabel = <br>
    switch (quarter) { <br>
        case 0  -> "Q1 - Winter"; <br>
        case 1  -> "Q2 - Spring"; <br>
        case 2  -> "Q3 - Summer"; <br>
        case 3  -> "Q3 - Summer"; <br>
        default -> "Unknown quarter"; <br>
    };<br>
    eg2: we shouldn't be using return statement. This gives compilation error.<br>
    // Be careful, this code does NOT compile! <br>
    public String convertToLabel(int quarter) { <br>
    String quarterLabel = <br>
        switch (quarter) { <br>
            case 0  -> { <br>
                IO.println("Q1 - Winter"); <br>
                return "Q1 - Winter"; <br>
            } <br>
            default -> "Unknown quarter"; <br>
        }; <br>
    return quarterLabel; <br>
   } <br>
   eg3: we must use yield statement incase of return within swith case. <br>
   public String convertToLabel(int quarter) { <br>
    String quarterLabel = <br>
        switch (quarter) { <br>
            case 0  -> { <br>
                IO.println("Q1 - Winter"); <br>
                yield "Q1 - Winter"; <br>
            } <br>
            default -> "Unknown quarter"; <br>
        }; <br>
    } <br>
    return quarterLabel; <br>
    } <br>
    eg4: colon with yeild <br>
    int quarter = ...; // any value  <br>
    String quarterLabel =  <br>
    switch (quarter) { <br>
        case 0 :  yield "Q1 - Winter"; <br>
        case 1 :  yield "Q2 - Spring"; <br>
        case 2 :  yield "Q3 - Summer"; <br>
        case 3 :  yield "Q3 - Summer"; <br>
        default: IO.println("Unknown quarter"); <br>
                 yield "Unknown quarter"; <br>
    }; <br>
   a) yield is only used in switch in block requirement. <br>
   b) Block Requirement: When using the arrow syntax (->), yield is only required if the code following the arrow is a multi-line block {}.
   c) yield acts like a break except that yield returns value. <br>
   d) yiled must followed by an expression/value <br>
   e) eg:   case SATURDAY, SUNDAY -> 0;
                default -> {
                    int remainingWorkDays = 5 - d.ordinal();
                    yield remainingWorkDays;
                }
            }; <br>
