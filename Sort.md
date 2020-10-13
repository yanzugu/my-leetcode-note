# 排序
<!-- TOC -->
- [目錄](#排序)
- [> Bubble Sort](#Bubble-Sort)
- [> Selection Sort](#Selection-Sort)
<!-- /TOC -->

# Bubble Sort
- #### *不斷將較大的數右移，使區間最後的數一定為最大值，接著將區間向前縮小。*
```cpp
// len = array size
int arr[len];                    
for (int i = 0; i < len; i++)
{
    for (int j = 0; j < len-i-1; j++)
    {
        if (arr[j] > arr[j+1])
        {
            swap(arr[j], arr[j+1]);
        }
    }
}
```

# Selection Sort
- #### *找出區間最小的數，再與區間的第一個數交換，不斷將區間向後縮小。*
```cpp
// len = array size
int arr[len];       
for (int i = 0; i < len; i++)
{
    int min = i;
    for (int j = i+1; j < len; j++)
    {
        if (arr[min] > arr[j])
        {
            min = j;
        }
    }
    swap(arr[min], arr[i]);
}
```
