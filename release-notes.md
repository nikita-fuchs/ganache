Ganache turns 2 in the first public beta of this major release! What better way to celebrate than with a cake? The batter is ready; please help us finish the baking process by using the beta in your development workflow. This version is feature-complete, but as with any beta release be on the lookout for cake invaders. 🐛

**Get ready for more dapp insight!** You can now save your development blockchains in workspaces. These workspaces contain the configuration of your development chian, along with any Truffle projects you've provided to decode contract and event data.

## Workspaces: One Ganache, Multiple Blockchains

In Ganache 2.0 a development blockchain is one part of a larger *workspace*. Workspaces allow you to save the settings and state of your development blockchain to revisit later.

The other part(s) of a workspace are your desired Truffle projects. By pointing Ganache to a `truffle-config.js` file (see more in creating a workspace), we can use that project's contract artifact files to decode transaction, storage and event data.

### Creating a Workspace

When you open Ganache 2.0 for the first time, you'll see a new home screen. On this screen you're prompted to load an existing workspace (_if_ any exist), create a new custom workspace or quickstart a one-click blockchain with default options (see below).

![Workspaces](https://truffleframework.com/img/docs/ganache/v2-shared/home-empty.PNG)

Selecting NEW WORKSPACE will take you to the options screen to configure your workspace.

![New Workspace](https://truffleframework.com/img/docs/ganache/v2-shared/new-workspace.PNG)

After you're satisfied with the configuration, click SAVE WORKSPACE to be taken to the accounts screen. Notice the name of your new workspace near the upper right.

![Workspace Name](https://truffleframework.com/img/docs/ganache/v2-shared/workspace-name.png)

### Saving & Switching Workspaces

To save a workspace, click the SAVE button near the upper right of the screen. If you have not selected a name, a name will be randomly generated for you. Accept that name or fill in your own, then click SAVE WORKSPACE.

![Saving a Workspace](https://truffleframework.com/img/docs/ganache/v2-shared/save-workspace.png)

To switch workspaces, click the SWTICH button near the upper right of the screen. You'll be taken to the home screen where you can select a different existing workspace or create a new one.

![Switching Workspaces](https://truffleframework.com/img/docs/ganache/v2-shared/switch-workspaces.png)

### Deleting Workspaces

To delete a workspace, from the home screen, hover over the workspace name and click the trash can icon on the right hand side. From there you'll see a prompt ask you to confirm the deletion. Click REMOVE to delete the workspace.

![Workspaces](https://truffleframework.com/img/docs/ganache/v2-shared/home-delete.png)

### Workspace Defaults

Quickstart workspaces have these default options:

```
Hostname: 127.0.0.1 - localhost
Port Number: 7545
Network ID: 5777
Automine: true
Error on Tx Failure: true

Account Default Balance: 100
Total Accounts to Generate: 10
Autogenerate HD Mnemonic: false
Lock Accounts: false

Output Logs to File: false
Verbose Logs: false
```

## Truffle Projects: Contract & Event Decoding

Ganache 2.0 goes beyond blocks and transactions, providing you with fully decoded contract and event data. To get these benefits we must add **truffle projects** to our workspace.

To add a project, click the gear icon in the upper right. You'll see the workspace settings pane. The second input is a list of `truffle-config.js` file paths.

Once you've added a Truffle project

### Contracts Page

The new contracts page contains a list of your smart contracts by project. At a glance we can see the contract's name, address, transaction count, and deployment status.

![Workspaces](https://truffleframework.com/img/docs/ganache/v2-shared/contracts.PNG)

Clicking one of the contracts will show more details about that contract including its creation transaction, storage (state), transactions and events.

![Workspaces](https://truffleframework.com/img/docs/ganache/v2-shared/contract-details.png)

### Events Page

The new events page shows the events that have fired during this chain's life. We'll try to decode the events if possible. A decoded event will show its name, the emitting contract, hash of the transaction it appears in, log index, and block time. Encoded events will not display decoded names (they appear instead with the generic name "Encoded Event") or contract names.

**Why aren't my events being decoded?** Check and make sure you've added the corresponding Truffle project defining that event.

![Workspaces](https://truffleframework.com/img/docs/ganache/v2-shared/events.PNG)

Clicking a decoded contract will reveal more information about the event including its return values and signature.

![Workspaces](https://truffleframework.com/img/docs/ganache/v2-shared/event-details.PNG)

**Why the major version bump?** There is some debate over the use of semver for GUI applications. After our own deliberations, we've decided to bump Ganache's major version to 2.0 because the _workflow_ has a breaking change.