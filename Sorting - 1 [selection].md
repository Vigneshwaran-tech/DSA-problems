# Selection Sort Implementation in C++

This repository contains a C++ implementation of the **Selection Sort** algorithm. Selection Sort is a simple sorting algorithm that works by repeatedly finding the minimum element from the unsorted part of the array and swapping it with the first unsorted element.

---

## Problem Description

Given an array of integers, sort the array in **ascending order** using the **Selection Sort** algorithm.

### Examples

#### Example 1:
- **Input**: `arr = [4, 1, 3, 9, 7]`
- **Output**: `[1, 3, 4, 7, 9]`
- **Explanation**:
  - The algorithm selects the smallest element (`1`) and swaps it with the first element (`4`). The array becomes `[1, 4, 3, 9, 7]`.
  - Next, it selects the smallest element (`3`) from the remaining unsorted part and swaps it with the second element (`4`). The array becomes `[1, 3, 4, 9, 7]`.
  - This process continues until the entire array is sorted.

#### Example 2:
- **Input**: `arr = [10, 9, 8, 7, 6, 5, 4, 3, 2, 1]`
- **Output**: `[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`

#### Example 3:
- **Input**: `arr = [38, 31, 20, 14, 30]`
- **Output**: `[14, 20, 30, 31, 38]`

---

## Algorithm: Selection Sort

1. **Start with the first element** as the beginning of the unsorted portion of the array.
2. **Find the smallest element** in the unsorted portion of the array.
3. **Swap the smallest element** with the first element of the unsorted portion.
4. **Move the boundary** of the sorted portion one element to the right.
5. **Repeat steps 2-4** until the entire array is sorted.

### Time Complexity:
- **Worst Case**: \(O(n^2)\)
- **Best Case**: \(O(n^2)\)
- **Average Case**: \(O(n^2)\)

### Space Complexity:
- \(O(1)\) (in-place sorting)

---

## Solution Code

Below is the C++ implementation of the Selection Sort algorithm:

```cpp
#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    // Function to perform selection sort on the given array.
    void selectionSort(vector<int> &arr) {
        int n = arr.size();
        for (int i = 0; i < n - 1; i++) {
            int minIndex = i; // Assume the first element of the unsorted part is the smallest
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j; // Update the index of the smallest element
                }
            }
            // Swap the smallest element with the first element of the unsorted part
            swap(arr[minIndex], arr[i]);
        }
    }
};

int main() {
    vector<int> arr = {41, 39, 7, 136, 99, 3, 4, 7, 9};
    
    cout << "Before sorting: ";
    for (int i : arr) {
        cout << i << " ";
    }
    cout << endl;

    Solution solution;
    solution.selectionSort(arr);

    cout << "After sorting: ";
    for (int i : arr) {
        cout << i << " ";
    }
    cout << endl;

    return 0;
}

## 📂 How to Run the Code

1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/DSA-Solutions.git
   ```
2. Compile the code:
   ```sh
   g++ maxFrequency.cpp -o maxFrequency
   ```
3. Run the program:
   ```sh
   ./maxFrequency
   ```

---

## 🤝 Contributing

Feel free to open issues or submit pull requests to improve the algorithm! 🚀

---

## 📜 License

This project is licensed under the MIT License.

