```cpp
void perm(vector<int> arr, int idx)
{
    if (idx == arr.size())
    {
        for (int i = 0; i < arr.size(); i++)
        {
            cout << arr[i] << " ";
        }
        cout << endl;
    }
    for (int i = idx; i < arr.size(); i++)
    {
        swap(arr[i], arr[idx]);
        perm(arr, idx + 1);
        swap(arr[i], arr[idx]);
    }
}
```
