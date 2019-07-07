# M3 2019-06-16

## Schedule

#### Sunday June 16, 2019
#### **Time:** 6pm PST


[Livestream VOD](https://youtu.be/5ECkc7w7Abc)
[Photo Album](https://imgur.com/a/iebuBr5)

-------------------------------------------


### **Agenda:**
 - **Logistics:**
   - Meeting date shifted to Sundays/weekend
   - Meeting time going to 6pm PST again, EU meetings will need EU leadership to be ran
   - Schedule Shaneharris on Side Quest talk for a time before 4pm PST, tomorrow?

 - **Lightning Talks:**
   - [mqp on Mozilla Hubs](https://youtu.be/LMkdA6OCdGs)
   - [Mauve on editing XR in XR](https://youtu.be/qwOOgvEiN_M)
   - [bnolan on Cryptovoxels](https://youtu.be/3fdDqHpurbg)

 - **Topic of discussion:**
   - DAT takeaway task from previous meet
   - Membership dues / incentivizing development

-------------------------------------------

## [mqp on Mozilla Hubs](https://youtu.be/5ECkc7w7Abc)

![](https://i.imgur.com/RQN6OLJ.jpg)

One of about 9 people working on Hubs, most of whom came from Altspace. Collectively think that avatar bodied communication is an interesting form of communication because it gives interesting distinct social cues and abilities.

Trying to poke around to see what works, build up infrastrucutre, discover best practices in social vr world.

First difference that team really liked about doing it on the web vs native was how easy it is to go to URL versus having to download a thing off steam and running a client then navigating via a menu. Other thing really like is that its cool to have good drawing and screensharing support because Google Hangouts version isn't that great.

The environment one is in and what things look like gives communication a vibe. Stuff like spoke and avatar customization to give everyday users control over that is interesting also.

Want to continue seeing to use discord bot and see if other bots for slack / matrix / etc would be useful. Try to make it convenient to use Hubs to meet up in existing social communities.

Wish it was easier to script in Hubs instead of opening javascript console on browser or making a browser extension, not quite sure how to do a good job of it because of sandboxing concerns.

Really want to keep pushing the bar on performance, lots of promising roads for improvements. Devices like the Oculus Quest will be the standard for next couple years, have to run well on that. One example of performance improvements is dynamic batching which didn't previously exist in webxr.

Hubs team wants to make the product more hackable both in terms of making it easy to modify the client (fork and hook to infrastructure) and for people to host their own backend also.

Want to make the moderation tools even better, outsourcing the identity, account moderation stuff to discord has served this purpose well. Want to make a better ownership and permissions model. 

Want to be less dependent on a-frame in the future because it isn't super well optimized for high performance.

Might be better off with simpler abstraction using just 3js.

Couple people on Mozilla working on Three.js ECS.

Q: **How do you forsee this spanning out eventually into all of XR and WebXR? Into the environment?**
A: Care a lot about little details and performance bugs, contributing back to a lot of open libraries in the 3D web ecosystem.

Q: **Is it just that aframe is inherently inefficient for some reason or is there just low hanging fruit for optimization?**
A: Couple things, DOM operations usually not very efficient. If you're using DOM like scene graph the code isn't going to be super efficient. For example, we don't want to commit changes back to DOM during a frame. Lot of overheard when instatiating new objects from the DOM. [DOM event bubbling](https://javascript.info/bubbling-and-capturing) is also pretty slow compared to other ways. Aframe components using events to communicate with eachother isn't that good. Another is setattribute on aframe components is remarkably complicated. Typical aframe conventions inherently optimized for ease of use and not so much for performance.

Q: **Does it make more sense to run physics server-side for everyone?**
A: Not sure, very few of team has any game dev background.

Not the best at creating a totally open source community driven project because background is a small team working in startups just getting along with eachother well. Would really like to get better at open source stuff though!

Did not like not multiplexing the audio when there's over 12 people which could constrain people on bandwidth (sending to 15 people instead of 1 place and then it going downstream from there to 15). If okay with trade-off and paying that tax, its 100% reasonable then.

There's other concerns with Hubs like security / moderation, for p2p would have to deal with own moderation systems.

"Really wish there were Hubs forks. To me the dream is I wanna make the infrastructure stuff other people can build on and would like other people forking Hubs, doing weird stuff with it we never thought of. Don't really know what it will take to get other people to do it though."

Ideas for potentially getting others interested in forking Hubs:

- Make the backend more runnable
- Better documentation
- Evangelizing to community
- More example cool hax

Hubs isn't a social layer to aframe, started out thinking about a multi-user webvr thing and thought about what should be used to do it. First thought everyone liked aframe a lot because it was a Mozilla sponsored project, didn't know too many details. Networked-aframe also existed so that seemed like a good thing to use also. The maintainers of aframe left mozilla to work on Supermedium so Mozilla doesn't contribute development effort much. It's complicated.

At current scale the Hubs server costs are quite cheap, no business model yet as its not a big priority yet. Thinking about ideas in the backs of their minds for now.

Q: **Is there a grand vision for Mozilla Reality or how are the teams structured / resourced?**
A: There is a mixed reality org at mozilla thats a child of the emerging technology group with others like Rust, Servo, and deep speech.

Q: **Are the projects we can spawn scriptable?**
A: To some extent, right now we don't send javascript over the wire. When pasting in glTF model and someone else gets it in networked-aframe and spawn it there can be little tags in it that say names of aframe components that are in Hubs and attach those components to parts of the model. For example, the way the avatar works is that there is a glTF model and the head object of the glTF model refers to the aframe component that makes it bigger or smaller when you talk. There is a preset set of aframe components that can go on models and sometimes they do.

Q: **Do you have any components for reacting to events?**
A: Not sure if there's anything that generic, probably easy to add something like that. If you have a good reason that's generic / useful / reason why you want it could probably convince us to merge it or make it in a fork. There's a scripting channel on Hubs discord.

Q: **Are/will animations be supported?**
A: They should currently be supported. There is an animation aframe component that looks at animations specified in the glTF. Don't have a mechanism to trigger an animation when pressing a key yet. If you paste in a gltf model that has animations then animations will happen in Hubs. I think you can also specify them in Spoke.

Q: **Have you thought about the performance gap between webxr and native?**
A: Don't know how big it is exactly but it can't be that big because I worked at Altspace making the GearVR / Oculus Go and Daydream compatible versions work real smooth using Unity. Could join with a dozen people and have a great experience and thats the same with Hubs now. It's about the performance we could get out of Hubs. 

Q: **What is missing apart from UI to fill the gap?**
A: Not a game developer or expert on game engines but it doesn't seem to me there's anything super missing from webxr / webgl ecosystem that makes it super hard to get great performance for easy things. For doing fancy things its harder since there's no web vulkan and lots of features in webgl that don't exist to make AAA VR experiences. Doesn't seem like a big deal. There is a tooling gap also, there's no Unity editor for webxr and that sucks. The standard libraries and non-standard libraries people have made available are way more and better than what's in javascript land.

Q: **That's too bad that graphics parity is not a priority, is that because high end systems are rare?**
A: I'm sure its a priority for people working on webgl but not sure why it seems to lag behind a little bit. I'm guessing as a programmer that the browser stuff is one abstraction layer higher above the rest of it so not surprised if lower down abstraction layer gets done first when it comes to new features and so on.

Q: **As an Altspacer did you see the Anyland model or other interesting complex social VR software development models?**

A: I've used Anyland a little bit but not sure what you mean by the model: the philosophy of building environment from inside of it? I think that is really cool. Don't know how to do a good job of it, it's really appealing and can make cool stuff and I guess what makes me a little skeptical or confused about it is people have thought visual programming with blocks and visual representation of source has been a good idea for a long time but its never become really popular except in very small domains (scratch / logo / maxmsp). No one sits around making general purpose programs in visual environments and not sure why, guess no one has come up with something better than a text file yet.

Think its a really cool idea if Spoke, the part of putting together a 3D environment, was in VR or multiplayer. Haven't tried the Unity or Unreal in-VR editors.

[Non-text programming: spatial metaphors for composing behaviors](https://youtu.be/LMkdA6OCdGs?t=2076) 

It seems like you should be able to use multimedia representations of programs to aid in understanding and composition of programs somehow. Even if you used this environment as feedback somehow.

[The tools can structure what can be made](https://youtu.be/LMkdA6OCdGs?t=2141)

[Already better than Google Hangouts](https://youtu.be/LMkdA6OCdGs?t=2387)

---

## [Editing XR in XR](https://youtu.be/qwOOgvEiN_M)

![](https://i.imgur.com/dE4fwhf.jpg)

Tool for editing #WebXR scenes from within XR using a unix-like shell.

Demo: <https://ranger.mauve.moe/dat-xr-scene-ide/>

[How can I edit a VR scene live?](https://youtu.be/qwOOgvEiN_M?t=159)

Workflow so far is opening a text editor, messing code, saving, then refreshing the web page.

Works great on computer but not in a VR headset.

<https://twitter.com/fernandojsg/status/1139220673438597120>

Used to using command line and the browser dev tools then thought, "what if I could press a button and get a terminal inside VR?".

Glued a library called xterm js, trying to integrate with aframe and getting the html/css into the scene is a pain but noticed they updated to start using an actual canvas to get higher performance.

Other cool thing is people can make tools in VR for editing in VR! High level way to import other components into the world. Inspired by Playstation Dreams - people can share 3D assets and bits of logic in there, would be really cool for webxr also.

<https://youtu.be/qwOOgvEiN_M?t=1076>

---

## [bnolan on Cryptovoxels](https://youtu.be/3fdDqHpurbg)

![](https://i.imgur.com/KQBIkql.jpg)

Voxel world built using a voxel engine (got it from voxel.js guys) and the land ownership of the world is recorded on the Ethereum blockchain. This decentralized ledger says which part of the world you own and which part you can build on. 

**Tech Stack**: Uses webgl, webvr support, webrtc for voice chat, web audio api for positional audio, websockets and node.js on backend. Looking at Dat and libp2p stuff and want to move towards a decentralized open source project. 


Starting with monolithic node at the moment as it keeps it nice and simple: MOMS <https://gist.github.com/bnolan/874986afc05f52093d657423da63b98b>

```
Monolith with Opensource Microservices.

Basically, you write your app as a monolith because its quick and easy.

And when you have a subsystem of sufficient complexity and independent enough (doesn’t require being deeply enmeshed in your app), you split it out to a microservice that you opensource.

By opensourcing it, it makes you think of how other people might use it, so you make the APIs a bit more generic, you document it better with a readme, and you standardise the deployment so it’s easy for you to deploy.

The opensourcing has real benefits, even if no-one ever sends you PRs.

MOMs.
```

People use the platform a lot to share art, galleries, cryptocollectibles. Also interested in NFTs that are 3D objects that one can add to their avatar and use them in multiple worlds. For example, if you have a voxel hat in CV you can wear it Somnium Space or wherever. Would like to add support to the aframe multiplayer stuff so that when using multiplayer your avatar can automatically request information from the blockchain and render any add-ons that you have.

Q: **Where do you wanna take Cryptovoxels next? What drives it?**
A: I wanna build the Metaverse, not the whole Metaverse but a cool chunk of it. Full response: <https://youtu.be/3fdDqHpurbg?t=280>

Q: **Have you planned about non-voxel data structures that use the Cryptovoxels framework?** 
A: <https://youtu.be/3fdDqHpurbg?t=352>

Q: **What do you think about Minecraft Earth being a voxel AR base-layer?** 
A: <https://youtu.be/3fdDqHpurbg?t=412>

Q: **How many people are online in world on cryptovoxels daily/weekly?** 
A: <https://youtu.be/3fdDqHpurbg?t=560>
