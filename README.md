# 1-MEGABYTE-STORE
A storage logic to distribute your whole user-database, but with only 1 Megabyte on each user's device. Works with 1, 100, 3333, and 8 Billion users. Stays always 1 MB!!!<br>
<br>

## How does it work?

- 1 ECDH Public Key = 0,0003 MB - 1 Backup<br>
- 100 ECDH Public Keys = 0,03 MB - 100 Backups<br>
- 3333 ECDH Public Keys = 0,9999 MB - 3333 Backups<br>
- 8 000 000 000 Public Keys = 2,4 Million MB - 3333 Backups<br>

##### Not enough backups? 2-MEGABYTE-STORE
8 000 000 000 Public Keys = 2,4 Million MB - 6666 Backups


# Not only for user-databases
The 1 Megabyte Store works best with very small files, so everything that is able to be compressed could go too.<br>

But if it comes to distributing more then the user-accounts, i (as a user) want to decide myself, what i am using my storage for.<br>
A combination from multiple 1 Megabyte Stores and a logic of .get().on(data) subscriptions could work here.<br>

Just a thought: A subscription of a graphics community will sure take more space in an X Megabyte Store, than the subscription of a travel blog for instance. And you dont want to have that knitting forum data on your storage, because its not valueable to you.
