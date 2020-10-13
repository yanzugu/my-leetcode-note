# 排序
<!-- TOC -->
- [目錄](#排序)
- [> Bubble Sort](#Bubble-Sort)
- [> Selection Sort](#Selection-Sort)
<!-- /TOC -->

# Bubble Sort
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
```cpp
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
