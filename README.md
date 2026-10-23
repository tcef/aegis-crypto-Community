# AEGIS — 大模型资产安全保护系统 / AI Model Asset Protection System

社区版 · 免费使用 — 专为 AI 模型设计的加密保护与安全部署工具
Community Edition · Free — encryption protection and secure deployment for AI models

> 📮 反馈与订阅 / Feedback & Subscribe：aegiscrypto@139.com 

> ⚠️ **内测版本 / Beta**：当前为内测版本，部分模型尚未经过充分压力测试；如遇问题，欢迎通过上方邮箱反馈。
> **Beta release**: This is a beta version. Some models have not been fully stress-tested. If you encounter issues, feedback is welcome via the email above.

## 🔐 产品说明 / Product Overview

### 产品定位 / Positioning

大模型从训练、微调到上线，需要投入大量算力、数据与时间，模型文件本身即是企业与开发者的核心资产。然而模型文件一旦被拷贝或泄露，投入即付诸东流。AEGIS 是一款面向 **AI 模型资产安全保护** 的工具，通过加密保护、安全部署与授权管理，让模型资产从存储、传输到部署的**全链路**都处于保护之下，防止未授权访问、复制与盗用。
Training, fine-tuning, and shipping a large model demands enormous compute, data, and time; the model file itself is the core asset. AEGIS is an **AI model asset security protection** tool that keeps that asset protected across storage, transfer, and deployment — against unauthorized access, copying, and theft.

### 核心能力 / Core Capabilities

**1. 模型资产加密保护 / Model encryption**
对 AI 模型文件进行加密。加密后的模型无法被未授权方读取、加载或使用——即使文件被拷贝或窃取，没有密钥也无法还原。从源头杜绝模型资产的盗用与泄露。
Encrypts model files so unauthorized parties cannot read, load, or use them — even if copied, the model cannot be restored without the key.

**2. 安全部署与推理 / Secure deployment & inference**
加密后的模型可直接交给推理服务加载，运行时在内存中完成还原、不写入磁盘，避免部署环节的泄露风险。推理服务兼容主流调用接口，可直接接入现有业务。
Encrypted models load directly into the inference service; restoration happens in memory without touching disk. The service is compatible with mainstream calling interfaces.

**3. 授权分级管理 / License & tiering**
通过许可证控制使用权限，分为免费版、专业版、企业版三档，按档位开放 GPU 数量、部署节点、模型体量、水印等能力。许可证绑定设备，换机需重新授权，有效防止授权被共享或越权使用。
Licenses control permissions across three tiers (free / pro / enterprise), opening GPU count, deployment nodes, model size, and watermark capabilities per tier. Licenses are bound to the device; switching machines requires re-authorization.

**4. 水印追踪 / Watermark tracing**
支持对生成内容添加水印，用于追踪内容来源、防止盗用与二次分发。
Adds watermarks to generated content to trace its origin and deter misuse and redistribution.

**5. 高性能 / High performance**
支持 GPU 加速、多卡并行、多节点部署，满足大模型在高并发、大规模场景下的推理性能需求。
Supports GPU acceleration, multi-card parallelism, and multi-node deployment for high-concurrency, large-scale inference.

**6. 智能加载 / Smart loading**
推理时仅还原正在使用的部分，显著降低内存占用，让更大体量的模型在有限资源下也能稳定运行。
During inference, only the parts actually in use are restored, sharply reducing memory so larger models run on limited resources.

**7. 跨平台 / Cross-platform**
支持 Windows、macOS、Linux 三大平台，一套方案覆盖主流开发与部署环境。
Runs on Windows, macOS, and Linux — one solution for mainstream development and deployment environments.

**8. 易集成 / Easy integration**
提供命令行工具、图形界面与 Python SDK 三种使用方式，可轻松嵌入训练脚本、CI/CD 流水线与 Docker 部署。
Offers CLI, GUI, and a Python SDK, easily embedded into training scripts, CI/CD pipelines, and Docker deployments.

**9. 内容不可辨识 / Content obfuscation**
加密后的模型不再以明文形式存在，文件名也采用哈希等无意义命名——从内容到名称都无法判断其原本是什么模型，难以被他人分析或定位价值。即使文件被获取，也无法直接使用或还原。
Encrypted models no longer exist as plaintext, and file names use meaningless hashes — neither the content nor the name reveals what the model is. Even if obtained, the file cannot be used or restored directly.

### 为什么模型需要保护 / Why Protect Models

- **投入巨大 / Huge investment**：大模型的训练与微调需要大量算力、数据与时间，模型文件是开发者与企业的核心资产。
  Training and fine-tuning a large model demands enormous compute, data, and time; the model file is the core asset.
- **复制成本极低 / Trivial to copy**：模型文件一旦泄露，可被轻易复制、传播与二次分发，前期投入无法追回。
  Once leaked, a model file can be copied, spread, and redistributed at near-zero cost, with no way to recover the investment.
- **可被直接分析 / Easily analyzable**：未加密的模型文件可被直接分析，暴露其能力与商业价值。
  An unencrypted model can be analyzed directly, exposing its capabilities and business value.
- **授权容易失控 / Hard to control authorization**：缺乏有效的授权管理，模型可能被越权部署或超出约定范围使用。
  Without effective authorization management, models may be deployed beyond the agreed scope.

### 适用人群 / Who It's For

- **AI 开发者 / AI developers**：训练、微调模型后，需要保护模型资产、防止被复制盗用。
- **企业 / Enterprises**：需要对模型资产进行授权分发，按权限控制使用范围与期限。
- **算力服务商 / Compute providers**：需要为企业客户提供定制化的模型保护与授权方案。

### 支持范围 / Supported Scope

- **模型类型 / Model formats**：支持 PyTorch（.pt / .pth / .bin）、ONNX（.onnx）、GGUF（.gguf）等主流 AI 模型格式。
  Supports PyTorch (.pt / .pth / .bin), ONNX (.onnx), GGUF (.gguf), and more.
- **运行环境 / Platforms**：Windows、macOS、Linux 三大平台。
  Windows, macOS, and Linux.
- **部署方式 / Deployment**：本机、服务器、Docker 容器均可。
  Local machines, servers, and Docker containers.
- **调用接口 / Interfaces**：推理服务兼容主流调用接口，可直接接入现有业务。
  The inference service is compatible with mainstream calling interfaces for easy integration.

### 典型场景 / Typical Scenarios

1. **训练完成后立即加密 / Encrypt right after training**：训练或微调完成后，一条命令完成加密，防止模型文件在存储与传输中被窃取。
   Encrypt with a single command right after training or fine-tuning, preventing theft during storage and transfer.
2. **加密模型安全部署 / Secure deployment of encrypted models**：加密后的模型直接部署为推理服务，运行时内存还原、全程不落盘。
   Deploy encrypted models directly as an inference service; restoration happens in memory with nothing written to disk.
3. **模型授权分发 / Authorized distribution**：将加密模型分发给客户或合作方，通过许可证控制使用权限与期限。
   Distribute encrypted models to customers or partners, controlling permissions and duration via licenses.

## 🎯 版本说明 / Editions

| 版本 / Edition | 仓库 / Repo | 说明 / Description |
|------|------|------|
| **社区版 Community**（FreePersonal） | [aegis-crypto-Community](https://github.com/tcef/aegis-crypto-Community) | 免费开放：加密、解密、部署推理等核心能力 / Free: core encryption, decryption & inference deployment |
| **专业版 Pro**（ProPersonal） | [aegis-crypto-pro](https://github.com/tcef/aegis-crypto-pro)（私有） | 高级算法、GPU 加速、多节点部署、优先支持 / Advanced algorithms, GPU acceleration, multi-node deployment, priority support |
| **企业版 Enterprise**（ComputeProvider） | [aegis-crypto-Enterprise](https://github.com/tcef/aegis-crypto-Enterprise)（私有） | 算力服务商定制，完整功能与专属支持 / Compute-provider custom, full features & dedicated support |

本仓库公开发布**社区版**。专业版 / 企业版面向付费客户定向发布，升级无需重装（导入许可证即可生效）。
This repository publicly releases the **Community Edition**. Pro / Enterprise are distributed to paying customers; upgrading requires no reinstall (import a license to activate).

## 🔄 升级指南 / Upgrade Guide

免费版可随时升级到专业版或企业版，许可证、配置与已加密数据全部原样保留。
You can upgrade from Community to Pro or Enterprise at any time; your license, configuration, and encrypted data are all preserved.

### 方式一：只导入许可证（多数情况，无需重装）/ Option 1: Import a license (most cases, no reinstall)

以下需求，只需在「许可证」页面导入开发者签发的许可证文件即可，客户端无需更换：
For these needs, just import the license file issued by the developer on the "License" page — no need to replace the client:

- 使用更大体量的模型 / Use larger models
- 使用更多 GPU 卡 / Use more GPU cards
- 去除生成内容中的水印 / Remove the watermark from generated content
- 部署到服务器（多节点）/ Deploy to servers (multi-node)
- 续费或调整使用档位 / Renew or change your tier

### 方式二：下载对应版本客户端（需要高级算法 / 多卡并行时）/ Option 2: Download the matching client (only for advanced algorithms / multi-card parallelism)

免费版客户端内置的是基础加密能力。若你需要以下能力，需下载专业版或企业版客户端：
The Community client ships the core encryption capabilities. For the following, download the Pro or Enterprise client:

- 更多高级加密算法 / More advanced encryption algorithms
- 多卡并行计算 / Multi-card parallel computation

下载地址 / Download（私有仓库，需授权 / private, authorization required）:
- 专业版 Pro：[aegis-crypto-pro](https://github.com/tcef/aegis-crypto-pro)
- 企业版 Enterprise：[aegis-crypto-Enterprise](https://github.com/tcef/aegis-crypto-Enterprise)

步骤 / Steps：从对应仓库下载客户端 → 解压后用新客户端替换原客户端（只需替换一个程序文件）→ 原许可证、配置、数据全部保留，启动即自动识别。
Download the client from the corresponding repo → extract and replace the original client (only one program file) → your license, configuration, and data are all kept, and it is recognized automatically on startup.

## 🚀 快速开始 / Quick Start

### 安装 / Install

#### Linux / macOS

```bash
# 社区版（国际版）下载，按平台选择 / Download the Community Edition (international), pick your platform
wget https://github.com/tcef/aegis-crypto-Community/releases/download/v0.1.0/aegis-free-international-0.1.0-linux-x64.tar.gz
# macOS (Apple Silicon):  .../aegis-free-international-0.1.0-macos-arm64.tar.gz
# macOS (Intel):          .../aegis-free-international-0.1.0-macos-x64.tar.gz

# 解压 / Extract
tar -xzf aegis-free-international-0.1.0-linux-x64.tar.gz

# 进入目录，二进制名为 aegis / Enter the directory; the binary is named aegis
cd aegis-free-international-0.1.0-linux-x64/
./aegis version
```

#### Windows

```powershell
Invoke-WebRequest -Uri https://github.com/tcef/aegis-crypto-Community/releases/download/v0.1.0/aegis-free-international-0.1.0-windows-x64.zip -OutFile aegis.zip
Expand-Archive aegis.zip
```

### 图形界面（UI）/ Graphical Interface

解压后运行图形界面（同一账号登录态，也可纯命令行使用）：
After extracting, launch the graphical interface (same login session; the CLI can also be used on its own):

```bash
./aegis ui   # 自动打开浏览器（监听 127.0.0.1:7878）/ Opens the browser automatically (listens on 127.0.0.1:7878)
```

> 图形界面内置了详细的使用说明：CLI 命令参考、API 文档、部署与 GPU 规划等均可直接在界面内查看。上文的命令行用法覆盖了核心操作，完整参数请以 UI 内的指南为准。
> The UI ships detailed built-in guides — CLI command reference, API docs, deployment, and GPU planning — all viewable inside the interface. The CLI usage above covers the essentials; for full parameters, refer to the in-UI guide.

### 基本使用（命令行）/ Basic Usage (CLI)

#### 1. 加密模型 / Encrypt a model

```bash
# 加密并生成密钥（推荐：口令保护，交互式输入两次口令）/ Encrypt & generate a key (recommended: passphrase-protected; enter it twice)
./aegis encrypt ~/models/<模型目录> ~/aegis_models/<模型>_encrypted \
  --generate-key ~/aegis_models/<模型>.keywrap --force

# 使用已有密钥加密 / Encrypt with an existing key
./aegis encrypt ~/models/<模型目录> ~/aegis_models/<模型>_encrypted \
  --key-file ~/aegis_models/<模型>.keywrap --force
```

`encrypt` 会自动检测目录 / 单文件 / GGUF，支持 PyTorch、ONNX、GGUF 等主流模型格式。
`encrypt` auto-detects a directory / single file / GGUF, and supports PyTorch, ONNX, GGUF and more.

#### 2. 解密模型 / Decrypt a model

```bash
./aegis decrypt <加密目录> <输出目录> --key-file ~/aegis_models/<模型>.keywrap
# 加密目录 / encrypted dir → 输出目录 / output dir
```

#### 3. 查看版本 / 诊断 / Version & Diagnose

```bash
./aegis version     # 查看版本与支持能力 / Show version & capabilities
./aegis diagnose    # 诊断输出（脱敏，用于问题定位）/ Redacted diagnostics for troubleshooting
```

## 🚀 部署与推理服务 / Deployment & Inference

AEGIS 的核心价值在于「加密 → 部署 → 安全调用」一条龙：加密产物可直接交给推理服务加载，模型数据在内存中解密、不落盘。
AEGIS's core value is the end-to-end "encrypt → deploy → secure serving" flow: encrypted artifacts are loaded directly by the inference service, and model data is decrypted in memory without touching disk.

```bash
# 1) 加密并生成密钥（口令交互式输入两次）/ Encrypt & generate a key (enter the passphrase twice)
./aegis encrypt ~/models/<模型目录> ~/aegis_models/<模型>_encrypted \
  --generate-key ~/aegis_models/<模型>.keywrap --force

# 2) 把 <模型>_encrypted 目录与 <模型>.keywrap 一起拷贝到部署机（scp / U 盘均可）
#    Copy the <模型>_encrypted dir and <模型>.keywrap to the deploy machine (scp / USB both fine)

# 3) 部署机启动推理服务（Ollama / OpenAI 兼容 API，默认端口 11434）
#    Start the inference service on the deploy machine (Ollama / OpenAI compatible, default port 11434)
./aegis serve ~/aegis_models/<模型>_encrypted \
  --keywrap ~/aegis_models/<模型>.keywrap --device cpu
```

启动后即可调用 / Once started, call it with:

```bash
# Ollama 客户端 / Ollama client
ollama run default

# 或 OpenAI 兼容接口 / or the OpenAI-compatible endpoint
curl http://127.0.0.1:11434/v1/models
```

停止服务 / Stop the service:

```bash
./aegis serve-stop    # 或前台 Ctrl+C，或在 UI 部署页点「停止」/ or Ctrl+C in the foreground, or the Stop button on the UI Deploy page
```

> 部署机需 Python ≥ 3.9，并安装发布包 `python/` 目录内的组件（核心组件必装、加速组件推荐），详见包内《安装说明》。加速组件安装后加载更快、内存占用更低；未安装时自动回退，功能与安全性不变。
> The deploy machine needs Python ≥ 3.9 and the components in the release `python/` directory (core component required, accelerator recommended); see the bundled install guide. With the accelerator, loading is faster and memory usage lower; without it the system falls back automatically with no change in function or security.

### GPU 部署（可选）/ GPU Deployment (optional)

```bash
./aegis serve ~/aegis_models/<模型>_encrypted \
  --keywrap ~/aegis_models/<模型>.keywrap --device cuda
```

部署前可用 `./aegis gpu identify` 识别本机 GPU、`./aegis gpu recommend` 规划 GPU 数量。
Before deploying, use `./aegis gpu identify` to detect local GPUs and `./aegis gpu recommend` to plan the GPU count.

### SafeTensors 模型 → GGUF 加密（可选）/ SafeTensors → GGUF (optional)

多文件的 SafeTensors 模型，推荐先转成标准 GGUF 再加密：
For multi-file SafeTensors models, we recommend converting to a standard GGUF first, then encrypting:

```bash
./aegis st-to-gguf-encrypt ~/models/<HF模型目录> ~/aegis_models/<模型>_gguf_encrypted \
  --generate-key ~/aegis_models/<模型>.keywrap \
  --quantization q4_k_m --force
```

## 📖 集成示例 / Integration Examples

### 场景 1：训练完成后自动加密 / Scenario 1: encrypt right after training

**原来的训练脚本 / Original training script:**

```bash
python train.py && cp -r model_dir /release/
```

**集成 AEGIS 后 / With AEGIS:**

```bash
python train.py && ./aegis encrypt model_dir /release/model_encrypted \
  --generate-key /release/model.keywrap --force
```

### 场景 2：Python 脚本中调用 / Scenario 2: call from Python

```python
import subprocess, sys

def encrypt_model(input_dir, output_dir, key_path):
    """加密模型目录 / Encrypt a model directory"""
    result = subprocess.run(
        ["./aegis", "encrypt", input_dir, output_dir,
         "--generate-key", key_path, "--force"],
        capture_output=True, text=True,
    )
    if result.returncode != 0:
        print(f"加密失败 / Encrypt failed: {result.stderr}", file=sys.stderr)
        sys.exit(1)
    print(f"✓ 加密成功 / Encrypted: {output_dir}")
    print(f"✓ 密钥已保存 / Key saved: {key_path}")

def decrypt_model(input_dir, output_dir, key_path):
    """解密模型目录 / Decrypt a model directory"""
    result = subprocess.run(
        ["./aegis", "decrypt", input_dir, output_dir,
         "--key-file", key_path, "--force"],
        capture_output=True, text=True,
    )
    if result.returncode != 0:
        print(f"解密失败 / Decrypt failed: {result.stderr}", file=sys.stderr)
        sys.exit(1)
    print(f"✓ 解密成功 / Decrypted: {output_dir}")
```

> 发布包内含官方 Python 组件（`python/aegis_crypto-*.whl`），需要更深度集成时建议直接使用，而非调用命令行。
> The release ships an official Python component (`python/aegis_crypto-*.whl`); for deeper integration, prefer it over calling the CLI.

### 场景 3：Docker 容器内部署 / Scenario 3: deploy in Docker

```dockerfile
FROM python:3.10-slim

# 复制 AEGIS 与推理组件 / Copy AEGIS and the inference components
COPY aegis /usr/local/bin/aegis
COPY python/ /opt/aegis-python/
RUN pip install "/opt/aegis-python/aegis_crypto-*.whl[serve]" && \
    pip install /opt/aegis-python/llama_cpp_python-*.whl

# 复制加密模型与密钥 / Copy the encrypted model and key
COPY <模型>_encrypted /models/
COPY <模型>.keywrap /run/secrets/

# 启动推理服务（口令经 Docker Secret 注入）/ Start the inference service (passphrase via Docker Secret)
CMD ./aegis serve /models/ --keywrap /run/secrets/<模型>.keywrap \
    --password-file /run/secrets/<模型>_pass --host 0.0.0.0
```

```bash
# 构建镜像 / Build the image
docker build -t my-model-service .

# 运行容器（口令通过 Docker Secret 挂载为文件）/ Run (passphrase mounted as a Docker Secret file)
docker secret create model_pass <(echo "your-passphrase")
docker service create --name model-service --secret model_pass my-model-service
```

### 场景 4：CI/CD 流水线集成 / Scenario 4: CI/CD pipeline

```yaml
name: Train and Encrypt Model

on:
  push:
    branches: [main]

jobs:
  train:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.9'

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Train model
        run: python train.py

      - name: Download AEGIS
        run: |
          wget https://github.com/tcef/aegis-crypto-Community/releases/download/v0.1.0/aegis-free-international-0.1.0-linux-x64.tar.gz
          tar -xzf aegis-free-international-0.1.0-linux-x64.tar.gz

      - name: Encrypt model
        run: |
          ./aegis-free-international-0.1.0-linux-x64/aegis encrypt model_dir model_encrypted \
            --generate-key key.keywrap --force

      - name: Upload encrypted model
        uses: actions/upload-artifact@v3
        with:
          name: encrypted-model
          path: |
            model_encrypted/
            key.keywrap
```

## ❓ 常见问题 / FAQ

### Q: 加密会改变我的模型精度或结构吗？/ Will encryption change my model's precision or structure?

**A:** 不会。AEGIS 使用文件级加密，不修改模型内部数据。解密后的文件与原始文件完全一致（通过 SHA-256 哈希验证）。加密只是对文件进行加壳保护，不会触及模型本身。
**A:** No. AEGIS uses file-level encryption and does not modify the model's internal data. The decrypted file is identical to the original (verified by SHA-256 hash). Encryption only wraps the file; it never touches the model itself.

### Q: 支持哪些模型格式？/ Which model formats are supported?

**A:** 支持以下格式 / The following formats are supported:
- PyTorch (.pt, .pth, .bin)
- ONNX (.onnx)
- TensorFlow (.pb, .h5)
- SafeTensors (.safetensors)
- GGUF (.gguf)

### Q: 智能部署（智能加载）如何加速？/ How does smart deployment (smart loading) speed things up?

**A:** 部署机安装加速版推理组件（发布包 `python/` 目录内，一键 `pip install`）后，推理时只还原正在使用的数据，加载更快、内存占用更低。未安装时自动回退全量解密，不影响功能与安全性。
**A:** After installing the accelerated inference component on the deploy machine (inside the release `python/` directory, one `pip install`), inference only restores the data actually in use, giving faster loading and lower memory. Without it, the system falls back to full decryption automatically, with no impact on function or security.

### Q: 加密后的文件大小会变化吗？/ Will the file size change after encryption?

**A:** 默认启用压缩，加密后文件大小通常与原始文件相近（取决于数据可压缩性），并会附加少量元数据与认证信息，对大文件影响可忽略不计。
**A:** Compression is enabled by default, so the encrypted size is usually close to the original (depending on compressibility), plus a small amount of metadata and authentication info. For large files the impact is negligible.

### Q: 密钥丢失了怎么办？/ What if I lose the key?

**A:** 很遗憾，如果密钥（`.keywrap` 文件）及其口令都丢失，将无法恢复加密的模型。请务必妥善保管，建议：
**A:** Unfortunately, if both the key (`.keywrap` file) and its passphrase are lost, the encrypted model cannot be recovered. Keep them safe and consider:
- 将密钥备份到安全的位置 / Back up the key to a secure location
- 使用密钥管理系统（如 AWS KMS、Azure Key Vault）/ Use a key management system (e.g. AWS KMS, Azure Key Vault)
- 不要将密钥提交到版本控制系统 / Never commit keys to version control

### Q: 社区版有什么限制？/ Are there limits in the Community Edition?

**A:** 社区版免费开放加密、解密、部署推理等核心能力。专业版 Pro 额外提供：
**A:** The Community Edition is free for core encryption, decryption, and inference deployment. Pro additionally offers:
- XChaCha20-Poly1305、AES-GCM-SIV 等高级算法 / Advanced algorithms such as XChaCha20-Poly1305, AES-GCM-SIV
- GPU 加速（CUDA/OpenCL）/ GPU acceleration (CUDA/OpenCL)
- 多节点部署 / Multi-node deployment
- 优先技术支持 / Priority support

访问 https://aegis-crypto.com/pro 了解更多。 / Visit https://aegis-crypto.com/pro to learn more.

## 🎯 核心特性 / Key Features

### ✅ 安全可靠 / Secure & Reliable
- **完整性验证 / Integrity verification**：SHA-256 哈希验证，确保解密后文件完整无损 / SHA-256 hash verification ensures the decrypted file is intact
- **中断恢复 / Interruption recovery**：支持 Ctrl+C 安全中断，自动清理临时文件 / Safe Ctrl+C interruption with automatic temp-file cleanup
- **密钥保护 / Key protection**：密钥经口令包装加密保存，支持硬件绑定 / Keys are passphrase-wrapped and can be hardware-bound

### ✅ 性能优异 / High Performance
- **高速加解密 / Fast**：AES-256-GCM 硬件加速 / AES-256-GCM with hardware acceleration
- **大文件支持 / Large files**：轻松处理 GB 级模型文件 / Easily handles multi-GB model files
- **跨平台 / Cross-platform**：Windows、macOS、Linux 全平台支持 / Windows, macOS, Linux

### ✅ 易于集成 / Easy to Integrate
- **一行命令 / One command**：无需 SDK，无需依赖 / No SDK, no dependencies
- **无缝集成 / Seamless**：轻松嵌入训练脚本、Docker、CI/CD / Fits training scripts, Docker, CI/CD
- **一键部署 / One-click deploy**：加密产物直接交给推理服务安全加载 / Encrypted artifacts load directly into the inference service

## 📊 性能数据 / Performance

以下为社区版在常见环境下的参考耗时（实际速度受硬件与文件特性影响）：
Reference timings for the Community Edition on a common setup (actual speed depends on hardware and file characteristics):

| 文件大小 / File size | 加密耗时 / Encrypt | 解密耗时 / Decrypt |
|---------|---------|---------|
| 1 MB    | 7 ms    | 1 ms    |
| 100 MB  | 569 ms  | 383 ms  |
| 1 GB    | 6.8 s   | -       |

*测试环境 / Test env：Ubuntu 22.04，Intel i7-10700，16 GB RAM*

## 🔧 技术细节 / Technical Details

### 支持的加密算法 / Supported algorithms
- **AES-256-GCM**（默认 / default）
- **ChaCha20-Poly1305**
- 专业版 / Pro：XChaCha20-Poly1305、AES-GCM-SIV、国密 SM2/SM3/SM4 / Chinese SM2/SM3/SM4

### 完整性验证 / Integrity verification
- 使用 SHA-256 哈希算法 / Uses SHA-256 hashing
- 加密时计算原始文件哈希 / Computes the original file hash on encryption
- 解密时自动验证文件完整性 / Verifies integrity automatically on decryption

### 中断恢复机制 / Interruption recovery
- 临时文件保护 / Temp-file protection
- Ctrl+C 信号处理 / Ctrl+C signal handling
- 自动清理临时文件 / Automatic temp-file cleanup

## 📝 反馈与支持 / Feedback & Support

遇到问题、功能建议或订阅专业版 / 企业版，欢迎邮件联系或提交 Issue / Found a bug, have a feature idea, or want to subscribe to Pro / Enterprise? Email us or open an issue:

- 📮 国内用户 / China：aegiscrypto@163.com
- 📮 国际用户 / International：aegiscrypto@zohomail.com
- 🐛 [报告 Bug / Report a bug](https://github.com/tcef/aegis-crypto-Community/issues/new?template=bug_report.md)
- 💡 [功能建议 / Feature request](https://github.com/tcef/aegis-crypto-Community/issues/new?template=feature_request.md)

## 📄 许可证 / License

社区版 - 免费使用与分发。专业版 Pro / 企业版需商业许可，详见 https://aegis-crypto.com/pro。
Community Edition — free to use and distribute. Pro / Enterprise require a commercial license; see https://aegis-crypto.com/pro.

---

**AEGIS — 大模型资产安全保护系统 / AI Model Asset Protection System** - 保护您的 AI 模型资产 / Protect your AI model assets 🔐
