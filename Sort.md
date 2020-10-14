# 排序
<!-- TOC -->
- [目錄](#排序)
- [> Bubble Sort](#Bubble-Sort)
- [> Selection Sort](#Selection-Sort)
- [> Insertion Sort](#Insertion-Sort)
- [> Shell Sort](#Shell-Sort)
<!-- /TOC -->

<!-- 
# Content Name
- #### *Description*
```cpp                 
Code
```
-->


```
variable:

vector<int> list(?);
int len = list.size();
```

# Bubble Sort
- #### *不斷將較大的數右移，使區間最後的數一定為最大值，接著將區間向前縮小。*
```cpp                 
for (int i = 0; i < len; i++)
{
    for (int j = 0; j < len-i-1; j++)
    {
        if (list[j] > list[j+1])
        {
            swap(list[j], list[j+1]);
        }
    }
}
```

# Selection Sort
- #### *找出區間最小的數，再與區間的第一個數交換，不斷將區間向後縮小。*
```cpp     
for (int i = 0; i < len; i++)
{
    int min = i;
    for (int j = i+1; j < len; j++)
    {
        if (list[min] > list[j])
        {
            min = j;
        }
    }
    swap(list[min], list[i]);
}
```

# Insertion Sort
- #### *選定當前值，不斷向前比對直到遇到比其小的值插入該值後面，其餘比其大的一律向右移。*
```cpp
for (int i = 1; i < len; i++)
{
    int now = list[i];
    int j = i;
    for (; j > 0 && list[j-1] >= now; j--)
    {
        list[j] = list[j-1];
    }     
    list[j] = now;
}
```

# Shell Sort
- #### *將 List 以 Gap 為間隔 {Gap=len/2^n, n=1,2,3...} 進行切塊後再做 Insertion Sort*
```
e.g. 
    list(1) = {5, 8, 1, 3, 2, 4, 7, 6}, len = 8, gap(1) = 4  
    group(1)(1) = {5, 2} => {2, 5}
    group(1)(2) = {8, 4} => {4, 8}
    group(1)(3) = {1, 7} => {1, 7}
    group(1)(4) = {3, 6} => {3, 6}
    
    //////////////////////////////////////////////////////////
    
    list(2) = {2, 4, 1, 3, 5, 8, 7, 6}, len = 8, gap(2) = 2
    group(2)(1) = {2, 1, 5, 7} => {1, 2, 5, 7}
    group(2)(2) = {4, 3, 8, 6} => {3, 4, 6, 8}
    
    //////////////////////////////////////////////////////////
    
    list(3) = {1, 3, 2, 4, 5, 6, 7, 8}, len = ; gap(3) = 1
    group(3)(1) = {1, 3, 2, 4, 5, 6, 7, 8} => {1, 2, 3, 4, 5, 6, 7, 8}
```

```cpp                 
for (int gap = len/2; gap > 0; gap /= 2)   // 得到 Gap
{
    for (int i = gap; i < len; i++)        // 從每個間隔的第二個數開始做 Insertion Sort
    {
        int now = list[i];
        int j = i;
        for (; j >= gap && now <= list[j-gap]; j -= gap)
        {
            list[j] = list[j-gap];
        }
        list[j] = now;
    }
}
```
