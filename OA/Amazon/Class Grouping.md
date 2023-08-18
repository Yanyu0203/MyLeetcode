[Link](https://cybergeeksquad.co/2023/03/class-grouping-amazon-oa-2022-solution.html)

```c++
int classNumber(vector<int>& level, int &maxSpread) {
    int res = 1;
    sort(level.begin(), level.end());
    int minimun = level[0];
    for (int i = 1; i < level.size(); ++i) {
        if (level[i] - minimun <= maxSpread) {
            continue;
        }
        else {
            ++res;
            minimun = level[i];
        }
    }
    return res;
}
```
