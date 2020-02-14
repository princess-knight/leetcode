# 题目：旋转矩阵
给定一幅由N × N矩阵表示的图像，其中每个像素的大小为4字节，编写一种方法，将图像旋转90度。
不占用额外内存空间能否做到？

# 示例
+ 示例 1：
```
给定 matrix = 
[
  [1,2,3],
  [4,5,6],
  [7,8,9]
],
原地旋转输入矩阵，使其变为:
[
  [7,4,1],
  [8,5,2],
  [9,6,3]
]
```
+ 示例 2:
```
给定 matrix =
[
  [ 5, 1, 9,11],
  [ 2, 4, 8,10],
  [13, 3, 6, 7],
  [15,14,12,16]
], 
原地旋转输入矩阵，使其变为:
[
  [15,13, 2, 5],
  [14, 3, 4, 1],
  [12, 6, 8, 9],
  [16, 7,10,11]
]
```

# 代码
```
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        int length=matrix.size();
        for(int i=0;i<length/2;i++){  //左右翻转
            for(int j=0;j<length;j++){
                int tmp=matrix[i][j];
                matrix[i][j]=matrix[length-1-i][j];
                matrix[length-1-i][j]=tmp;
            }
        }
        for(int i=0;i<length;i++){  //对角线翻转
            for(int j=0;j<i;j++){
                int temp=matrix[i][j];
                matrix[i][j]=matrix[j][i];
                matrix[j][i]=temp;
            }
        }
    }
};
```
