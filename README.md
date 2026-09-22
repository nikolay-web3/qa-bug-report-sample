# Manual QA Bug Report Sample

This repository contains a sample QA bug report demonstrating how I document and investigate issues in Web3 applications.

## Bug Report

### Title

Wallet balance is not refreshed after switching blockchain networks

### Severity

Medium

### Priority

Medium

### Environment

- Browser: Chrome
- Operating System: macOS
- Application type: Web3 dApp
- Wallet: Browser wallet
- Test type: Manual / Exploratory Testing

## Preconditions

1. User has a wallet connected to the application.
2. Wallet contains assets on more than one supported blockchain network.
3. User is logged into the application.

## Steps to Reproduce

1. Open the Web3 application.
2. Connect a wallet.
3. Confirm the displayed balance on Network A.
4. Switch the wallet to Network B.
5. Return to the application's portfolio page.
6. Observe the displayed wallet balance.

## Expected Result

After switching networks, the application should:

- detect the new blockchain network
- request updated wallet data
- refresh token balances
- display the correct network name

## Actual Result

The application continues displaying the balance from the previous network until the page is manually refreshed.

## Reproducibility

4/4 attempts.

## User Impact

The user may see outdated financial information and incorrectly assume that assets from the previous network are available on the currently selected network.

This may cause confusion when attempting to perform a transaction.

## Suggested Investigation

Check:

- wallet network-change event handling
- cached balance data
- RPC request refresh logic
- frontend state invalidation
- network ID synchronization

## Suggested Fix

Trigger a balance refresh whenever the connected wallet emits a network-change event.

Cached blockchain data should be invalidated before requesting balances for the newly selected network.

## Regression Testing

After implementing the fix, verify:

1. Network A → Network B
2. Network B → Network A
3. rapid network switching
4. switching while portfolio data is loading
5. unsupported network handling
6. disconnecting and reconnecting the wallet

## Skills Demonstrated

- manual QA
- exploratory testing
- bug reproduction
- Web3 testing
- troubleshooting
- technical documentation
- regression testing

---

This is a portfolio sample created to demonstrate QA documentation skills. It is not a report from a paid client engagement.
