# ic-token

## Mint

铸造票据：目前支持铸造以下三种释放方式的票据

Mint之前需检查是否已对合约进行授权 [underlyingAllowance](token.md#underlyingAllowance)

```typescript
import { ChainId, ICToken, PoolTokenSchema } from '@solver/ic-market-sdk'

// MetaMask provider
const provider = ethereum
const walletAccount: string = '0x9C0cF35Cf489f6893A7bCf5209819CD15500D1a1'
const icTokenSymbol: string = 'icSOLV'

const icTokenSchema: PoolTokenSchema = await getPoolTokenSchemaBySymbol(ChainId.mainnet, icTokenSymbol, PoolTokenType.icToken)
const icToken: ICToken = new ICToken(provider, icTokenSchema, walletAccount)
```

* 线性释放

```typescript
// 实际输入数量 * tokenDecimals
const amount: string = '100000000000000000000'
// 精确到秒
const maturities: Array<string> = [1622476800]
// 实际输入数值 * 100
const percentages: Array<number> = [10000]
const term: number = 30 * 86400
const res = await icToken.mint(term, amount, maturities, percentages, '', {})
```

* 单点释放（term = 0）

```typescript
const amount: string = '100000000000000000000'
const maturities: Array<string> = [1622476800]
const percentages: Array<number> = [10000]
const term: number = 0 // Must 0
const res = await icToken.mint(term, amount, maturities, percentages, '', {})
```

* 多点释放

```typescript
const amount: string = '100000000000000000000'
const maturities: Array<string> = [1622476800, 1625068800, 1627747200]
const percentages: Array<number> = [2000, 3000, 5000]
const term: number = maturities[maturities.length - 1] - maturities[0]
const res = await icToken.mint(term, amount, maturities, percentages, '', {})
```

## underlyingAllowance

icToken合约 - 返回 icToken 底层资产授权数量

## underlyingApprove

icToken合约 - 底层资产授权

## isApprovedForAll

查询票据底层资产是否已授权

## setApprovalForAll

票据底层资产授权

