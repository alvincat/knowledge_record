## C++数据处理

### 获取浮点型数的小数部分
```c
float value;
float rear = value - (int)value; //获取浮点数的小数部分
```

### double保留指定位数的小数
```cpp
double round(double number, unsigned int bits) {
    stringstream ss;
    ss << fixed << setprecision(bits) << number;
    ss >> number;
    return number;
}
```
