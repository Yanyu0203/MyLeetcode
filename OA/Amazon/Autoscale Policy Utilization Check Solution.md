[Link](https://cybergeeksquad.co/2023/03/autoscale-policy-utilization-check.html)

```c++
int getFinalInstance(vector<int>& avarageUtil, int &instance) {
    int res = instance;
    int i = 0;
    while (i < avarageUtil.size()) {
        
        if (avarageUtil[i] < 25) {
            if (i > 1) {
                res = (int)ceil(double(res) / 2.0);
                i += 10;
            }
        }
        else if (avarageUtil[i] > 60) {
            if (i <= pow(10, 8)) {
                res *= 2;
                i += 10;
            }
        }
        ++i;
    }
    return res;
}
```
