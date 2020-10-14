# 排序
<!-- TOC -->
- [目錄](#排序)
- [> Bubble Sort](#Bubble-Sort)
- [> Selection Sort](#Selection-Sort)
- [> Insertion Sort](#Insertion-Sort)
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
