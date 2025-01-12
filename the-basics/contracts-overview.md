# Contracts Overview

The Tellor contracts are modular, but together comprise the core functionality of the Tellor oracle.

### [Oracle](https://github.com/tellor-io/tellorFlex)

The Oracle contract handles [staking](https://app.gitbook.com/s/tcQlo49FAqTaOimNOz0X/reporting-data/setup-and-usage/staking-unstaking), [reporting](https://app.gitbook.com/s/tcQlo49FAqTaOimNOz0X/reporting-data), and reading data. Accounts stake TRB to the Oracle to become data reporters. Users read data feeds from this contract.&#x20;

This contract also handles slashing reporter stakes and removing data when called by Governance.

### [Autopay](https://github.com/tellor-io/autoPay)

The Autopay contract handles payments to reporters for submitting data to requested feeds. Users can [setup and fund](https://app.gitbook.com/s/tcQlo49FAqTaOimNOz0X/getting-data/funding-a-feed#funding-a-recurring-data-feed) a schedule for reporting rewards (tips) using this contract, or just add a [one time tip](https://app.gitbook.com/s/tcQlo49FAqTaOimNOz0X/getting-data/funding-a-feed#funding-a-one-time-request).

### [Governance](https://github.com/tellor-io/governance)

The Governance contract handles creating, voting on, and executing disputes on the Oracle contract. After a dispute is resolved this contract sends the dispute fee and slashed stake to the appropriate parties.

### [Controller](https://github.com/tellor-io/tellor360)

The Controller contract is also the token contract and handles minting Time Based Rewards to the Oracle contract on Ethereum mainnet.
