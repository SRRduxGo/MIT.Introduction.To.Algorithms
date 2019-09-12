# [Binary Search Trees, BST Sort ⤇ ⭆ ⇛ ➟ ➠](https://youtu.be/9Jry5-82I68?list=PLUl4u3cNGP61Oq3tWYp6V_F-5jb5L2iHb)

> Runway reservation system:
>
> - Airport with a Single Runway
> - Reservation for future landings
> - Reserve Request specifies landing time `t`
> - Add `t` to the set `R` if no other landings are scheduled within `k` minutes
> - Remove from set `R` once the plane lands
> - `|R| = n` size of the set
> - all operations should be `O( log n )`
> - Rank(`t`) = how many planes are scheduled to land at times ≤ `t`
>
> what is the best Data Structure to achieve the above?
>
> ## Bad DS choices
>
> - ***Unsorted List*** : Insert in `O(1)` time, check takes `O(n)` time
> - ***Sorted Array*** : Search in `O(log n)`, constraint check `O(1)`, Insert `O(n)`
> - ***Sorted List*** : Search `O(n)`, insertion time `O(1)`: can't  do binary search on list
> - ***Heaps*** : Search `O(n)` time

## Binary Search Tree

- Structure `NODE X`
  - _`key(x)`_
  - _`Pointers`_
    - _`parent(x)`_
    - _`left(x)`_
    - _`right(x)`_

> Invariant BST: For all nodes `x`, if `y` is the left subtree then
>
> - `key(y) ≤ key(x)`
>
> if `y` is in the right subtree then
>
> - `key(y) ≥ key(x)`

- _`h` is the height of the tree_
  - _Insertion Complexity `O(h)` time_
- _`h` = `Log N`_

### Augment the BST Structure

- _Associate one more number with the Node - `SubTree Size - SBZ`_
- _After every `Insert` or `Delete` ➟ Modify `SBZ` at each Node above the action point_
- _`SBZ` = 1 + Left-Subtree-Size + Right-Subtree-Size_
- _`SBZ` of a leaf is `1`_

### Number of Nodes ≤ x in a given BST - Augmented

- _Walk down the tree to find the desired time_
- _Add in the nodes which are smaller than `x`_
- _Add in the Subtree-Sizes to the left_
