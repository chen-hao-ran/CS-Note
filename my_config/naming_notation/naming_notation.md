# 存储我的程序命名规范

### 路径/文件夹

全部采用小写，使用名词，不使用动词，单词之间使用下划线连接

```
data： 数据集
models：模型
dataprocess：数据处理
logs：日志文件
utils：工具类
```



### 代码文件/类

驼峰命名法则，开头大写，使用名词、动名词

```
ModelingAbstrct：模型训练抽象类
DataSetLoader：数据集加载类
DataProcesser: 数据预处理类
```



### 函数

java使用驼峰命名法，首字母小写，动词加名词

python使用蛇形命名法,全部使用小写字母，使用下划线做为分隔符号

c/c++常规函数使用大小写混合, 取值和设值函数则要求与变量名匹配:

```python
---- def convert_word_to_token():将汉字转换成token
---- def load_origin_data():加载原始数据
---- best_micaroF1：最优微平均
---- max_doument_length：最大文本长度
```

```c++
MyExcitingFunction() 
MyExcitingMethod() 
my_exciting_member_variable()
set_my_exciting_member_variable()
```

---

### 变量

#### 普通变量

小写字母，下划线连接

```
string table_name; 
```

#### 类数据成员

不管是静态的还是非静态的, 类数据成员都可以和普通变量一样, 但要接下划线.

```
class TableInfo {
  ...
 private:
  string table_name_;  // 好 - 后加下划线.
  string tablename_;   // 好.
  static Pool<TableInfo>* pool_;  // 好.
};
```

#### 结构体变量

不管是静态的还是非静态的, 结构体数据成员都可以和普通变量一样, 不用像类那样接尾部下划线:

```
struct UrlTableProperties {
  string name;
  int num_entries;
  static Pool<UrlTableProperties>* pool;
};
```

#### 常量

声明为 constexpr 或 const 的变量, 或在程序运行期间其值始终保持不变的, 命名时以 “k” 开头, 大小写混合

```
const int kDaysInAWeek = 7;
```

#### 宏

```
MY_MACRO_THAT_SCARES_SMALL_CHILDREN
```

---

### 命名空间

命名空间以小写字母命名. 最高级命名空间的名字取决于项目名称. 要注意避免嵌套命名空间的名字之间和常见的顶级命名空间的名字之间发生冲突.

顶级命名空间的名称应当是项目名或者是该命名空间中的代码所属的团队的名字. 命名空间中的代码, 应当存放于和命名空间的名字匹配的文件夹或其子文件夹中.

注意 *不使用缩写作为名称* 的规则同样适用于命名空间. 命名空间中的代码极少需要涉及命名空间的名称, 因此没有必要在命名空间中使用缩写.

要避免嵌套的命名空间与常见的顶级命名空间发生名称冲突. 由于名称查找规则的存在, 命名空间之间的冲突完全有可能导致编译失败. 尤其是, 不要创建嵌套的 `std` 命名空间. 建议使用更独特的项目标识符 (`websearch::index` ，`websearch::index_util`) 而非常见的极易发生冲突的名称 (比如 `websearch::util`).

对于 `internal` 命名空间, 要当心加入到同一 `internal` 命名空间的代码之间发生冲突 (由于内部维护人员通常来自同一团队, 因此常有可能导致冲突). 在这种情况下, 请使用文件名以使得内部名称独一无二 (例如对于 `frobber.h`, 使用 `websearch::index::frobber_internal`).

### 命名规则的特例

如果命名的实体与已有 C/C++ 实体相似, 可参考现有命名策略

`bigopen()`: 函数名, 参照 open() 的形式

`uint`: `typedef`

`bigpos`: `struct` 或 `class`, 参照 `pos` 的形式

`sparse_hash_map`: STL 型实体; 参照 STL 命名约定

`LONGLONG_MAX`: 常量, 如同 `INT_MAX`

