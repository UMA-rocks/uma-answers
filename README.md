# UMA.rocks voting committees

UMA.rocks is using Github as an offline multisig for voting committees to reach consensus on dispute answers at every voting round.

## How does it work?

Each voting committee has its own branch on this repository.

A voting committee can have from 1 to 5 members and a majority of the members need to approve each pull request before it can be merged to the main branch.

At the beginning of every voting round, a pull request from voting committee branches to the main branch is automatically created. Voting committees have until 11AM UTC to reach consensus on dispute answers and merge the pull request.

At 12PM UTC, the merged answers for each voting committee will be committed for all delegators who subscribed to that committee.

## Why should UMA.rocks have multiple voting committees?

Having multiple independent voting committees contributes to the decentralisation of the UMA oracle by making it harder to corrupt it.

There is also a financial incentive to create and run an efficient committee. For every delegator subscribing to a committee, 30% of the delegator fees paid to UMA.rocks will be redistributed to the committee and shared equally between all committee members.

## How to create a voting committee?

To create your own voting committee:

1. Fork the `main` branch of this repository on your Github

2. Edit the file `voting-committees.json` by adding your committee details to the list. You will need to choose a name for your committee and enter the Github ID and Ethereum address for all members of your committee. Ethereum addresses will be used to distribute the voting committee earnings at the beginning of each month. The `id` value should be a +1 increment of the biggest committee id already in the file. Then, create a new file in the `landing-pages` folder called `{your-voting-committee-id}.md` to present your committee members and explain why stakers should delegate to your committee. This will serve as the official landing page for your committee.

3. Create a pull request to merge your branch in the `main` branch of this repository and wait for the approval of the UMA.rocks team. We will accept it as long as it follows the syntax from step 2.

4. After your pull request is merged, all members from your voting committee will be invited to become contributors to this Github repository. All of you will need to accept this invite on Github.

5. You will receive your first pull request once a delegator subscribes to your committee.

Happy voting!

## Special cases

### What happens if my committee fails to reach consensus and merge a PR before 11AM UTC?

This is very bad because it means you won't be able to commit answers for your delegators and they will be slashed.

Fortunately, to prevent anyone from being slashed, UMA.rocks will automatically unsubscribe all your delegators and subscribe them to other committees at random.

**Therefore, a failure to reach consensus even once is fatal for your committee.** You will lose all your existing delegators and you will have to convince them to manually resubscribe to your committee again.

We are enforcing this policy in the interest of our delegators, to incentivize committees to do their work properly, and promote a fair and healthy competition between committees. In the end, the most dedicated committees will see their UMA stake grow with time while the bad committees will die naturally. This is natural selection.




