# Claude Commands 工具依赖检查与安装指南

## 概述

本文档详细分析了 `claude/commands/` 目录下所有自定义命令所需的工具依赖，并提供了完整的安装指南。

## 当前系统工具状态

### ✅ 已安装的工具

| 工具 | 版本 | 状态 |
|------|------|------|
| Git | 2.45.1.windows.1 | ✅ 已安装 |
| Node.js | v22.17.1 | ✅ 已安装 |
| npm | 10.9.2 | ✅ 已安装 |
| Python | 3.11.5 | ✅ 已安装 |
| Go | go1.24.3 | ✅ 已安装 |
| Rust | 1.87.0 | ✅ 已安装 |
| Cargo | 1.87.0 | ✅ 已安装 |
| ripgrep (rg) | 13.0.0 | ✅ 已安装 |
| GitHub CLI (gh) | 2.78.0 | ✅ 已安装 |
| curl | 8.7.1 | ✅ 已安装 |
| Maven (mvn) | 3.9.8 | ✅ 已安装 |
| pytest | ✅ 已安装 |
| jq | 1.6 | ✅ 已安装 |

### ❌ 缺失的工具

| 工具 | 状态 | 安装优先级 |
|------|------|------------|
| Deno | ❌ 缺失 | 高 |
| Docker | ❌ 缺失 | 高 |
| kubectl | ❌ 缺失 | 高 |
| Helm | ❌ 缺失 | 中 |
| Skaffold | ❌ 缺失 | 中 |
| Terraform | ❌ 缺失 | 中 |
| fd | ❌ 缺失 | 中 |

## 详细安装指南

### 1. Deno 安装

**Windows 安装方法:**

```powershell
# 方法1: 使用 PowerShell
irm https://deno.land/install.ps1 | iex

# 方法2: 使用 Chocolatey
choco install deno

# 方法3: 使用 Scoop
scoop install deno

# 方法4: 手动下载
# 访问 https://deno.land/
# 下载 Windows 版本并添加到 PATH
```

**验证安装:**
```bash
deno --version
```

### 2. Docker 安装

**Windows 安装方法:**

```powershell
# 方法1: 使用 Docker Desktop
# 访问 https://www.docker.com/products/docker-desktop/
# 下载并安装 Docker Desktop for Windows

# 方法2: 使用 Winget
winget install Docker.DockerDesktop

# 方法3: 使用 Chocolatey
choco install docker-desktop
```

**验证安装:**
```bash
docker --version
docker run hello-world
```

### 3. kubectl 安装

**Windows 安装方法:**

```powershell
# 方法1: 使用 Chocolatey
choco install kubernetes-cli

# 方法2: 使用 Scoop
scoop install kubectl

# 方法3: 手动安装
# 下载最新版本: https://dl.k8s.io/release/v1.30.0/bin/windows/amd64/kubectl.exe
# 添加到 PATH 环境变量
```

**验证安装:**
```bash
kubectl version --client
```

### 4. Helm 安装

**Windows 安装方法:**

```powershell
# 方法1: 使用 Chocolatey
choco install kubernetes-helm

# 方法2: 使用 Scoop
scoop install helm

# 方法3: 手动安装
# 下载: https://get.helm.sh/helm-v3.15.0-windows-amd64.zip
# 解压并将 helm.exe 添加到 PATH
```

**验证安装:**
```bash
helm version
```

### 5. Skaffold 安装

**Windows 安装方法:**

```powershell
# 方法1: 使用 Chocolatey
choco install skaffold

# 方法2: 使用 Scoop
scoop install skaffold

# 方法3: 手动安装
# 下载: https://github.com/GoogleContainerTools/skaffold/releases
# 将 skaffold.exe 添加到 PATH
```

**验证安装:**
```bash
skaffold version
```

### 6. Terraform 安装

**Windows 安装方法:**

```powershell
# 方法1: 使用 Chocolatey
choco install terraform

# 方法2: 使用 Scoop
scoop install terraform

# 方法3: 手动安装
# 下载: https://www.terraform.io/downloads
# 解压并将 terraform.exe 添加到 PATH
```

**验证安装:**
```bash
terraform version
```

### 7. fd (find 替代工具) 安装

**Windows 安装方法:**

```powershell
# 方法1: 使用 Chocolatey
choco install fd

# 方法2: 使用 Scoop
scoop install fd

# 方法3: 使用 Cargo (需要 Rust)
cargo install fd-find

# 方法4: 手动下载
# 访问: https://github.com/sharkdp/fd/releases
# 下载 fd-vX.X.X-x86_64-pc-windows-msvc.zip
# 解压并将 fd.exe 添加到 PATH
```

**验证安装:**
```bash
fd --version
```

## 包管理器安装指南

### Chocolatey 安装

```powershell
# 以管理员身份运行 PowerShell
Set-ExecutionPolicy Bypass -Scope Process -Force
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```

### Scoop 安装

```powershell
# 安装 Scoop
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
irm get.scoop.sh | iex

# 添加额外仓库
scoop bucket add extras
scoop bucket add versions
```

## 依赖工具按命令分类

### Git 相关命令
- `/git/commit/commit.md`
- `/git/commit/commit-push.md`
- `/git/merge/merge-main.md`
- `/git/pr/pr-check.md`
- `/git/pr/pr-create.md`
- `/git/pr/pr-review.md`
- `/git/pr/pr-update.md`
- `/git/resolve-merge-conflicts.md`
- `/git/review/review-git.md`

**所需工具:** Git, GitHub CLI (gh)

### DevOps/Kubernetes 相关命令
- `/kubernetes/k8s-debug.md`
- `/ops/deploy/containerize.md`
- `/ops/deploy/deploy.md`
- `/ops/infra/infra-status.md`
- `/ops/monitor/monitor.md`
- `/ops/monitor/observe.md`

**所需工具:** kubectl, Helm, Docker, Skaffold

### 代码分析与重构命令
- `/code/analyze/bottleneck.md`
- `/code/analyze/dependencies.md`
- `/code/analyze/technical-debt.md`
- `/code/fix/bug-fix.md`
- `/code/refactor/refactor.md`
- `/code/refactor/simplify.md`
- `/code/refactor/standardize.md`

**所需工具:** rg (ripgrep), fd, jq

### 测试相关命令
- `/test/analyze/coverage.md`
- `/test/debug/debug.md`
- `/test/fix/flaky-fix.md`
- `/test/generate-tests.md`
- `/test/run/load-test.md`
- `/test/run/tdd.md`
- `/test/run/validate.md`

**所需工具:** pytest, Node.js (npm), Deno

### 文档相关命令
- `/docs/analyze/explain.md`
- `/docs/generate-docs.md`
- `/docs/manage/docs-add.md`
- `/docs/manage/docs-init.md`
- `/docs/manage/docs-update.md`

**所需工具:** Node.js, Python

## 环境变量配置

确保以下工具已添加到 PATH 环境变量中：

```bash
# 检查当前 PATH
echo $env:PATH

# 添加工具路径 (根据需要调整)
$env:PATH += ";C:\Program Files\Docker\Docker\resources\bin"
$env:PATH += ";C:\ProgramData\chocolatey\bin"
$env:PATH += ";$env:USERPROFILE\.cargo\bin"
$env:PATH += ";$env:USERPROFILE\scoop\shims"
$env:PATH += ";$env:USERPROFILE\.deno\bin"
```

## 验证所有工具安装

创建验证脚本 `verify-tools.ps1`:

```powershell
$tools = @(
    "git", "node", "npm", "python", "go", "rustc", "cargo",
    "rg", "gh", "curl", "mvn", "pytest", "jq",
    "deno", "docker", "kubectl", "helm", "skaffold", "terraform", "fd"
)

foreach ($tool in $tools) {
    try {
        $version = & $tool --version 2>$null
        Write-Host "✅ $tool : $($version -join ' ')" -ForegroundColor Green
    } catch {
        Write-Host "❌ $tool : 未安装" -ForegroundColor Red
    }
}
```

## 故障排除

### 常见问题

1. **权限问题**: 以管理员身份运行 PowerShell
2. **网络问题**: 检查代理设置或使用国内镜像
3. **PATH 问题**: 重启终端或重新加载配置文件
4. **版本冲突**: 使用版本管理工具 (nvm, pyenv, etc.)

### 工具替代方案

- **fd**: 可以使用系统自带的 `find` 或 PowerShell 的 `Get-ChildItem`
- **rg**: 可以使用 `grep` 或 `Select-String`
- **jq**: 可以使用 PowerShell 的 `ConvertFrom-Json`

## 更新和维护

定期更新工具版本：

```powershell
# Chocolatey 更新
choco upgrade all -y

# Scoop 更新
scoop update
scoop update *

# Cargo 更新
cargo install-update -a

# npm 更新
npm update -g
```

## 结论

安装所有缺失工具后，Claude 命令将能够完全正常运行。建议优先安装 Deno、Docker 和 kubectl，这些是大多数 DevOps 和开发相关命令的核心依赖。