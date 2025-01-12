# Submitting Values

Reporting data is the same on any network, it requires a staked reporter to run the [`submitValue` function](../../getting-data/tellor-functions.md):

```solidity
/**
 * @dev Allows a reporter to submit a value to the oracle
 * @param _queryId is ID of the specific data feed. Equals keccak256(_queryData) for non-legacy IDs
 * @param _value is the value the user submits to the oracle
 * @param _nonce is the current value count for the query id
 * @param _queryData is the data used to fulfill the data query
 */
function submitValue(
    bytes32 _queryId,
    bytes calldata _value,
    uint256 _nonce,
    bytes memory _queryData
) external {
```

#### Notes:

Once a value is submitted, the reporter is then locked from submitting again for the reporterLock time period (currently 12 hours on most networks).

For all queryId's except legacy ID's (ETH only), the \_queryId must be the keccak256 hash of the \_queryData. For information on how to get the queryId or how to parse the \_queryData, see the [Creating a Query](https://app.gitbook.com/s/tcQlo49FAqTaOimNOz0X/getting-data/creating-a-query) section.

The \_nonce also must be correct for a valid report. The nonce represents the number of submissions for a given query. The purpose of the \_nonce is to prevent two parties from submitting at the same time for the same ID.
