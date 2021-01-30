# We will set up a private blockchain network in our local computer

## First we will need to download two tools:
  1. MyCrypto --- go to https://download.mycrypto.com/
  2. Geth and tools --- go to https://geth.ethereum.org/downloads/ and choose the version for your machine
  (rename the folder to a simpler name for easy access)
  
### When all that is done we are ready to begin:

## We will create a Proof of Authority algorithm for our blockchain newtwork

### Follow these Steps:
   1. Open your terminal and create accounts for the two nodes neccesary. We will use datadir and geth for these.
      
          code: $   ./geth account new --datadir hwmnode1 
      
          * this will create a new account for node1 and it is named in this case hmwnode1. It will also ask you for a password just click enter
      
          * it will also show a set of private and public keys which NEED to be saved somewhere as you will need them later on.
      
   2.  Now we will create the account for the second node
   
           code: $   ./geth account new --datadir hwmnode2 
      
           * again type enter when it asks for a password and save both public and private keys for your second node.
      
   3. After we have both accounts we will now run puppeth and name our network
   
            $ ./puppeth  (this will show a Welcome on your terminal and ask you to name your network)
            $ houstontx  (the name used on example) and enter
            $ 2          (configure new genesis block)
            $ 1          (we chose 1 because we will start it from scratch)
            $ 2          (choose Proof of Authority) and enter again enter when ask how many seconds 
            
            
            * you will be what accounts to seal, and here is where you go back and paste the hwknode1 and hmwnode2 public keys
            * repeat same step when asked if any account should be prefunded
            
            $ click enter when asked if prefunded by 1
            $ 1998      (In the step of Name you CHAIN it can be any number doesnt matter just make sure to SAVE IT!)
            
   4. After we set up our nodes and created our Genesis block we need to initialize the nodes.
    
          hmwnode1:    $  ./geth init houstontx.json --datadir hwmnode1
        
          repeat for  node2
        
          hmwnode2:    $ ./geth init houstontx.json --datadir hwmnode2
        
   5. Lastly we need to start mining the blocks for this step we will need two have open two terminals
   
          terminal1:   $   ./geth --datadir hwmnode1 --unlock "0x6165E46ED3F2BAaD48585C8c1F59cEC0bE1847bB" --mine --rpc --allow-insecure-unlock
          (you are using the public of hwknode1 inside " " and make sure that when the output is running, look for self=enode.... and copy it all from enode to the end)
          
          terminal2:   $   ./geth --datadir hwmnode2 --unlock "0xf17Cc212Fe9a156Ba340BFd1be847A786fD7D71A" --mine --port 30304 --bootnodes "enode://fb05c1d53a85c83624973441e0302ac53fbc0b7f3b17ba5cc9e87eb5db3402bd2143037ca0c5a223355222f51a8c3cc84f413f8f3edb97e0a8f67b0a953632eb@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock
          
          (again you will use the public key of hmwnode2 inside the " " and inside the second " " you will past the selfnode that we copied from the output of terminal1)
          
   6. Both terminals should be running at the same time and now we will upload the node to MyCrypto and send a transction.
   
## Now create a Custom Network in my Crypto 

    1. Open MyCrypto that we downloaded and on the left it says Change Network 
    2. Click and scroll down to see custom newtork
  
  It will ask you for
  
    3. NodeName: houstontx (same name as at the beginnig when doing puppeth)
    4. Network: Custom
    5. NetworkName: houstontx 
    6. Currency: ETH
    7. ChainID: 1998 (this is the number that was saved when doing puppeth that was explicitly said to save)
    8. URL: there is a default copy that default but replace the https with http
    9. Save and Use Custom Node
  
## Now to send a transaction

    1. Upload the hmwnode1/keystore file that was saved under hmwnode1 as this will have the private key to log in to the wallet in MyCrypto
    2. Once logged in on send to: copy the public adress of hwmnode2 and send whatever you amount you want 
    3. If it worked you should see a Transaction Succesful message or you could check status on TX Status on the left hand side bar.
  
## Celebrate, you just created a blockchain and sent a transaction!

* Refer to the screenshots folder to see code from the terminal and images of what you should see both in terminal and MyCrypto.
  
  
  
  
            
           
            
            
      
      
     
