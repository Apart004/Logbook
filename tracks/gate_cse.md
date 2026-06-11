# June 11, 2026
Focus: Pointer-to-Array Conversions & 2D Matrix Addressing

-What I did: Advanced through core GATE C theory by breaking down the intersection of multidimensional (2D) arrays and pointer decays. Evaluated matrix index offset conversions, analyzing how an array identifier decays into a pointer to its first row vector (e.g., $A$ as type `int (*)[N]`). Solved baseline practice problems to map out multi-dereferencing address calculations and element stride scales ahead of deep-dive pointer question tracking tomorrow.
-Takeaway: An array name behaves as a constant pointer to its first contiguous block; scaling multidimensional lookups correctly requires mapping how nested dereferences handle array pointer decayed types.

# June 10, 2026
Focus: 1D and 2D Array Structures & Pointer Offsets

-What I did: Mastered contiguous linear allocation patterns by reviewing 1D arrays alongside multidimensional (2D) row-major configurations. Drilled deep into index evaluation mechanics, base address calculation equations, stride length increments, and compile-time boundary constraints while executing structural code examples to map how multi-indices reduce to linear physical offsets.
-Takeaway: Array brackets ($A[i][j]$) serve as a syntactic abstraction for raw pointer arithmetic, evaluating directly to dynamic target locations based on element size offsets and raw contiguous row length factors ($\*( \*(A + i) + j)$).

# June 9, 2026
Focus: C Unary Operators & Pointer Architecture

-What I did: Deep-dived into the evaluation mechanics of unary pre/post-increment and decrement operators ($++$, $--$), focusing on operator precedence, sequence points, and compiler-specific side effects. Paired this with a detailed architectural breakdown of pointers, analyzing address-of operators ($\&$), dereferencing ($\*$), memory layouts, pointer arithmetic rules, and how data sizes dictate byte offsets during pointer step increments.

-Takeaway: Post-increment operators evaluate the current expression value before modifying the register variable, whereas pointer arithmetic modifies physical byte steps based strictly on the scaling factor of the data type it references.

# June 8, 2026
Focus: GATE C Programming Foundation & Lexical Analysis

-What I did: Initiated foundational theory for the GATE C programming syllabus by completing the first three core lectures. Analyzed the execution lifecycle, compilation phases, and source code structure before drilling deep into lexical analysis and language tokens. Broke down syntactic building blocks, evaluating memory constraints, compiler interpretation rules, and classifications of identifiers, keywords, constants, literals, operators, and symbols.

-Takeaway: Lexical analysis relies on the strict categorization of components into distinct tokens, forming the precise foundation upon which the compiler constructs semantic understanding and memory allocation rules.

# June 7, 2026
Focus: Exam Strategy & Curriculum Mapping

-What I did: Locked down my official subject sequence, daily study strategy, and long-term timeline leading up to the exam. Structured a balanced, daily grind through core CS theory designed to integrate smoothly with active coding and cybersecurity lab work rather than relying on last-minute cramming.

-Takeaway: Consistency beats intensity.