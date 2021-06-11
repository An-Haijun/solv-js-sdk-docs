# SDK Quick start

Uniswap SDK 的存在是为了帮助开发人员在 Solv 之上进行构建。它旨在在任何可以执行 JavaScript 的环境中运行（比如网站、节点脚本等）。

## 安装

使用 SDK 的最简单方法是通过 npm。要将其安装到您的项目中，只需运行：

* 使用 yarn： 

```bash
yarn add git+ssh://git@github.com:solv-finance-dev/solv-ic-js-sdk.git ethers bignumber.js -S
```

* 使用 npm： 

```bash
npm install git+ssh://git@github.com:solv-finance-dev/solv-ic-js-sdk.git ethers bignumber.js -S
```

> SDK 依赖项目本身 ethers.js@^9.0.1 | bignumber.js@^5.1.0

## 用法

要在您的应用程序中运行来自 SDK 的代码，请使用 import 语句，具体取决于您的环境支持。请注意，本页后面的指南将使用 ES6 语法。

```typescript
import { ICToken } from '@solver/ic-market-sdk'
```

