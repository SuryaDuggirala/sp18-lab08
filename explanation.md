### What's going on in `Mystery.sol`?

##### Answer:
Mystery.sol is basically running through a transaction. We have the variable g which has a mask running over it to get the top 32 bits to get an unsigned int. 'g' represents the gas amount we have to work with for our transaction. The next variable is o_code which is the opcode. We pull the opcode from the memory address 0x40. This is stored in memory and not in storage. Then we take our address from our global storage and run and AND it with a bitmask to get the top 40 bytes in unsigned form. Next, we copy our calldata to our memory using calldatacopy. We assign retval to be equal to whatever our return value is for our function call. In order to do this, we pass in the gas value, the address, and the opcode to come up with the kind of operation we're going to perform. Finally we do a check. If the retval is nonzero, we do nothing and get to the return value. On the other hand, if the retval is invalid and our function 'isnonzero' returns 0 for our retval, then we jump to an invalid address 0x02 which causes the function to error out. 

Surya Duggirala: 26132062 \n
Morgan Jordan: 3032116153
