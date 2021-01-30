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
      
      * this will create a new account for node1 and it is named in this case hmwnode1. It will also ask you for a password just click enter,
      * it will also show a set of private and public keys which NEED to be saved somewhere as you will need them later on.
      
   2.  Now we will create the account for the second node
   
      code: $   ./geth account new --datadir hwmnode2 
      
      * again type enter when it asks for a password and save both public and private keys for your second node.
      
   3. After we have both accounts we will now run puppeth and name our network
   
      code: $ ./puppeth  (this will show a Welcome on your terminal and ask you to name your network)
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
            
           
            
            
      
      
     
