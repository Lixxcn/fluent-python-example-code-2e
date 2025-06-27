# Python 数据模型

_Luciano Ramalho 著《流畅的 Python（第2版）》（O'Reilly, 2020）_ 第一章的示例代码

## 运行测试

### Doctest

使用 Python 标准库中的 ``doctest`` 模块检查独立的 doctest 文件：

    $ python3 -m doctest frenchdeck.doctest -v

检查嵌入在模块中的 doctest：

    $ python3 -m doctest vector2d.py -v

### Jupyter Notebook

安装 ``pytest`` 及其 ``nbval`` 插件：

    $ pip install pytest nbval

运行：

    $ pytest --nbval

---

## 相关解释

### 1. `python3 -m doctest frenchdeck.doctest -v` 是什么写法？

这是在命令行中运行 Python 的一种方式：
- `python3` 表示使用 Python 3 解释器。
- `-m doctest` 表示用 doctest 这个标准库模块来运行。
- `frenchdeck.doctest` 是要检查的文件名。
- `-v` 表示 verbose（详细）模式，会输出更多信息。

这条命令的意思是：用 doctest 模块检查 frenchdeck.doctest 文件中的测试，并详细输出结果。

### 2. doctest 是什么模块？

doctest 是 Python 标准库中的一个模块。它可以自动查找文档字符串（docstring）中的代码示例，并运行这些示例，检查它们的输出是否和文档中写的一致。这样可以保证文档中的代码示例是正确的。

#### docstring 是什么？
docstring（文档字符串）是写在 Python 函数、类、模块开头的字符串，用于描述该对象的用途和用法。通常用三引号括起来，紧跟在定义后面。例如：

```python
def add(a, b):
    """返回 a 和 b 的和"""
    return a + b
```

docstring 一般是开发者手写的，也可以通过一些文档生成工具自动生成模板，但内容通常需要人工补充和完善。

### 3. doctest 如何进行检查？

doctest 会扫描指定的文件或模块，查找形如 Python 交互式命令行（>>>）的代码块，然后执行这些代码，并把实际输出和文档中写的期望输出进行对比。如果一致，测试通过；否则会报告错误。

### 4. "嵌入" 是什么？

这里的“嵌入”指的是 doctest 代码示例直接写在 Python 源代码文件的文档字符串（docstring）里，而不是单独放在 .doctest 文件中。这样可以让文档和代码保持同步。

### 5. `pytest --nbval` 又是什么？

pytest 是一个流行的 Python 测试框架。nbval 是 pytest 的一个插件，可以让 pytest 检查 Jupyter Notebook（.ipynb 文件）中的代码单元格。

`pytest --nbval` 这条命令会自动运行当前目录下所有的 Jupyter Notebook 文件，检查每个代码单元格的输出是否和 notebook 文件中保存的输出一致。如果不一致，就会报告错误。这有助于保证 notebook 文档的可重复性和正确性。
