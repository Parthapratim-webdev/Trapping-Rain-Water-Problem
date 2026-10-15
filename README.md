# 🌧️ Trapping Rain Water

## 📌 Approach: Two-Pointer Technique

This solution calculates the total amount of rainwater trapped between bars using two pointers (`l` and `r`) and two variables (`lmax` and `rmax`) to track the maximum heights from both sides.

### ⚙️ Workflow

1. Initialize two pointers: `l = 0` and `r = n - 1`.
2. Initialize `lmax = 0`, `rmax = 0`, and `ans = 0`.
3. Update the maximum heights from the left and right.
4. If `lmax < rmax`, calculate the trapped water at the left pointer and move `l` forward.
5. Otherwise, calculate the trapped water at the right pointer and move `r` backward.
6. Repeat until both pointers meet.
7. Return `ans`, the total trapped rainwater.

### 🔄 Flowchart

```mermaid
flowchart TD
    A([Start]) --> B[Initialize l, r, lmax, rmax, ans]
    B --> C{l < r?}
    C -- No --> H[Return ans]
    C -- Yes --> D[Update lmax and rmax]
    D --> E{lmax < rmax?}
    E -- Yes --> F[Add lmax - height l to ans]
    F --> G[Increment l]
    E -- No --> I[Add rmax - height r to ans]
    I --> J[Decrement r]
    G --> C
    J --> C
    H --> K([End])
```

### ⏱️ Complexity Analysis

* **Time Complexity:** `O(n)` — Each pointer moves through the array at most once.
* **Space Complexity:** `O(1)` — Only a constant number of extra variables are used.
