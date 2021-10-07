# Git 

> git repository 

## git常用

### 配置repo为ssh

> 最近总是发现基于https推送仓库时总是报fatal: 发送请求时出错。fatal: 请求被中止: 未能创建 SSL/TLS 安全通道。remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.
> 针对这个问题，把repo的url配置为ssh协议后基本没有这个问题

配置步骤：

- 检查git用户名和邮箱

```bash
git config user.name
git config user.email
```

- 如果没有配置，先配置用户名和邮箱

```bash
git config --global user.name "xxx"
git config --global user.email "xxx"
```

- 检查ssh密钥
> 如果公钥没有配置，则先把本地的公钥配置到github账户的setting-SSH and GPK keys

```sh
ssh -T git@github.com

# 输出：You've successfully authenticated, but GitHub does not provide shell access.
```

- 修改git的remote url

首先查看本地的remote url
```bash
git remote -v

# 输出：
# origin  https://github.com:zyf0201/Docs.git (fetch)
# origin  https://github.com:zyf0201/Docs.git (push)
```

然后修改remote url

```bash
git remote rm origin
git remote add origin [url]
# 其中url的格式为：git@github.com:zyf0201/Docs.git
#例如：
#git remote add origin 'git@github.com:zyf0201/Docs.git'
```
- 删除原来的密钥

  - macos搜索**Keychain Access.app**
  - 选择所有项目
  - 搜索git
  - 删除旧的凭证
  - 重新push