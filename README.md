## NeContainer 容器

### 一、序列式容器
> 序列式容器： 元素排列顺序与元素本身无关，由添加顺序决定
> 序列式容器包括：vector,list,dequeue,queue,stack,priority queue

### 二、关联式容器
> 序列式容器包括：set map hashmap

### 三、代码示例
```c++
#include <iostream>
#include <vector>
#include <set>
#include <map>
using namespace std;

int main(int argc, const char * argv[]) {
    
    vector<int> vec_1;
    //声明有一个元素空间
    vector<int> vec_2(1);
    //声明6个元素，值都是1
    vector<int> vec_3(6, 1);
    vector<int> vec_4(vec_3);
    //增加元素
    vec_1.push_back(10);
    //通过下标获取元素
    cout << "通过下标获取元素：" << vec_1[0] << endl; //10
    vec_1.front(); //获取队首元素
    vec_1.back(); //获取队尾元素
    vec_1.clear(); //清除
    vec_1.erase(vec_1.begin(), vec_1.end()); //清除指定区间的元素
    cout << "获取vec的容量大小：" << vec_1.capacity() << endl; //1
    
    //set集合，元素不可重复
    set<int> set1 = {1, 2, 3, 4};
    set1.insert(6);
    pair<set<int>::iterator, bool> _pair = set1.insert(1); //是否插入成功
    cout << "set里面有：" << set1.size() << "个元素" <<endl; //4
    set<int>::iterator it = set1.begin();
    set1.end(); //指向最后一个元素的下一个元素
    for(; it != set1.end(); it++) {
        cout << *it << endl;
    }
    
    //map key不能为空，也不能重复，重复的话会覆盖
    map<int, string> map1;
    map<int, string> map2 = {{1, "A"},{2, "B"}};
    map2.insert({3, "C"});
    //修改key为3的元素的值
    map2[3] = "D";
    
    return 0;
}
```