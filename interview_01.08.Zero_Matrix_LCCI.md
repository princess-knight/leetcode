# 题目：零矩阵
编写一种算法，若M × N矩阵中某个元素为0，则将其所在的行与列清零。

- 示例 1：
```
输入：
[
  [1,1,1],
  [1,0,1],
  [1,1,1]
]
输出：
[
  [1,0,1],
  [0,0,0],
  [1,0,1]
]
```
- 示例 2：
```
输入：
[
  [0,1,2,0],
  [3,4,5,2],
  [1,3,1,5]
]
输出：
[
  [0,0,0,0],
  [0,4,5,0],
  [0,3,1,0]
]
```
# 代码
```
class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        int row=matrix.size(),col=matrix[0].size();
        vector<int> record;
        for(int i=0;i<row;i++){
            for(int j=0;j<col;j++){
                if(matrix[i][j]==0){
                    record.push_back(j);
                    record.push_back(i);
                }
            }
        }
        int count=record.size();
        for(int i=0;i<count;){
            for(int k=0;k<row;k++)
                matrix[k][record[i]]=0;
            i++;
            for(int m=0;m<col;m++)
                matrix[record[i]][m]=0;
            i++;
        }
    }
};
```
