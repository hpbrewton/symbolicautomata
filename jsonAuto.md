# JSON Automata

Work on a ranked alphabet:
- Arity 0 (leaves): End, True, False, Null, Number
- Arity 1: Key, Character, Object, Array, String
- Arity 2: Array-Element
- Arity 3: Key-Value

And are subsets of the (Σ, Q, Qr, ∆), such that:
- Σ are predicates (isEqual for all but characters and numbers)
- Q are states {:, k, v, s, f, e, 0}
- Qr is the accepting root {f}
- And ∆ is the following transitions
    - (:, Key-Value, k, v, :)
    - (e, Array-Element, v, e)
    - (:, End)
    - (k, Key, s)
    - (s, Character, s)
    - (s, End)
    - (v, True)
    - (v, False)
    - (v, Null)
    - (v, Number)
    - (v, Object, :)
    - (v, Array, e)
    - (v, String, s)
    - (f, Object, :)
    
   