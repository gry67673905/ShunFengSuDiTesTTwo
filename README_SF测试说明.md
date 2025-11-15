# 2025 全国大学生软件测试大赛 Web 应用测试省赛（顺丰官网）

本仓库包含：

- `测试用例_顺丰Web测试省赛.xlsx`：根据需求 R001–R010 设计的 27 条测试用例。
- `test_SF.py`：基于 Selenium + Pytest 的自动化脚本，按照 R001–R010 分别实现 `test_SF_R001` ~ `test_SF_R010`。
- `.github/workflows/run-sf-tests.yml`：GitHub Actions 工作流文件，用于在云端运行自动化脚本并生成截图。
- `requirements.txt`：Python 依赖列表。

## 在本地或 GitHub 上运行

1. 将上述文件全部放入同一个 GitHub 仓库根目录（`.github/workflows` 目录结构保持不变）。
2. 仓库根目录下应包含：

   ```text
   .github/
     workflows/
       run-sf-tests.yml
   test_SF.py
   requirements.txt
   测试用例_顺丰Web测试省赛.xlsx
   ```

3. 推送到 GitHub 后，在仓库的 **Actions** 页面手动触发 `Run SF Web Tests` 工作流；
   工作流会：
   - 安装 Chrome 和依赖；
   - 运行 `pytest test_SF.py`；
   - 在仓库运行环境中生成 `screenshots` 目录和所有截图；
   - 将 `screenshots` 目录作为 artifact 上传，供你下载。

4. 下载 artifact 中的 `screenshots` 文件夹，确认包含所有测试用例文档中“截图文件名”列对应的截图；
   将该 `screenshots` 文件夹用 ZIP 格式压缩后，即可作为“文件三 截图压缩包”提交。

> 注意：比赛正式提交前，如果评测环境是 Windows + 本地 ChromeDriver，需确认 `test_SF.py` 中
> `executable_path` 保持为官方提供的路径。
