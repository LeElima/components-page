<template>
    <div>
        <h2>Longest Common Prefix</h2>
        <h4>
            Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".
</h4>
        <h5>
            Example 1:

Input: strs = ["flower","flow","flight"]
Output: "fl"
Example 2:

Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
        </h5>
<h6>
    Constraints:

1 <= strs.length <= 200
0 <= strs[i].length <= 200
strs[i] consists of only lowercase English letters.
</h6>
 <br />
 <h3>

    public class Solution {
    public string LongestCommonPrefix(string[] strs) {
        if (strs == null || strs.Length == 0)
            return "";
        string prefix = strs[0];
        for (int i = 1; i < strs.Length; i++) {
            while (strs[i].IndexOf(prefix) != 0) {
                prefix = prefix.Substring(0, prefix.Length - 1);
                if (prefix == "")
                    return "";
            }
        }
        return prefix;
    }
}
 </h3>


 


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