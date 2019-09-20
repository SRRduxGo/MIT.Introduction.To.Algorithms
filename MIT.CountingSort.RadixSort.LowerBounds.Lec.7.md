# [Counting Sort, Radix Sort, Lower Bounds for Sorting ⫘ Ω ⤇ ⭆ ⇛ ➟ ➠](https://youtu.be/Nz1KZXbghj8?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb)

## Agenda

- Comparison Model
- Lower Bounds
  - _Searching: `Ω (Log N)`_
  - _Sorting: `Ω (N Log N)`_
- `O(N)` _Sorting Algorithms_
  - _Counting Sort_
  - _Radix Sort_

## Comparison Model

- All input items are Black Boxes `(ADT's)`
- _Only operations allowed are comparisons `(≤ ≥ = < >)`_
- _`time cost = #number of comparisons`_

### Decision Tree

- **_Any `comparison algorithm` can be viewed as a `tree` of all possible `comparisons and their outcomes`, and resulting answer for any particular `N`_**
  - _Example: `Binary Search N = 3 Decision Tree`_
    - _At each level when searching for an `X` there is a ***`Recursive Decision`*** `⫘  X ≥ Node ⤇ Yes { Go right } or No { Go Left }`_
    - This can be seen as `Yes OR No` decision tree and each Node can be seen as `{Parent-Node [≤, ≥] X [<,>] Child-Node}`
    - Good to view an `Algorithm` like this so that it can be `Analysed` - not a good representation in a Memory as Space complexity will grow exponentially - Hint! look at the node structure, at every level memory size would be a double of what previous level consumed for representation

### Decision Tree ⫘ Algorithm {one to one mapping in Representation}

- _`{internal.node - Binary.Decision}`_
- _`{leaf - found.answer}`_
- _`{Root.To.Leaf.PATH - Algorithm.Execution}`_
- _`{Path.LENGTH - Running.Time}`_
- _`{HEIGHT.of.The.Root - WORST.CASE.Running.Time}`_ **why because leaf is the solution**

### Searching Lower Bound - Claim

- _`N` preprocessed items, finding a given item among them in Comparison_
- _Model requires `Ω (Log N)` in worst case_

#### PROOF_

- _Decision Tree is `Binary` & Must have `≥ N leaves`, **one for each answer**_
  - As search variable `x` can take any of the `N` values and each answer is a `leaf`
- _**Implies[Binary Tree Property `N` leaves ] ⤇ `height ≥ Log N`**_

### Sorting Lower Bound - Claim

- _`N` preprocessed items, finding a given item among them in Comparison_
- _Model requires `Ω (N Log N)` in worst case_

#### _PROOF

- _leaf would look like `[A[0] ≤ A[1] ≤ A[3] ≤ A[1] ≤ A[7] ... ]`_
- _Decision Tree is `Binary`_
- _`#Number of Leaves ≥ #Number of possible answers = N!`_
  - _since number of items are `N` and can have any value this leads to **maximum possible comparison orders between `A[0] to A[N]` can only be `N!`**_
- _Implies ⤇ `height` ≥ `Log N!` since it is a binary-tree_  
                     _= `Log (N.(N-1).(N-2).(N-3)...1)`_  
                     _= `Log N + Log (N-1) + Log(N-2) + Log(N-3)...+ Log 1`_  
                     _= `∑`<sub>`i = 1`</sub><sup>`N`</sup> `Log i`_  
                     _≥ `∑`<sub>`i = N/2`</sub><sup>`N`</sup> `Log i`_
                     _≥ `∑`<sub>`i = N/2`</sub><sup>`N`</sup> `Log N/2`_
                     _= `∑`<sub>`i = N/2`</sub><sup>`N`</sup> `(Log.N - 1)`_
                     _= `(N/2).Log N - N/2`_
                     _= `Ω (N Log N)`_

<hr/>

## Linear Time Sorting (Some Times) / Integer Sorting

- **Assume `N - keys` being sorted are Integers `∈ { 0,1,2... (K - 1) }`**
  - _each fir in a `memory-word` RAM_
- **Can do more operations than `Comparisons`**

### Claim - for k integers - if not `Ginormous` -  can be sorted in Linear Time `O(N)`

### Counting Sort
  
- _if there are `K` items and we assume Integers are between `1 to K`_
- _Create another array of total `K` slots - `B'`_
- _Start Traversing the `unsorted Array - UA'` from `0 to K-1`_
  - _As soon as you read the element `el`, increase the count at `B'[el]`_
  - _By the time we reach the end of `UA'`, in `B'` we have the `counts` at `indexes` and just by reading the `index-key` and its `count` value, starting from `0` to `K-1` we get the sorted list_

#### Formal Definition

- `L` = Array of `k` empty lists:

```js
`L` = Array of `k` empty lists /** O(K) */
for j in range(n):
    L[ key(A[j]) ].append(A[j]) /**O(1) each step ⤇ takes O(n) time in completing the loop*/
output = [] /**O(1)*/
for i in range(k):
    output.extend(L[i]) /**O(length of L[i]) at each step ⤇ O(n) Since there are n elements in total*/
/**
Total time Complexity = O(n) + O(1) + O(K) = O(n + k)
*/
```

### Radix Sort

- Imagine each integer as `base b`
- number of digits = `d` = `Log`<sub>`b`</sub>`k`
  - Sort the integers by `least Significant Digit`
    - then repeat the same procedure, but use the `Next Significant Digit`
    - repeat till the `Most Significant Digit`
    - each of these sorts are achieved by `Counting Sort`
    - Time Complexity  at each step `O(n + b)`
    - Total is `O(d.(n + b))` = `O((Log k).(n + b))`
- `b` is minimized when `b = ϴ (n)`
- if `k` ≤ `n`<sup>`c`</sup>
  - `O((Log k).(n + b))` = `O(n.(Log`<sub>`n`</sub> `k))`
  - _=`O(n.c)`_

## TODO : Refer Cormen to get more details
