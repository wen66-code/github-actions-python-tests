# github-actions-python-tests

一个用于练习 Python 单元测试与 GitHub Actions 的小型示例仓库。`calculator.py` 提供加法与乘法函数，`test_calculator.py` 使用 pytest 检查普通输入、负数与零值。

## 文件结构

- `calculator.py`：实现 `add(a, b)` 和 `multiply(a, b)`。
- `test_calculator.py`：包含两个测试函数及四个断言。
- `.github/workflows/ci.yml`：在 GitHub Actions 中运行测试。

## 在本地运行测试

建议使用 Python 3.11（与 CI 环境一致）及可用的 `pip`。克隆仓库并进入目录后执行：

```bash
python -m pip install pytest
python -m pytest -v
```

预期结果是 `test_add` 与 `test_multiply` 均通过。也可以在 Python 解释器中导入函数：

```python
from calculator import add, multiply

print(add(2, 3))       # 5
print(multiply(3, 4))  # 12
```

## 自动化测试

工作流在推送提交或创建 Pull Request 时触发，使用 `ubuntu-latest` 和 Python 3.11，安装 pytest 后执行 `pytest -v`。运行结果可在仓库的 **Actions** 页面查看。

## 参与修改

提交改动前，请在本地运行测试，并在 Pull Request 中说明修改目的、变更内容和验证结果。此仓库主要用于 GitHub 协作流程练习。
