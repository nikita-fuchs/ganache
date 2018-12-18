Ganache turns 2 in the first public beta of this major release! What better way to celebrate than with a cake? The batter is ready; please help us finish the baking process by using the beta in your development workflow. This version is feature-complete, but as with any beta release be on the lookout for cake invaders. 🐛

**Get ready for more dapp insight!** You can now save your development blockchains in workspaces. These workspaces contain the configuration of your development chian, along with any Truffle projects you've provided to decode contract and event data.

## Workspaces: One Ganache, Multiple Blockchains

In Ganache 2.0 a development blockchain is one part of a larger *workspace*. Workspaces allow you to save the settings and state of your development blockchain to revisit later.

The other part(s) of a workspace are your desired Truffle projects. By pointing Ganache to a `truffle-config.js` file (see more in creating a workspace), we can use that project's contract artifact files to decode transaction, storage, and event data.

### New Home Screen

When you open Ganache 2.0, you'll see a new home screen. On this screen you're prompted to load an existing workspace (_if_ any exist), create a new custom workspace, or quickstart a one-click blockchain with default options. We'll go over each of these options below.

![Empty Home Screen](https://truffleframework.com/img/docs/ganache/v2-shared/home-empty.png)

### The Quickstart Workspace
The `QUICKSTART` button on the home screen opens the `Quickstart` workspace. This workspace is similar to how Ganache 1.x worked: you get a brand new blockchain with a genesis block every time you open it. The `Quickstart` workspace is meant to provide a clean slate for prototype development.

![Quickstart Button](https://truffleframework.com/img/docs/ganache/v2-shared/home-quickstart.png)

### Workspace Default Configuration

Every workspace has it's own configuration. Each workspace's configuration is based off the Quickstart configuration at the time of workspace creation. While these can be changed, the `Quickstart` workspace starts with the below options:

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

However, during workspace creation, the `Autogenerate HD Mnemonic` is set to `true` to maintain the same set of accounts.

### Creating Workspaces

There are two methods to create a workspace described below.

#### Saving the Current Quickstart Blockchain as a New Workspace

As mentioned above, the `Quickstart` workspace resets the blockchain every time you restart it. We found ourselves prototyping in the `Quickstart` workspace to try out a couple of things, but then we wanted to save the blockchain and elevate it into a new workspace.

To accomplish this, click the `SAVE` button near the upper right of the screen when in the `Quickstart` workspace. You will be taken to the [options screen to configure your workspace](#workspace-configuration).

![Saving a Workspace](https://truffleframework.com/img/docs/ganache/v2-shared/save-workspace.png)

#### Creating a Workspace From Scratch

You can also create a workspace from the home screen. Clicking the `NEW WORKSPACE` button on the home screen will be taken to the [options screen to configure your workspace](#workspace-configuration).

![New Workspace Button](https://truffleframework.com/img/docs/ganache/v2-shared/home-new-workspace.png)

#### Workspace Configuration

A workspace name will be randomly generated for you, but you can go ahead and change it. You can also change any of the other configuration options. When you're ready to start the new workspace, click `SAVE WORKSPACE` in the top right corner.

![New Workspace](https://truffleframework.com/img/docs/ganache/v2-shared/new-workspace.png)

You will be taken to the accounts screen. Notice the name of your new workspace near the upper right.

![Workspace Name](https://truffleframework.com/img/docs/ganache/v2-shared/workspace-name.png)

### Loading Existing Workspaces

After at least one workspace has been created, the home screen will now have a list of workspaces for you to choose from. You can scroll through the list to find the desired workspace, and clicking on it will load it.

![Filled Home Screen](https://truffleframework.com/img/docs/ganache/v2-shared/home-filled.png)

You will be taken to the accounts page. You'll notice that the blockchain state picked up from where you left off (i.e. mnemonic, accounts, associated balances, block height, transactions, etc.).

### Switching Workspaces

To switch workspaces, click the `SWTICH` button near the upper right of the screen. You'll be taken to the home screen where you can select a different existing workspace or create a new one.

![Switching Workspaces](https://truffleframework.com/img/docs/ganache/v2-shared/switch-workspaces.png)

### Deleting Workspaces

To delete a workspace, from the home screen, hover over the workspace name and click the trash can icon on the right hand side. From there you'll see a prompt ask you to confirm the deletion. Click `REMOVE` to delete the workspace. This action is irreversible! While your linked Truffle projects will remain safe and unchanged, the blockchain data (i.e. blocks, transactions, events, etc.) will be deleted.

![Delete Workspace](https://truffleframework.com/img/docs/ganache/v2-shared/home-delete.png)

## Truffle Projects: Contract & Event Decoding

Ganache 2.0 goes beyond blocks and transactions, providing you with fully decoded contract and event data. To get these benefits we must add **Truffle projects** to our workspace.

### Link a Truffle Project

To link a project, enter the settings by clicking the gear icon in the upper right.

![Settings Icon](https://truffleframework.com/img/docs/ganache/v2-shared/settings-icon.png)

You should be seeing the `WORKSPACE` settings pane; if not, you can get there by clicking `WORKSPACE` tab in the top left.

![Workspaces Settings Pane Tab](https://truffleframework.com/img/docs/ganache/v2-shared/workspaces-pane-tab.png)

From here, there is a section labeled `TRUFFLE PROJECTS`. Beneath this box, click the button `ADD PROJECT`. A file selection popup will appear. Navigate to the folder of your Truffle project, and select the `truffle-config.js` or `truffle.js` configuration file. The file you pick **must** be either named `truffle-config.js` or `truffle.js` for Ganache to correctly load it.

After selecting your file, you'll see it listed in `TRUFFLE PROJECTS` section.

![Project Listed](https://truffleframework.com/img/docs/ganache/v2-shared/project-listed.png)

You can add multiple projects to a workspace. After you're finished with adding projects you can click the `SAVE AND RESTART` (`SAVE WORKSPACE` if this is a new workspace) button in the top right.

### Unlinking a Truffle Project

If you no longer want a Truffle project linked to a workspace, go to the `WORKSPACE` settings pane the same way you did when [linking the projct](#link-a-truffle-project).

To remove/unlink a Truffle project from the workspace, click on the project file in the `TRUFFLE PROJECTS` list and then click the `REMOVE PROJECT` button.

![Project Selected](https://truffleframework.com/img/docs/ganache/v2-shared/project-selected.png)

When you're done, click the `SAVE AND RESTART` (`SAVE WORKSPACE` if this is a new workspace) button in the top right.

### Contracts Page

The new contracts page contains a list of your smart contracts by project. At a glance we can see the contract's name, address, transaction count, and deployment status.

![Contracts Page](https://truffleframework.com/img/docs/ganache/v2-shared/contracts.png)

Clicking one of the contracts will show more details about that contract including its creation transaction, storage (state), transactions, and events.

![Contract Details](https://truffleframework.com/img/docs/ganache/v2-shared/contract-details.png)

### Events Page

The new events page shows the events that have fired during this chain's life. We'll try to decode the events if possible. A decoded event will show its name, the emitting contract, hash of the transaction it appears in, log index, and block time. Encoded events will not display decoded names (they appear instead with the generic name `Encoded Event`) or contract names.

**Why aren't my events being decoded?** Check and make sure you've added the corresponding Truffle project with the contract that defines that event.

![Events Page](https://truffleframework.com/img/docs/ganache/v2-shared/events.png)

Clicking a decoded contract will reveal more information about the event including its return values and signature.

![Event Details](https://truffleframework.com/img/docs/ganache/v2-shared/event-details.png)

### Decoded Transactions

Ganache will now attempt to decode transactions that are contract calls. In addition to listing the events (encoded or not) for the transaction, Ganache will show the function signature of the transaction as well as the values of the arguments.

![Decoded Transaction](https://truffleframework.com/img/docs/ganache/v2-shared/decoded-transaction.png)

**Why aren't my transactions being decoded?** Check and make sure you've added the corresponding Truffle project with the contract that the transaction is being interacted with.

**Why the major version bump?** There is some debate over the use of semver for GUI applications. After our own deliberations, we've decided to bump Ganache's major version to 2.0 because the _workflow_ has a breaking change.