# VSCode ESLint, Prettier & Airbnb Style Guide Setup

### 在 VSCode 中安装扩展

- 在 extensions 中查找并安装 ESLint、Prettier。
- 在设置中修改 Editor: Format On Save 用来在保存时自动格式化代码。
- 在设置中修改 Prettier：Single Quote 代码中使用单引号替代双引号。
- 在设置中修改 Prettier：Jsx Single Quote React 的 JSX 语法中使用单引号代替双引号。

### 安装项目开发依赖

- 安装 ESLint 相关依赖，`npm i -D eslint eslint-plugin-prettier eslint-config-prettier eslint-plugin-node eslint-config-node`
- 安装 Airbnb 规则相关，`npx install-peerdeps --dev eslint-config-airbnb`，本条命令要求 npm 版本>=5。

### 全局安装 ESLint 模块

- `npm i -g eslint`，目的是能够通过命令生成 `.eslintrc`
- 安装完成后，在项目下执行 `eslint --init`，通过一些列的可选项，最终会在项目根路径下生成 ESLint 的配置文件。

### 通过 eslint 或 prettier 自动格式化

- 配置默认格式化工具为二选一，看个人喜好。

### 自定义一些 Lint 配置

.eslintrc.json

```json
{
  "extends": ["airbnb", "prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error",
    "no-unused-vars": "warn",
    "no-console": "off",
    "func-names": "off"
  }
}
```

.prettierrc

```json
{
  "singleQuote": true
}
```

### 使用其他已配置的规则

- `npx install-peerdeps --dev eslint-config-wesbos`

.eslintrc

```json
{
  "extends": ["wesbos"],
  "rules": {
    "no-unused-vars": 0
  }
}
```
