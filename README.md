<h1>DTEAM Shielded Application</h1>

Our team has done some research and we have found that it is currently very difficult to build a properly working "shielded-based" application.

As we can see, at the moment shielded wallet tokens are not displayed in the https://namada.me/ application (so it is impossible to make a transaction from the shielded wallet), this is due to the way the extension and the interface receive the shielded wallet balance. 

To solve this problem we decided to run the network locally and find out what could be the reason for such a strange behaviour of the interface, when tokens are displayed on a regular wallet, but not on a shielded wallet.

<b>While investigating the problem we found out the reasons why tokens are not displayed:</b>
- shielded balance takes longer to load than transparent balance;
- the longer the network works, the longer it takes to load the shielded balance;
- the browser extension has a "timeout" for receiving the balance, so due to the previous factors, the shielded balance is not loaded at all.

To achieve the result on the local network, we changed the epochs_per_year parameter from 31536000 to 1105000, as well as changed the timeout parameter to get the number of tokens in extension. 

Thanks to the above changes we managed to achieve correct operation of the interface in the local network for some time, until the network has not gained too many blocks, because the <b>value of height in the network at the moment directly affects the time of obtaining the balance on the interface</b>. 

<h3>It follows that it is impossible to build a correctly working shielded application on the current Shielded Expedition network due to the high height.</h3>

<b>Links:</b>
- Example of how our application works on a local network - 
- Our modified interface - 
- Local network RPC - 
- Local network Chain Id - 
- Our interface fork -
