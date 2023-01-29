# 1-MEGABYTE-STORE
A storage logic to distribute your whole user-database, but with only 1 Megabyte on each user's device. Works with 1, 100, 3333, and 8 Billion users. Stays always 1 MB!!!<br>
<br>
##### Scaling/Consistency is very interesting!
- You need to double the backups? Go for 2 Megabyte Store
- You need more consistency? Have 2x X-Megabyte Stores mirrored, but both stored at different locations. (GunJS sync)
- You need more resilence? Have X-times X-Megabyte Stores, mirrored or not or both, stored at X-locations.
- You need more space? Raise the size of the store! haha

##### A weird thought maybe, but what if we would limit the on-boarding (sign-up) to 500 times a month = 16times a day = every 1,5h ??? 👀
- We write our X-Megabyte's data.js into our static build (which is reactive and consums dynamically APIs) and drop it on edge! (200 CDNs worldwide, thats also a huge security feature) The transition to the new build is seamless thanks to Cloudflare.
- Cloudflare Pages free account already provides 500 builds a month for free.
- With some logic the users will not even noticing it...

##### Following the Cloudflare thought
For 25$ a month you get already 5 concurrent builds and 5000 builds per month.<br>
You could automatically drop data regularly on the other 4 CI/CD pipelines, not even touching your main build.(update every 8,5min)<br>
Consuming the data from your "static" page(JAMstack) on edge, via API. (static-API-static)<br>
<br>

![image](https://user-images.githubusercontent.com/67427045/215322640-9f94c832-4b3f-414a-9752-fe2af4f3dd58.png)
<br><br>

##### Just another thought: Containerizing X-Megabyte Stores...<br><br>

## How does it work?

- 1 ECDH Public Key = 0,0003 MB - 1 Backup<br>
- 100 ECDH Public Keys = 0,03 MB - 100 Backups<br>
- 3333 ECDH Public Keys = 0,9999 MB - 3333 Backups<br>
- 8 000 000 000 Public Keys = 2,4 Million MB - 3333 Backups<br>
<br>

##### Not enough backups? 2-MEGABYTE-STORE
8 000 000 000 Public Keys = 2,4 Million MB - 6666 Backups<br>
<br>
##### I think 1 Megabyte Store will need a logic for file-splitting and reconstruction in general.(Work In Progress)<br>
<br>

##### 
# Not only for user-databases
The 1 Megabyte Store works best with very small files, so everything that is able to be compressed could go too.<br>
Use-case dependant we also dont need 3333 backups for each application.<br>

But if it comes to distributing more then the user-accounts, i (as a user) want to decide myself, what i am using my storage for.<br>
A combination from multiple 1 Megabyte Stores and a logic of .get().on(data) subscriptions could get us there.<br>

Another thought - use-case: file splitting - A subscription of a graphics community would then sure take more space in an X Megabyte Store, than the subscription of a travel blog for instance. And you dont want to have that knitting forum data chunks on your storage, because its not valueable to you.
