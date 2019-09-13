# [AVL Trees, AVL Sort](https://youtu.be/FNeL18KsWPc?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb)

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

> ***Requires `heights` of `left` and `right` children of `every node` to `differ` by at most `±1`***

- ***|`h`<sub>`l`</sub> - `h`<sub>`r`</sub>| `≤ 1`***

