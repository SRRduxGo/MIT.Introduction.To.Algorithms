# [Models of Computation, Document Distance](https://youtu.be/Zc54gFhdpLA?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb)

## Agenda

- What's an algorithm?
- what is time?
- Random Access Machine
- Pointer Machine
- Python Model
- Document Distance
- Problem and Algorithms

### What's an Algorithm

- _Computational procedure to solve some problem_
- _Mathematical Analog of a Computer program_  
     _`{Program - Algorithm}`_  
     _`{Programming Language - Structured English}`_
     _`{Computer - Model of Computation}`_

### Model of Computation

- `what operations an Algorithm is allowed`
- `cost, (time..) of each operation`

#### Random Access Machine (RAM) Model

- Random access memory modeled by big array
- in `O(1)` **time** can do
  - _load `O(1)` words_
  - _do `O(1)` computations_
  - _store `O(1)` words_
- `O(1)` registers
- word: `w` bits
- `w` = `Log (size of memory)`

#### Pointer Machine Model

- Dynamically allocated `Objects`
- An `Object` has `O(1)` `fields`
- _`field = { word || pointer }`_
- _`pointer` points (has ref of) to an `Object` or is `null`_

#### [Python Model](https://youtu.be/Zc54gFhdpLA?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb&t=1470)

- _`list` = array_
  - _`L[i] = L[j] + 5` : such operations take constant time `O(1)`_
  - _`table doubling`_
- _Object with `O(1)` attributes_
  - _`x = x.next` : such operations take constant time `O(1)`_

<hr/>

## Document Distance Problem

### Problem - distance between to documents `D1`, `D2`

- what is `document-distance`?
  - _`NON-Similarity` between two documents, `less Similar` means greater the Distance_
  - _`document` = sequence of `words`_
  - _`word` = string of `AlphaNumeric Characters`_
  - _`idea`: "shared words"  to define distance_
  - _Think of document as a `Vector`_
    - _`D[w]` =  `#Occurences` of `w` in `D`_

#### Example

- `D1 = "the cat"`
- `D2 = "the dog"`
- `Distance = d'(D1,D2) = ∑ D1[w].D2[w]` where `D'[missing word] = 0`
- high product means less Distance

> Better Still

- `∑ D1[w].D2[w] / |D1|.|D2|` where `|D'|` is the length of the vector

#### Algorithm

- Split document into words
- Compute word frequencies
- dot product




