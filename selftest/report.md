# Buyback verification — FLAPJAX (BNB Smart Chain)

Generated 2026-10-20 09:30:28 UTC by buyback-verifier 1.0 (read-only chain audit; no explorer index figures used).

## Scope

- Token: `0x90c8889f428f9ebb77bb8f15cad3a50a9ac680df` (FLAPJAX, 18 decimals)
- Treasury: `0x7c34e9e21ee28a49ff0b84b61774119e6633359f`
- Pool: `0xca93ec685b8623688e6b236f9068034b298c2150` (quote asset WBNB)
- Window: 2026-10-09 00:00:00 → 2026-10-18 23:59:59 UTC (blocks 126,536,085–128,454,490)
- Discovery transport: **seeds** — SEED-BASED — every listed buy was verified from raw chain receipts, but the window was NOT independently enumerated (no logs-capable endpoint); completeness rests on the seed list supplied by the caller.

## Result

- **Buys: 9**
- **Total spent: 0.09 WBNB** (basis: quote-token transfers into the pool (receipts))
- **Total received: 214,002,792.664923451883644637 FLAPJAX**
- **Average price: 4.205553e-10 WBNB per FLAPJAX**
- **Sells by treasury into the pool: 0**
- Gas fees paid by treasury for the buys: 0.0000573319 BNB

## Buys (each verified from its transaction receipt)

| # | UTC time | Block | Tx | Spent (WBNB) | Received (FLAPJAX) | Price (WBNB/FLAPJAX) | Recipient |
|---|---|---|---|---|---|---|---|
| 1 | 2026-10-09 18:30:53 | 126,684,151 | [0xbeefabdc89f9…](https://bscscan.com/tx/0xbeefabdc89f9148f9daaef6082d34a60dc5b4b612972ca0fd39d6bd4eb03b4b0) | 0.01 | 24,052,995.30827152476827804 | 4.157486e-10 | 0x7c34e9e2… |
| 2 | 2026-10-10 18:27:56 | 126,875,701 | [0x8ce8e8578da2…](https://bscscan.com/tx/0x8ce8e8578da26f8c7acb0f44c6ca0d0b8dcba868cafe2d729bb48562863f2d62) | 0.01 | 23,979,958.557395636288483739 | 4.170149e-10 | 0x7c34e9e2… |
| 3 | 2026-10-11 18:30:35 | 127,067,713 | [0x82d01172ae26…](https://bscscan.com/tx/0x82d01172ae26f1c86287643e123af1675ca5c18b984b7740c1a0c1647d2801eb) | 0.01 | 23,907,253.965589989685035768 | 4.182831e-10 | 0x7c34e9e2… |
| 4 | 2026-10-12 18:46:27 | 127,261,246 | [0x9afdc96e3ca8…](https://bscscan.com/tx/0x9afdc96e3ca876b5b617a26ba5105012ed8c33e805c77b1616bf48c198d5cbf1) | 0.01 | 23,834,879.521763892137228328 | 4.195532e-10 | 0x7c34e9e2… |
| 5 | 2026-10-13 18:41:15 | 127,452,454 | [0xc94de373d1fb…](https://bscscan.com/tx/0xc94de373d1fb00093431224a97475b3b2b48b9a4962d15acbe9d9c5c016d720c) | 0.01 | 23,762,833.230024087278551319 | 4.208252e-10 | 0x7c34e9e2… |
| 6 | 2026-10-14 18:32:29 | 127,643,212 | [0x172349c64ed3…](https://bscscan.com/tx/0x172349c64ed3c45663650049f9e2ad3d763b1243c5c849b7d66f144f221d3186) | 0.01 | 23,691,113.109537150143912753 | 4.220992e-10 | 0x7c34e9e2… |
| 7 | 2026-10-17 02:00:51 | 128,086,717 | [0xc999000f16f3…](https://bscscan.com/tx/0xc999000f16f326e8868fe37f83871219be1a63f98043b0aef9ee57f469232156) | 0.01 | 23,669,235.465921230581203552 | 4.224894e-10 | 0x7c34e9e2… |
| 8 | 2026-10-17 13:29:27 | 128,178,495 | [0x6ec66780e051…](https://bscscan.com/tx/0x6ec66780e0518da7c3c8b55d13b66d57400046f89ebe9df479c3c878f7b3311f) | 0.01 | 23,597,938.349722733902073707 | 4.237658e-10 | 0x7c34e9e2… |
| 9 | 2026-10-18 13:28:39 | 128,370,339 | [0x05a9acf81b0e…](https://bscscan.com/tx/0x05a9acf81b0eae4b7ff9a12168aead25964b6b2c0a16d3d1e667b7db6f17ad99) | 0.01 | 23,506,585.156697207098877431 | 4.254127e-10 | 0x7c34e9e2… |

## Sells

**No sells found** inside any of the verified transactions (window-wide outflow enumeration unavailable — see Method & limits): the treasury sent no FLAPJAX to the pool.

## Method & limits

- Candidate transactions come from the discovery transport named above; **every figure is then re-derived from raw chain data** — `eth_getTransactionByHash`, `eth_getTransactionReceipt`, `eth_getBlockByNumber` — via public BSC RPC. Token amounts are the exact ERC-20 `Transfer` log values (wei-exact), not index data.
- A buy is a transaction in which the pool sends the token to the treasury; the amount received is the sum of the receipt's pool→treasury `Transfer` logs for the token. Quote spent is measured from quote-token transfers into the pool in the same receipt, falling back to the transaction's native value.
- Log enumeration is chunked: public BSC endpoints reject `eth_getLogs` ranges above roughly 1,000 blocks (error -32005), so the scan walks the window in adaptive chunks and records any range it could not fetch.
- **This run used seeds discovery**: the seed hashes are the caller's list (e.g. a project's published buyback receipts). Buys not on the list cannot be found by this run, and the sell check covers the verified transactions themselves; a window-wide treasury outflow scan requires a logs-capable endpoint (preflight results are in the JSON output).
- Public BSC RPCs prune historical state (`eth_call` at old blocks returns 'missing trie node'), so all verification reads receipts/logs of mined transactions, never historical state.
- Scope is the single pool given as input: buys routed through other pools/aggregators, and direct (non-swap) token transfers into the pool, are outside this report.
