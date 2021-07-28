# Fetching Data

## useToken

获取票据信息

```typescript
import { ChainId, VoucherTokenInstance, VoucherTokenSchema, getVoucherTokenSchemaBySymbol } from '@solver/solv-vouchers-sdk'

// MetaMask provider
const provider = ethereum
const walletAccount: string = '0x9C0cF35Cf489f6893A7bCf5209819CD15500D1a1'
const tokenId: number = 1
const voucherTokenSymbol: string = 'icSOLV'

const voucherTokenSchema: VoucherTokenSchema = await getVoucherTokenSchemaBySymbol(ChainId.mainnet, voucherTokenSymbol)

const VoucherTokenInstance: VoucherTokenInstance = new VoucherTokenInstance(
  provider,
  voucherTokenSchema,
  tokenId,
  walletAccount
)

VoucherTokenInstance.useToken()
```


## sales

获取票据上架信息
