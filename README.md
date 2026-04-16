# UMA.rocks voting committees

<p align="center">
UMA.rocks enables anyone to delegate their Polymarket voting power to experienced voters searching for truth.
  </p>

  <p align="center">💸 Delegators get paid 23% APR · 💸 Voters get paid 30% of the UMA.rocks fee</p>
  
  <p align="center">🤖 Automated · 🔑 Non-custodial · 🚪 Permissionless exit</p>

  <p align="center">
<img width="704" height="384" alt="image" src="https://github.com/user-attachments/assets/b44c6405-5e11-4e21-9ee8-9afe54f35b9c" /></p>


## How does it work?

On creation, each voting committee chooses between 1 and 11 members and defines the minimum number of signers required to approve dispute answers.

Then, at the beginning of each voting round, a pull request is automatically created in each voting committee branch `voting-committee-{voting-committee-id}`. It contains all the dispute details for the current round. Committees only need to replace all occurences of `"answer": "P0"` with their desired answer.

Committees have until 11AM UTC to choose their answers, get the minimum required number of approvals, and merge the pull request in the `main` branch.

One hour later (at 12PM UTC), the merged answers for each voting committee will be committed for all delegators who subscribed to that committee.

## Why should UMA.rocks have multiple voting committees?

Having multiple independent voting committees contributes to the decentralisation of the UMA oracle by making it harder to corrupt.

There is also a financial incentive to create and run an efficient committee. For every delegator subscribing to a committee, 30% of the delegator fees paid to UMA.rocks will be redistributed to the committee and shared equally between all committee members at the beginning of every month.

## How to create a voting committee?

This is very simple.
To create your own voting committee:

1. Fork the `main` branch of this repository on your Github.

2. The `committees` folder contains all the committee IDs, and each committee ID folder contain the details for that committee. In the `committees` folder, copy & paste the folder `0` at the same location, and rename the copy with a number which should be the number increment of the maximum existing committee ID. This number will be your committee ID. In this folder, the files `metadata.json` and `presentation.md` are already prefilled for you. `metadata.json` needs to contain all your committee details while `presentation.md` will be the landing page for your committee that you can use to present your members and explain why people should delegate to your committee. You can customize `presentation.md` as much as you want, be creative!

3. Create a pull request to merge your branch in the `main` branch of this repository and wait for the approval of the UMA.rocks team. We will accept it as long as it follows the syntax from step 2.

4. After your pull request is merged, all members from your voting committee will be invited to the Github Team `Voting committee {your-committee-id}`. The invitation will be sent by Github to the email linked to your Github account. All of you need to accept this invite.

5. You will receive your first pull request once a delegator subscribes to your committee in the UMA.rocks webapp.

Happy voting!

## Frequently asked questions

### Who is eligible to be a committee member, are there any requirements?

Everyone can be part of a committee, there are no requirements at all.

### Can one person be part of several voting committees?

Yes, you can join as many voting committees as you want.

### Can I make changes to my voting committee once it is created?

Yes, you can change both `metadata.json` and `presentation.md` for your committee via a pull request from your voting committee branch to `main`, as long as your pull request gets the required number of approvals defined in the `multisig` property of your `metadata.json`.

### When a new delegator joins UMA.rocks, which committee is assigned to him/her by default?

We automatically assign to new delegators the voting committee with the biggest total stake, which is usually the best performing committee.

### What happens if my committee fails to reach consensus and doesn't merge the PR before 11AM UTC?

This is very bad because it means you won't be able to commit answers for your delegators and they will be slashed.

Fortunately, to prevent anyone from being slashed, UMA.rocks will automatically unsubscribe all your delegators and subscribe them to other committees at random.

Therefore, a failure to reach consensus even once is fatal for your committee. You will lose all your existing delegators and you will have to convince them to manually resubscribe to your committee again.

We are enforcing this policy in the interest of our delegators, to incentivize committees to do their work properly, and promote a fair and healthy competition between committees. In the end, the most dedicated committees will see their UMA stake grow with time while the bad committees will die naturally. This is natural selection.

### Brrr this is permissionned, is this just decentralization theater or real decentralization?

While it is true that this Github repo is owned by UMA.rocks, there are a few things to keep in mind:
- Making this whole voting committee logic permissionless with smart contracts would require an immense amount of work, time, audits, and money that we don't have. Therefore, this permissionned system is actually the best we can do for now.
- We promise to accept anyone who is willing to join or create a committee.
- We can't censor specific people from creating or joining committees because committee members are only required to give a Github username and an Ethereum address which can be both easily anonymized. People are free to join with a fake username and we won't be able to link it to their real identity.
