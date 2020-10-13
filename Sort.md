# 排序
<!-- TOC -->
- [目錄](#排序)
- [> Bubble Sort](#Bubble-Sort)
<!-- /TOC -->

# Bubble Sort
```cpp
// len = array size
int arr[len];                           
for (int i = 0; i < len - 1; i++)
{
    for (int j = i; j < len - 1; j++)
    {
        if (arr[j] > arr[j+1])
        {
            swap(arr[j], arr[j+1]);
        }
    }
}
```
