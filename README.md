# homework-blockchain

This is a homework exploring basic blockchain components and features, using Python, Pandas and Streamlit.

## The Chain

The chain of blocks records a ledger of history consisted with 3 information:
* Sender Name
* Receiver Name
* Amount

As a basic block chain, each block of the ledger history also includes features:
* Creator ID
* Previous Hash
* Nonce
* Timestamp

We use SHA256 to calculate the hash of all information. 

## The Tests

As one of the aspects to explore, levaraging streamlit, the targeting hash is alllowed to have leading zeros from 1 to 6, according to which the Nonce is mined, called "proof of work".

Only with the proper nonce meeting the target leading zero, a new block can be added to the chain.

When the difficulty of mining the nonce is high, we can pause the mining instead of running and waiting forever.

One other test is to check if the chain is a valid one, i.e., each block having its previous hash stored authenticated. If any block in the chain is changed, this validation will fail.

We also provide a function to try and change some information then validate the chain. Interestingly, we found that the last block can be changed without issue, but previous blocks cannot.

## Demo

### Build the chain

From a preset "genesis" block, we can input the information to build a new block, then add it to the chain.
![Add a block](Images/add_block.png)

### See the chain

Whenever a new block is added, the "chain view" extends to show it.
![The chain](Images/the_chain.png)

### Validate chain

Click the Validate Chain button, if the chain is validated, the ledger is displayed for easy read.
![The valid ledger](Images/valid_chain.png)

### Pause during long-run mining

High difficulty

![6 zeros](Images/high_difficulty.png)

Toggle to pause mining

![pause](Images/pause_mining.png)

### Valid change

We can change the last block
![last block change](Images/change_last_block.png)

It's valid!
![valid](Images/valid_change.png)

### Invalid change

Change the first block (it does not have ledger info!)
![1st block change](Images/change_1st_block.png)

It's invalid!
![invalid](Imagess/invalid_change.png)

### Inspect the block

Although the change makes the chain invalid, we still can inspect the block.
![inspect](Images/inspect_block.png)

### Last but not least

* If we change back the info, the chain becomes valid again.
* We have a Rerun button which if you click the chain starts from afresh