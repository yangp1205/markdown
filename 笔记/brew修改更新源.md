# 使用国内镜像源

## 使用中科大源

```bash
# 步骤一
cd "$(brew --repo)"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git

# 步骤二
cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git

#步骤三
brew update
```

## 还原官方源

```bash
cd "$(brew --repo)"
git remote set-url origin https://github.com/Homebrew/brew.git

cd "$(brew --repo)/Library/Taps/homebrew/homebrew-core"
git remote set-url origin https://github.com/Homebrew/homebrew-core

brew update
```
