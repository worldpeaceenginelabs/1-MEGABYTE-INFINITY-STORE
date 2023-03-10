# 1-MEGABYTE-INFINITY-STORE (WORK IN PROGRESS, coming soon...)
A storage logic to distribute your whole user-database, but with only 1 Megabyte on each user's device. Works with 1, 100, 3333, and 8 Billion users but stays always 1 MB!!!<br>
<br>

## How does it work?

- 1 ECDH Public Key = 0,0003 MB - 1 Backup<br>
- 100 ECDH Public Keys = 0,03 MB - 100 Backups<br>
- 3333 ECDH Public Keys = 0,9999 MB - 3333 Backups<br>
- 8 000 000 000 Public Keys = 2,4 Million MB - 3333 Backups<br>
<br>

##### Not enough backups? 2-MEGABYTE-STORE
8 000 000 000 Public Keys = 2,4 Million MB - 6666 Backups<br>
<br>

# What does it do for now?

#### Working on the 1MB swap logic (in progress)

![image](https://user-images.githubusercontent.com/67427045/216082308-7d9635a9-26a5-47ad-93d1-d2f4fb25061d.png)
![image](https://user-images.githubusercontent.com/67427045/216082511-448dc5b8-0aee-41d9-8207-fb165de5e2c8.png)<br>
<br>

##### Scaling/Consistency is very interesting!
- You need to double the backups? Go for 2 Megabyte Store
- You need more consistency? Have 2 times X-Megabyte Stores mirrored, but both stored at different locations. (GunJS sync)
- You need more resilence? Have X-times X-Megabyte Stores, mirrored or not or both, stored at X-locations.
- You need more space? Raise the size of the store! haha
<br><br>

##### A weird thought maybe, but what if we would limit the on-boarding (sign-up) to 500 times a month = 16times a day = every 1,5h ??? 👀
- We write our X-Megabyte's data.js into our static JAMstack build (which is reactive and consums dynamically APIs) and drop it on edge! (200 CDNs worldwide, thats a speed and also a huge security improvement) The transition to the new build is seamless thanks to Cloudflare.
- Cloudflare Pages free account already provides 500 builds a month for free.
- With some logic the users will not even noticing it...
<br><br>

##### Following the Cloudflare thought
For 25$ a month you get already 5 concurrent builds and 5000 builds per month.<br><br>
You could automatically drop data regularly on the other 4 CI/CD pipelines, not even touching your main build.<br>
(5000/720 = 6,9 builds per hour)(20000/720 = 27,7 builds per hour(or one per 30min))<br><br>
Consuming the data from your "static" page(JAMstack) on edge, via API. (static-API-static)<br>
<br>
Pages uploads each file on your site to Cloudflare’s globally distributed network to deliver a low latency experience to every user that visits your site. Cloudflare Pages sites can contain up to 20,000 files.
<br><br>
The maximum file size for a single Cloudflare Pages site asset is 25 MiB.
<br><br>

![image](https://user-images.githubusercontent.com/67427045/215322640-9f94c832-4b3f-414a-9752-fe2af4f3dd58.png)
<br><br>

##### Just another thought: Containerizing X-Megabyte Stores...<br><br>

##### 
# Not only for user-databases
I just realised that it could work with every kind of data.<br>
<br>
The Store works best with very small files, so everything that is able to be compressed could go too.<br>
<br>
Use-case dependant we also dont need 3333 backups for each application, feature or community.<br>
And you dont want to have that knitting forum data chunks on your storage, because its not valueable to you.<br>
<br>
##### If it comes to distributing anything else then the webapps basic assets, i (as a user) want to decide myself, what i am using my storage for.<br><br>
A combination from multiple 1 Megabyte Stores and a logic of .get().on(data) subscriptions, and maybe file-splitting could get us there.<br>

Notice: A subscription of a graphics community would then sure take more space in an X Megabyte Store, than the subscription of a travel blog for instance. 
