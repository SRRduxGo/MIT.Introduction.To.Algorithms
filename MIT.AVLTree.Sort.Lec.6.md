# [AVL Trees, AVL Sort ⫘ ⤇ ⭆ ⇛ ➟ ➠](https://youtu.be/FNeL18KsWPc?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb)

## Agenda

- Balanced BSTS
  - _The importance of being Balanced_
  - _AVL Trees_
    - _Definition_
    - _Rotation_
    - _Insert_
- Other balanced trees
- Data Structures in General
- Lower Bounds

### In-order Traversal

- ***Left, Center, Right*** Recursively

### Post-Order Traversal

- ******

### Height of the Tree / Balanced OR Not

- ***Balanced BST***
  - _`Height` of the tree is `O(Log N)`_

> `Height` of the `tree` is the length `Longest Path` from the `Root` to Some `Leaf`

- Worst Case - `O(N)`

> why oO!

## Height of a Node in a Tree (NOT BST)

- **Length of Longest path from the node to a leaf**
- **`Height` of a `leaf` is `zero`**
- **`Height` of the left and right `null` children of a leaf is `-1 each`**

> `Depth` of a `Node` is the same measure as above but the `longest path` from the `Root` to the given `Node`

- _can be calculated by taking the `Max` of the `height` of the `left` and the `right` child nodes and incrementing it by one_
  - _`Height of the current Node = Max(height(left), height(right)) + 1`_

> `Data Structure Augmentation`: Keeping more info at a node besides the `key` value

## AVL Trees

> ***Requires `heights` of `left` and `right` children of `every node` to `differ` by at most `± 1`***

- ***|`h`<sub>`l`</sub> - `h`<sub>`r`</sub>| `≤ 1` (numeric one)***

### AVL Trees are Balanced

- `worst case` is when `right` subtree  has height `1 more than` `left` subtree for `every Node`
  - _`N`<sub>`h'`</sub> = `min` no. of nodes in an `AVL Tree` of height `h'`_
  - _`N`<sub>`h'`</sub> = `1` + `N`<sub>`h'- 1`</sub> + `N`<sub>`h'- 2`</sub>_  
                        > _`1` + `2.N`<sub>`h'- 2`</sub>_   
                        > _`2.N`<sub>`h'- 2`</sub>_  
                        = **`O(2ˆh/2)`**  
                    `h` < `2.Log N`

### AVL Insert

- _Simple BST insert_
- _Fix AVL `INVARIANT` property_

> _SIDE NOTE :_
>
> #### Rotations
>
> - `Left Rotate`
>   - EXAMPLE: Tree ⤇ _Parent ⫘ x.{ A, y.{B,C} } ➠ **LEFT ROTATE (x)** ➠ Parent ⫘ y.{ x.{A, B}, C}_
>   - _Reversible Operation: **Right Rotate** ⇛ Parent ⫘ y.{ x.{A, B}, C}_
>
> - `Right Rotate`
>   - EXAMPLE: Tree ⤇ _Parent ⫘ y.{ x.{A, B}, C} ➠ **RIGHT ROTATE (y)** ➠ _Parent ⫘ x.{ A, y.{B,C} }_
>   - _Reversible Operation: **Left Rotate** ⇛ Parent ⫘ x.{ A, y.{B,C} }_  
>
>  

#### ***Fix `AVL Tree` `INVARIANT` property***

- Fix AVL property from changed node up
- Suppose `x` is the lowest Node violating AVL-Invariant
  - if `x` is right heavy
    - _if `x` has a `right` child which is `right-heavy` or `balanced`_
      - _LEFT-Rotate `x`_
    - _if `x` has a `right` - `z` child which is `left-heavy`_
      - _RIGHT-Rotate `z` then LEFT-Rotate `x`_

#### AVL sort

- Insert `N` items - `O(N Log N)`
- in-order traversal  - `O(N)` time
