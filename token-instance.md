# VoucherTokenInstance

## claim

部分提取票据已释放数量

```typescript
import { ChainId, ICTokenInstance, PoolTokenSchema, getPoolTokenSchemaBySymbol, PoolTokenType } from '@solver/ic-market-sdk'

// MetaMask provider
const provider = ethereum
const walletAccount: string = '0x9C0cF35Cf489f6893A7bCf5209819CD15500D1a1'
const tokenId: number = 1
const icTokenSymbol: string = 'icSOLV'
const amount: string = '100000000000000000000'

const icTokenSchema: PoolTokenSchema = await getPoolTokenSchemaBySymbol(ChainId.mainnet, icTokenSymbol, PoolTokenType.icToken)
const icTokenInstance: ICTokenInstance = new ICTokenInstance(
  provider,
  icTokenSchema,
  tokenId,
  walletAccount
)

icTokenInstance.claim(amount)
```

## claimAll

全部提取票据已释放数量

## safeTransferFrom

部分转让票据：为目标用户地址新生成一张票据

## mySafeTransferFrom

全部转让票据：包括票据本身同时转让给目标用户地址
