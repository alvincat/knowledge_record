
## C++字符串处理知识

### 字符数组初始化的方法

```c
//If you don't want to change the strings, then you could simply do
const char *a[2];
a[0] = "blah";
a[1] = "hmm";
//When you do it like this you will allocate an array of two pointers to const char. These pointers will then be set to the addresses of the static strings "blah" and "hmm".

//If you do want to be able to change the actual string content, the you have to do something like
char a[2][14];
strcpy(a[0], "blah");
strcpy(a[1], "hmm");
//This will allocate two consecutive arrays of 14 chars each, after which the content of the static strings will be copied into them.
```

### 整型数转换为string

```cpp
int a = 10;
stringstream ss;
ss << a;
string str = ss.str();

//清空stringstream
m.str("");
```

### 16进制字符串转换为整数字符串

```c
char str[] = "0x1800785";
int num;

sscanf(str, "%x", &num);
printf("0x%x %i\n", num, num); 
```

### C++ string与C字符串互转

```c++
//string转换为C字符串
string str = "abc";
char arr[100];

strncpy(arr, str.c_str(), str.size());


//c字符串转换为string
char cStr[] = "hello";
string str(cStr);
```

### 分割字符串
```cpp
vector<string> SplitString(const string& sourceStr, const string& delimiter)
{
    string tmp = sourceStr;
    vector<string> output;

    size_t pos = 0;
    string token;
    while ((pos = tmp.find(delimiter)) != string::npos)
    {
        token = tmp.substr(0, pos);
        cout << token << endl;
        output.push_back(token);
        tmp.erase(0, pos + delimiter.length());
    }
    cout << tmp << endl;
    output.push_back(tmp);

    return output;
}
```
