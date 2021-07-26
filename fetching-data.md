# Fetching Data

## useToken

```typescript
import { ChainId, ICTokenInstance, PoolTokenSchema, getPoolTokenSchemaBySymbol, PoolTokenType } from '@solver/ic-market-sdk'

// MetaMask provider
const provider = ethereum
const walletAccount: string = '0x9C0cF35Cf489f6893A7bCf5209819CD15500D1a1'
const tokenId: number = 1
const icTokenSymbol: string = 'icSOLV'

const icTokenSchema: PoolTokenSchema = await getPoolTokenSchemaBySymbol(ChainId.mainnet, icTokenSymbol, PoolTokenType.icToken)

const icTokenInstance: ICTokenInstance = new ICTokenInstance(
  provider,
  icTokenSchema,
  tokenId,
  walletAccount
)

icTokenInstance.useToken()
```

获取票据信息

## sales

获取票据上架信息
