# 题目：判定字符是否唯一
实现一个算法，确定一个字符串 s 的所有字符是否全都不同。
# 示例
- 示例 1：
```
输入: s = "leetcode"
输出: false 
```
- 示例 2：
```
输入: s = "abc"
输出: true
```
##### 限制：
0 <= len(s) <= 100  
如果你不使用额外的数据结构，会很加分。

# 代码
```
class Solution {
public:
    bool isUnique(string astr) {
        sort(astr.begin(),astr.end());
        if(astr.size()==0)
            return true;
        for(int i=0;i<astr.size()-1;i++){
            if(astr[i]==astr[i+1])
                return false;
        }
        return true;
    }
};
```
