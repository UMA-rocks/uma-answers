# UMA.rocks voting committees

UMA.rocks is using Github as an offline multisig for voting committees to reach consensus on dispute answers for every voting round.

## How does it work?

Each voting committee has its own branch on this repository.

A voting committee can have from 1 to 5 members and a majority of the members need to approve each pull request before it can be merged to the main branch.

At the beginning of every voting round, a pull request from voting committee branches to the main branch is automatically created. Voting committees have until 11AM UTC to reach consensus on dispute answers and merge the pull request.

At 12PM UTC, the merged answers for each voting committee will be committed for each delegator who subscribe to that committee.

## Why should UMA.rocks have multiple voting committees?

Having multiple independent voting committees contribute to the decentralisation of the UMA oracle by making it harder to corrupt it.

There is also a financial incentive to create and run an efficient committee. For every delegator subscribing to a committee, 25% of the delegator fees paid to UMA.rocks will be redistributed to its committee and shared equally between all committee members. It is the equivalent of "builder codes" that both Polymarket and Hyperliquid are using to pay anyone who is bringing them traffic.

## How to create a voting committee?

To create your own voting committee:

1. Fork the `main` branch of this repository on your Github

2. Edit the file `voting-committees.json` by adding your committee details to the list. You will need to choose a name for your committee and know the Github ID and Ethereum address for all members of your committee. Ethereum addresses will only be used to distribute the voting committee earnings at the beginning of each month. The `id` value should be a +1 increment of the previous committee id.

3. Create a pull request and wait for approval from the UMA.rocks team.

4. After your pull request is merged, all members from your voting committee will be invited to become contributor to this Github repository. You will need to accept this invite on Github.

5. In the newly created branch `voting-committee-<your-voting-committee-ID>`, you can edit the file `README.md` to present your committee members and explain why stakers should delegate to your committee.







