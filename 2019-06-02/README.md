# M3 2019-06-02

## Schedule

## 6pm PST Sunday June 2, 2019

### **Agenda:**
 - **Logistics:**
   - Meeting date shifted to Sundays/weekend
   - Meeting time, EU-friendly times requested (8am-1pm PST)
 - **Lightning Talks:**
   - [Mauve on local-first Cyberspace](https://gateway.mauve.moe/f453948f122e3b46b8aa2f36309c2114f2f6d5a4bcc6aa6323bbc876ffe56585#1)
   - Avaer on stores, sideloading, and content distribution innovations

------------------------------------------

### **Topic of discussion:**

- Recap of the World / Metaverse hopping event (https://github.com/M3-org/proposals/issues/4)
- M3 founding values and mandate (https://github.com/M3-org/proposals/issues/5)

------------------------------------------


[Livestream VOD](https://youtu.be/-z45Jpr9kYw)  
  
[Photo Album](https://imgur.com/a/O6i3VDZ)


------------------------------------------

Mauve presented about achieving a Local-First Cyberpsace using @dat_project and WebXR (via @exokitXR )

Link to slides / speaker notes: <https://gateway.mauve.moe/f453948f122e3b46b8aa2f36309c2114f2f6d5a4bcc6aa6323bbc876ffe56585/#p1>

![](https://i.imgur.com/L9Jwp6o.jpg)

Video of the talk: <https://www.youtube.com/watch?v=tQeBh9DKHXQ>

Highlights:

- Dat is a way to share files and folders, like torrents
- People can't see the data unless they have the link
- Originally for scientific data, made for handling large amounts of data
- Wants to make it easy to load, author, and share VR spaces from the P2P web
- Dat is replacing http server for serving html files.
- Dat doesn't need signalling servers, it's a traditional p2p protocol.


[Q](): **Are you using the beaker browser now to load sites from?**
A: Yes, using Beaker, Firefox, and Cliqz browser. 

[Q](): **Is there a speed difference between Dat hosted and regular site?**
A: Depends on site you're loading, how many peers there are, if you already loaded it before. Generally there is not much difference. After it is loaded its available offline also unless you purge it.

[Q](): **Is there anything in the web that can't be done through Dat like streaming video?**
A: Dat will load video from archive just like sharing any other file.

Beaker doesn't currently have pointerclick api because of electron bugs.

[Q](): **How does this compare to IPFS?**
A: IPFS optimizes for global deduplication of data. If you have 1 website that has a video and another with same video you should be sharing peers between the two. Dat doesn't have that sharing peers between them - have to advertise each file link. IPFS updates are still a bit slow because of the way you do it, Dat updates very quickly and can listen for changes in an archive.

IPFS is great for static content you want to deduplicate whereas Dat is good for private content and maybe faster updates.

[Q](): **How do the economics work out if we have local-first software? It destroys business model with big companies like Google and advertising.**
A: Don't think it changes things drastically as much as one might expect, it gets rid of servers but not really the tracking aspect. Nothing stopping from reaching out to centralized service like adtracking. Don't have to go with all these centralized services to get things done, this just adds a new layer / option on top of it. Its a place to experiment - perhaps could sell content in this space. Maybe people can sell decryption keys on this p2p network.


[Q](https://youtu.be/tQeBh9DKHXQ?t=920): **How would your stuff stay online if you're not there?**
A: There's a way or service have a peer stay online such as a storage providers in the Dat ecosystem. Someone can run a server, like [Hashbase](https://hashbase.io). There's a command line app like Dat-store to set things up like this (uses npm and runs in background) then send urls to keep track.

[Q](https://youtu.be/tQeBh9DKHXQ?t=1048): **What are most common ways to find Dat content?**
A: Best way is for someone to link them to you and there's also beaker browser explorer website. One search indexes add support for Dat protocol can add support for indexing.

[Mesh](https://youtu.be/tQeBh9DKHXQ?t=1137): Since it seems world is moving towards more mobile headsets for VR/AR, I think centralizing data locally around headset will be more of a thing. Can see future with dat nodes on head with mesh network all around us.
Mauve: Did mesh networks with raspberry pis earlier in the spring, collaboration with Atmos headset also which has support.

Geocached XR is an awesome idea, so much possibility when we localize data.

Chris Novello asks about Hubs infrastructure and how it fits in the context of Dat: <https://youtu.be/tQeBh9DKHXQ?t=1368>

With Dat you no longer need a server, if you wanted to create your own version of Hubs just need to clone the Hubs Dat archive, mess with code, and can share link then.

[Q](https://youtu.be/tQeBh9DKHXQ?t=1642): **What are some of the UI/UX or design challenges for people to manage their own data?**

[Dat changes the way you make applications](https://youtu.be/tQeBh9DKHXQ?t=2213)

Link to the roadmap: <https://github.com/RangerMauve/local-first-cyberspace>


------------------------------------------

### Avaer on stores, sideloading, and content distribution incentives

![](https://i.imgur.com/UOXj4ch.jpg)

Video of the talk: <https://www.youtube.com/watch?v=MrcNyyNsMkY>

Players in the space and their incentives:

Oculus: Interface to people, wants high quality, lock the content and features that are not, content speaks for the device
Enterprise: Microsoft (army contracts), sells vision and numbers
Valve, Qualcomm: Isn't in the biz of VR, selling Steam or chips
Developers: want to innovate, ship, and monetize, upset when Oculus rejected them
Users: want content, yesterday, cheap, not well informed but that's not on them
Startups: want to capture all of the above and not be under anyone's thumb

Have to be preapproved to make something for the Oculus store, pretty much everyone Avaer has spoken with has been rejected. Most these people are also doing web stuff, not sure how that might affect it.

Facebook the interface to the people, the gatekeepers to what quality is, want to be in control. Oculus seems to want to choose side of high quality store, filter out crap so that people can expect quality from the Quest. Aims to win (Lannister)

Enterprise is profit driven: sell vision to larger organization (Hololens can improve the lethality of X percent with our product) and get sales.

Valves and Qualcomms fell into the space, see where things are headed, important to their business. Mage that advises Lannisters / Kings. Necromancer who doesn't really care much about the GOT but being in the VR space helps them sell their bread n' butter: Steam games and chips.

Developers: Feeling sidelined by it all. Stark children: idealistic about how the world should be, treated terribly by the other people playing GOT. Somewhat helpless feeling, can't really get a break - trying to push our vision forward but world working against us. When you have goals everyone is a goalie.

Users: Purchasing headsets, content. They are like the peasants of GOT, no one fundamentally cares about the consumers - fights between the corporations over user acquisition. They are somewhat non-informed, hard to keep track of everything.

Startups: The Expanse, Supermedium, JanusVR, Exokit, etc. Trying to feel out where things are headed, want to capture the action but can't always see the direction to aim for. Figuring out GOT in the backalleys. Best characterized by 'Little Finger'. Contacting people through backchannels, figuring out shortcuts and making plans in the night.

People are going to realize when headsets are commoditized that it's all about the content, users, and access. 
Q: **How long do you think it will take?**
A: If you believe Zuck, it will take 10 years a few years ago - when it's really going to be important.

Getting a userbase is the most important battle right now. Oculus strategy of making high quality content and comfortable headsets to provide good experiences and grow userbase.

With 3D you really don't want to build app twice, open standards are going to be important for faster iteration cycles in content creation pipeline. Serious model, engine, and IO standards are needed to make better content for these platforms.

[Right to repair](https://youtu.be/MrcNyyNsMkY?t=1254): hardware vendors incentivized to have full control, phones are practically leased to users.

Gov is nearly not fast enough to keep up with acceleration of technology innovation. If things are locked down, privacy is violated, people are incentivized to seek alternatives.

Steam vs Epic: Epic is offering less of a cut to buy their way into Steam's business model. People vote with their money (includes developers and users).

One of the reasons why this group is interested in crypto, local-first, p2p economy: Fundamentally we need to solve problem of value exchange, people getting paid and commerce. If we can make this secure and cut out the middleman things will be very different. 

[Q](https://youtu.be/MrcNyyNsMkY?t=1774): **What do you think is holding quality WebVR content creation the most?**
A: Monetization and tooling. There's no real way to monetize webvr content right now besides shipping to stores which none allow webvr content. There's also in-world ads. Supermedium is currently the yahoo of webvr but not much monetization.

The 90s web wasn't made of money, was pretty cool still. At the beginning was pretty idealistic, people wanted to share content but then businesses caught wind of it and started to build on it.

WebVR hasn't closed the loop yet to constantly improve things via monetization of the things they make. Other engines like Unity have closed the loop. Right now users are not really paying for WebVR content ([AxonPark](https://www.axonpark.com/) is starting to become an exception).


------------------------------------------

### M3 World Traversal Event Recap

Write-up: <https://github.com/M3-org/world-traversal>

![](https://i.imgur.com/h8NwNPD.jpg)

Video: <https://www.youtube.com/watch?v=nlk5Du2obXk>

------------------------------------------

![](https://i.imgur.com/cnlho62.jpg)

![](https://i.imgur.com/3Q4hZZD.jpg)
