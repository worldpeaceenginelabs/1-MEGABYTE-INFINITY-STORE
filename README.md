# 1-MEGABYTE-STORE
A storage logic to distribute your whole user-database, but with only 1 Megabyte on each user's device. Works with 1, 100, 3333, and 8 Billion users. Stays always 1 MB!!!<br>
<br>
##### Scaling/Consistency is very interesting!
- You need to double the backups? Go for 2 Megabyte Store
- You need more consistency? Have 2x X-Megabyte Stores mirrored, but both stored at different locations. (GunJS sync)
- You need more resilence? Have X-times X-Megabyte Stores, mirrored or not or both, stored at X-locations.
- You need more space? Raise the size of the store! haha

##### A weird thought maybe, but what if we would limit the on-boarding (sign-up) to 500 times a month = 16times a day = every 1,5h ??? 👀
- We write our X-Megabyte's data.js into our static build (which is reactive and consums dynamically APIs) and drop it on edge! (200 CDNs worldwide, thats also a huge security feature)
- Cloudflare Pages free account provides 500 builds a month for free.
- With some logic (local first, PWA offline abilities, service-workers, Gun syncing, Gun .on subscription, and notifications even if browser and or PWA closed) the users will not even noticing it...

##### Just a thought: Containerizing X-Megabyte Stores...<br><br>

## How does it work?

- 1 ECDH Public Key = 0,0003 MB - 1 Backup<br>
- 100 ECDH Public Keys = 0,03 MB - 100 Backups<br>
- 3333 ECDH Public Keys = 0,9999 MB - 3333 Backups<br>
- 8 000 000 000 Public Keys = 2,4 Million MB - 3333 Backups<br>
<br>

##### Not enough backups? 2-MEGABYTE-STORE
8 000 000 000 Public Keys = 2,4 Million MB - 6666 Backups<br>
<br>

# Not only for user-databases
The 1 Megabyte Store works best with very small files, so everything that is able to be compressed could go too.<br>
Use-case dependant we also dont need 3333 backups for each application.<br>

But if it comes to distributing more then the user-accounts, i (as a user) want to decide myself, what i am using my storage for.<br>
A combination from multiple 1 Megabyte Stores and a logic of .get().on(data) subscriptions could get us there.<br>

Just a thought: A subscription of a graphics community will sure take more space in an X Megabyte Store, than the subscription of a travel blog for instance. And you dont want to have that knitting forum data chunks on your storage, because its not valueable to you.
