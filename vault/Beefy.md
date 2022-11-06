## Beefy API

Dashboard Data:

- Live Gwei Gas Price
- Streaming price charts: ETH, LP Token
- Pool Data
- Vault Data
- User data

---

## Pool and Vault Data

```ts

useVault(poolAddress: string, vaultName: string)

{
   pool_name: string;
   pool_tvl: number;
   pool_tvl_lp_token: number;
   vault_name: string;
   vault_tvl: number;
   vault_tvl_lp_token: number;
   vault_apy: number;
   vault_apy_daily: number;
   vault_last_harvest: date;
   vault_assets: [
       {
           asset_name: string;
           units: number;
           percent_of_vault: number;
       }
   ]
}

```

## User / Wallet Data

```ts

useVaultUser(vaultName: string, address: string)

{
    moo_token_name: string;
    moo_balance: number;
    lp_token_initial_balance: number;
    lp_token_current_balance: number;
    lp_token_current_price: number;
    asset_value_dolla: number; // Current lp token balance value
    annual_return_lp_tokens: number; // current lp bal at current APY
    annual_return_percent: number;
    monthly_return_lp_tokens: number;
    monthly_return_percent: number;
    vault_share: number;
    roi_lp_tokens: number; // Total return to date against initial lp bal
    roi_percent: number;
    daily_returns: [
        {
            date: date;
            daily_return_lp_tokens: number;
            daily_return_percent: number;
            daily_return_dolla: number;
        }
    ];
}

```

## Stripped down - let the front-end devs do some work

```ts

useVaultUser(vaultName: string, address: string)

{
    moo_token_name: string;
    moo_balance: number;
    lp_token_initial_balance: number;
    lp_token_current_balance: number;
    lp_token_current_price: number;
    daily_returns: [
        {
            date: date;
            daily_return_lp_tokens: number;
            daily_return_percent: number;
            daily_return_dolla: number;
        }
    ];
}

```
