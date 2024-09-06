<template>
    <div>
        <h3>27 - Remove Element</h3>
        <h4>Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. The order of the elements may be changed. Then return the number of elements in nums which are not equal to val.

Consider the number of elements in nums which are not equal to val be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the elements which are not equal to val. The remaining elements of nums are not important as well as the size of nums.
Return k.
Custom Judge:

The judge will test your solution with the following code:

int[] nums = [...]; // Input array
int val = ...; // Value to remove
int[] expectedNums = [...]; // The expected answer with correct length.
                            // It is sorted with no values equaling val.

int k = removeElement(nums, val); // Calls your implementation

assert k == expectedNums.length;
sort(nums, 0, k); // Sort the first k elements of nums
for (int i = 0; i < actualLength; i++) {
    assert nums[i] == expectedNums[i];
}
If all assertions pass, then your solution will be accepted.

 

Example 1:

Input: nums = [3,2,2,3], val = 3
Output: 2, nums = [2,2,_,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 2.
It does not matter what you leave beyond the returned k (hence they are underscores).
Example 2:

Input: nums = [0,1,2,2,3,0,4,2], val = 2
Output: 5, nums = [0,1,4,0,3,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums containing 0, 0, 1, 3, and 4.
Note that the five elements can be returned in any order.
It does not matter what you leave beyond the returned k (hence they are underscores).
 

Constraints:

0 <= nums.length <= 100
0 <= nums[i] <= 50
0 <= val <= 100</h4>

<h3>Como eu fiz:</h3>
<h4>public class Solution {
    public int RemoveElement(int[] nums, int val) {
        var retorno = new int[nums.Length];
        for (int i = 0; i < nums.Length; i++)
        {
            if(nums[i] != val)retorno[i] = nums[i];
        }
        return retorno.Length;
    }
}</h4>
<h3>Como foi resolvido:</h3>
<h4>public class Solution {
    public int RemoveElement(int[] nums, int val) {
        int index = 0; // Índice para acompanhar o número de elementos válidos
        for (int i = 0; i < nums.Length; i++) {
            if (nums[i] != val) {
                nums[index] = nums[i]; // Substitui o elemento na posição index
                index++; // Avança o índice
            }
        }
        return index; // Retorna o número de elementos válidos
    }
}</h4>
<h3>Melhorado:</h3>
<h4>public class Solution {
    public int RemoveElement(int[] nums, int val) {
        if (nums == null || nums.Length == 0) return 0; 
        int validCount = 0; 
        foreach (var num in nums) {
            if (num != val) {
                nums[validCount++] = num; 
            }
        }
        return validCount; 
    }
}</h4>
    </div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
    data(){
        return{

        }
    }
})
</script>