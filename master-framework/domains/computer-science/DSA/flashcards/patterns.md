# array

## conditional sliding

### Sliding Window Pattern

Expand → Violate → Shrink.

### Two Pointers Pattern

Move left/right based on condition.

### Prefix Sum Pattern

prefix[i] - prefix[j] = target.

## remove k duplicates from a sorted array

```python
class Solution:
    def removeDuplicates(self, nums, k):
        if len(nums) <= k:
            return len(nums)

        write = k  # first k elements are always allowed

        for i in range(k, len(nums)):
            if nums[i] != nums[write - k]:
                nums[write] = nums[i]
                write += 1

        return write

```
