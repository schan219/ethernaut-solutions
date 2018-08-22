1. `web3.eth.getStorageAt(contract.address, 1, (err, res) => { if (err) { password = err; } else { password = res } } )`
2. `await contract.unlock(password)`

Check if vault is opened: `await contract.locked()`.