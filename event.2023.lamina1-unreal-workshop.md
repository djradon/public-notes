---
id: gc0fvqvu98o459dbspnqcsb
title: Lamina1 Unreal Workshop
desc: ''
updated: 1698340969854
created: 1698336367018
---

t.2023.10.26.09

#related: https://discord.com/channels/771063831387439134/1072828679425638430/1167134651035439124

## Speakers

- @ivystive
- @chris-mahoney
- @will-carter
- @beardontheblock
- @ryan-crucible

## Prerequisites

💫 Download this Unreal Package: https://tinyurl.com/3bh5tvrk
💫 Set up a LAMINA1 Hub account & connect it to Metamask: https://tinyurl.com/mpsbd8vc
💫 Have a code editor installed like #VisualStudio or #Rider

## Highlights

- Anyone who wants to request future workshop deep dives from our teams, leave feedback on the workshop, or contact us about working together on an upcoming Space/experience launch on LAMINA1, please fill out this form! https://blocksurvey.io/emergence-workshop-follow-up-form-s7tjFoH3RtO5pghC.Ly0sg?v=o
- [ ] around 55min, mention of "json data"
- Unity vs Unreal
  - unreal has a couple more things, like keystore
  - @will-carter 58:40 - json metadata

## [[c.transcript]]

djradon
djradon
Online
BeforeCrypto
 — 
Today at 9:22 AM
emergenge sample not apearing in unreal
Aleissia
 — 
Today at 9:23 AM
Did you download via the link provide or the marketplace? 

Link to download is here: https://github.com/CrucibleNetworksLtd/EmergenceSDKUnreal/releases/tag/v0.3.3
GitHub
Release v0.3.3.1 · CrucibleNetworksLtd/EmergenceSDKUnreal
The plugin is also on the Unreal Engine Marketplace (for free)!
Additional Release files
A sample project has been made to show how to make use of the Emergence plugin. It is supplied with a specia...
Release v0.3.3.1 · CrucibleNetworksLtd/EmergenceSDKUnreal
BeforeCrypto
 — 
Today at 9:23 AM
i have both
Aleissia
 — 
Today at 9:23 AM
You'll see there's a "Lamina1UnrealSampleProject.zip" there
that's where the sample project will be
you'll want to then open the EmergenceSample.uproject that is in that zip
BeforeCrypto
 — 
Today at 9:25 AM
yea i unzipped
Aleissia
 — 
Today at 9:25 AM
Once you open the uproject, it will build for you, and then this sample project should open for you inside Unreal. It normally takes a few mins to build the first time around.
BeforeCrypto
 — 
Today at 9:27 AM
The following modules are missing or built with a different engine version:

  EmergenceSample
  Emergence
  EmergenceEditor
  EmergenceEditorMethodGraphPin
  EmergenceEmailForm
  EmergenceVRMSupport
  VRM4U
  VRM4ULoader
  VRM4UCapture
  VRM4UImporter
  VRM4UEditor
  VRM4UMisc

Would you like to rebuild them now?
Aleissia
 — 
Today at 9:27 AM
Yes, rebuild
BeforeCrypto
 — 
Today at 9:27 AM
Its showing like this
Aleissia
 — 
Today at 9:27 AM
that's what takes a few mins to rebuild
Wilson
 — 
Today at 9:28 AM
is it matic ?
Aleissia
 — 
Today at 9:28 AM
So just press YES there to rebuild. Once its done, the sample project will open up
BeforeCrypto
 — 
Today at 9:28 AM
do i need to launch unreal now ?
Aleissia
 — 
Today at 9:28 AM
Nope once its done rebuilding it should auto-open the project for you
WillCarter
 — 
Today at 9:28 AM
If you'd like to run a local RPC node for dev (more responsive) then you can follow the instructions here:  https://docs.lamina1.com/docs/Running-a-Betanet-Node#set-up-your-node and update the Default Node URL in Emergence to http://127.0.0.1:9650/ext/bc/C/rpc 
BeforeCrypto
 — 
Today at 9:28 AM
ok
@Aleissia is video available for chris done today
Aleissia
 — 
Today at 9:30 AM
Yes this is being recorded as well
BeforeCrypto
 — 
Today at 9:30 AM
ok
how long it will take to build
EL | MALAMAYA
 — 
Today at 9:30 AM
do we still use metamask for l1 tokens?
Aleissia
 — 
Today at 9:30 AM
and we have the step by step in our dev docs as well. Video for both this and yesterday's will be posted later today. We'll be sure to post in both discord & Twitter (X)
Yes still use MM for L1 Tokens!
ivystive
 — 
Today at 9:31 AM
You can definitely use MM to interact with LAMINA1. I've got instructions here on the best way to connect your LAMINA1 Hub account to your MM wallet: https://docs.google.com/document/d/18N2CVhD8xpSQRmaMl6qsM1WO4InGGJNauMFwx63_kFs/edit?usp=sharing
WillCarter
 — 
Today at 9:32 AM
Sent 2 L1
EL | MALAMAYA
 — 
Today at 9:32 AM
thanks for this!
BeforeCrypto
 — 
Today at 9:32 AM
Still not build @Aleissia
Sifr
 — 
Today at 9:33 AM
The previous wallet address was coinbase
Aleissia
 — 
Today at 9:33 AM
What version of Unreal are you running? And do you see the progress bar going still?
ivystive
 — 
Today at 9:34 AM
whooops
BeforeCrypto
 — 
Today at 9:34 AM
5.3
EL | MALAMAYA
 — 
Today at 9:34 AM
how do we get to the L1 Betanet network in Metamask?
Sifr
 — 
Today at 9:34 AM
🤦🏽‍♂️
Aleissia
 — 
Today at 9:34 AM
Unreal 5 sadly doesn't show the progress when it's building. Meh they removed that in 5. Maybe try reopening the uproject again.
BeforeCrypto
 — 
Today at 9:35 AM
oh damn'
it showing to rebauild again
Aleissia
 — 
Today at 9:36 AM
Do yes again, Unreal is normally smart enough to only rebuild what hasn't been built yet 😉 normally
We can also jump on with you directly to help you get setup after this @BeforeCrypto !
BeforeCrypto
 — 
Today at 9:36 AM
Normally :sip:
BeforeCrypto
 — 
Today at 9:37 AM
If video guide available that will good
Aleissia
 — 
Today at 9:38 AM
Yup all will be available! Also here's the dev doc that is step by step for getting things setup! 

https://docs.emergence.site/game-engines/unreal/getting-started
Getting Started
Requirements, Installing the plugin and opening the overlay.
Getting Started
BeforeCrypto
 — 
Today at 9:38 AM
EmergenceSample could not be compiled. Try rebuilding from source manually.
EL | MALAMAYA
 — 
Today at 9:38 AM
How do we get to the L1 Betanet network in Metamask?
BeforeCrypto
 — 
Today at 9:38 AM
now showing like this @Aleissia
Jackalgirl (she/her)
 — 
Today at 9:38 AM
https://docs.lamina1.com/docs/the-l1-staking-wallet/#connecting-metamask-to-the-lamina1-betanet - if you need to add it as a custom network.
Okay, so while we're playing this demo to see how it works, we need to have Polygon (and MATIC tokens) for the Emergence avatar side of things, and the L1 Betanet and L1 Betanet tokens for the trophy minting, is that correct?
Aleissia
 — 
Today at 9:41 AM
Yes that is correct. Neither are musts but there's 2 mint options in this project: 

    L1 will allow you to mint the L1 Trophy.
    Matic will allow you to mint your own VRM Avatar. So you can test out the whole flow of then having an avatar tied to your persona.


As a note, if ever you have another NFT Avatar you would love to use, we can help you get that setup, if it isn't already registered in our Emergence Avatar System.
Alchemist 19
 — 
Today at 9:44 AM
You guys totally rock!!!
Sifr
 — 
Today at 9:44 AM
Just realised I signed up to Lamina1 through email, so my address is actually 0x676E706aE6a7475bB2629E1011e942e619040fb1
WillCarter
 — 
Today at 9:45 AM
You're bleeding me dry
Aleissia
 — 
Today at 9:45 AM
Gameplay Examples of some things you can do with Emergence. Here you can see examples like: 

    Token gated areas
    Trading with NPCs (NFT Trading)
    Using our DynamicMetadata to add extra info to your NFTs
    Picking up collectibles / coins in game.
    A jukebox that streams your NFT music


Loads more you can do! 
https://www.youtube.com/watch?v=X5ADCzW9QWs
YouTube
Open Meta
Emergence Examples in The Lab
Image
BeforeCrypto
 — 
Today at 9:46 AM
@Aleissia looks like emergence pulgin installed, dont know how to open that
Sifr
 — 
Today at 9:46 AM
It's betanet so the token is worth null, spread the love brother lol.
Jackalgirl (she/her)
 — 
Today at 9:46 AM
Awesome, that makes a lot of sense (and gives me something to do to troubleshoot the issue I was having with the Unity demo).  I presume that we could retool the avatar system so that it works on the Lamina1 blockchain (provided that we either provide, or there is present, a comparable contract on Lamina1)?  I know this would not make it work across the whole Emergence ecosystem, but I'm just thinking of ways to keep things simple for Lamina1 users (to keep everything within the Lamina1 network, and users needing only the one token).
Aleissia
 — 
Today at 9:46 AM
Right after were done here, @Chris could hop on with you! Makes me think it's a 5.3 issue! But i'm sure Chris can get a version working for u once this is done!
Chris
 — 
Today at 9:47 AM
https://youtu.be/X5ADCzW9QWs
YouTube
Open Meta
Emergence Examples in The Lab
Image
Alchemist 19
 — 
Today at 9:48 AM
Hey @Jackalgirl (she/her) make sure you develop a working understanding here.
I just dropped in. I was teaching a class
Aleissia
 — 
Today at 9:48 AM
For Avatars specifically. We currently have our system working for Ethereum and Polygon. But we can def add in support for L1! 

Something we spoke about with @g0rd0 😉
We have a custom indexer and I know we both would love to extend it to index all NFTs (avatars included) for L1!
Alchemist 19
 — 
Today at 9:48 AM
I am sure I will quickly catch up. Hello @ivystive
ivystive
 — 
Today at 9:49 AM
Hello, Alchemist19! How are you today?
Jackalgirl (she/her)
 — 
Today at 9:49 AM
GLEE
Aleissia
 — 
Today at 9:49 AM
Love this example too. Avatars could be used as AI Pets too, not just your own avatar 🙂
Alchemist 19
 — 
Today at 9:50 AM
@ivystive just digesting what's here so we can guide the gang
Aleissia
 — 
Today at 9:51 AM
In future workshops. We want to dive into loads of these examples! This first 101 was meant to be able to show the basics of getting setup. And the basics of how to use the read / write functionality. From there though, future workshops will show how to use the read / write for loads of gameplay examples!
Alchemist 19
 — 
Today at 9:51 AM
@Aleissia awesome work thus far
Aleissia
 — 
Today at 9:54 AM
We have a BOUNTY for todays workshop! Make sure to take a screen shot of the super secret code and submit it via this link: https://www.openmeta.xyz/bounties/submit/653a6502825d9fd8c64c5f41

Code will be posted shortly!
Open Meta
Open Meta
Dominith
 — 
Today at 9:56 AM
Great workshops today and yesterday! Thank you all very much for sharing this. 😊
djradon
 — 
Today at 9:56 AM
From the Emergence perspective, are there any significant differences between Unity and Unreal?
ivystive
 — 
Today at 9:57 AM
Anyone who wants to request future workshop deep dives from our teams, leave feedback on the workshop, or contact us about working together on an upcoming Space/experience launch on LAMINA1, please fill out this form! https://blocksurvey.io/emergence-workshop-follow-up-form-s7tjFoH3RtO5pghC.Ly0sg?v=o
EL | MALAMAYA
 — 
Today at 9:57 AM
I'm not a really good game developer, but I do make 3D assets. How can I contribute to Lamina1?
Aleissia
 — 
Today at 9:57 AM
@BeforeCrypto  Chris said he can jump on with you right after this. There was an issue in 5.3 but it was fixed. But he can jump on with you after this to find the issue with you!
ivystive
 — 
Today at 9:57 AM
Reach out to us at ecosystem@lamina1.com. We're also looking for asset collection creators 🙂
Aleissia
 — 
Today at 9:59 AM
Unity and Unreal are meant to be feature parity, a few additional features today in Unreal but goal is to get to full feature parity for Emergence.

From an engine perspective, Unreal is alot more visual designer focused because of blueprints. Which can be great for non-coders. 
Chris
 — 
Today at 9:59 AM
would you be able to post the log file?
EL | MALAMAYA
 — 
Today at 9:59 AM
What do I say? I'm keen on making assets for games and metaverse platforms 🍻
Chris
 — 
Today at 10:00 AM
there might be a build log file in saved/logs
ivystive
 — 
Today at 10:00 AM
Yes. And share us the kind of assets, tech details, screenshots or images of what you make. Website, etc etc
BeardOnTheBlock
 — 
Today at 10:00 AM
SCREENSHOT THIS CODE!!

LAMINA1OPENMETAFRENS

(This is for the bounty)
ivystive
 — 
Today at 10:00 AM
https://hub.lamina1.com/ 💫
Come visit us!
BeforeCrypto
 — 
Today at 10:02 AM
when i open emergence sample, It showing "EmergenceSample could not be compiled. Try rebuilding from source manually."
Chris
 — 
Today at 10:03 AM
did the saved folder get created?
ivystive
 — 
Today at 10:04 AM
Survey: https://blocksurvey.io/emergence-workshop-follow-up-form-s7tjFoH3RtO5pghC.Ly0sg?v=o
RyanCrucible
 is now a speaker.
 — 
Today at 10:04 AM
Jackalgirl (she/her)
 — 
Today at 10:04 AM
@ivystive if we filled it out for Unity, do you want it again for Unreal?
MAiWORLD
 — 
Today at 10:04 AM
Q: for dynamic metadata, would this be a seperate layer of metadata that can applied to already existing NFT collections?  and this layer of metadata would not be on chain?  i.e. used specifically for in-game logic**

follow up:  would there be a way to allow this dynamic metadata to be written and thus change an NFT's actual on chain metadata?  like it's artwork or a type of metadata that is already on chain?

hope that makes sense ty 
Aleissia
 — 
Today at 10:05 AM
Would be great if you guys can create a chat together, since this chat will go away once the event is done
BeforeCrypto
 — 
Today at 10:05 AM
i can t find any project name with emergence sample in unreal
Chris
 — 
Today at 10:05 AM
can you create a thread about this in 
⁠🪧︱emergence-topics pls :)
EL | MALAMAYA
 — 
Today at 10:06 AM
I just sent an email! Looking forward to your reply, cheers!
BeardOnTheBlock
 — 
Today at 10:06 AM
SCREENSHOT THIS CODE!!

LAMINA1OPENMETAFRENS

(This is for the bounty)
WillCarter
 — 
Today at 10:06 AM
There are some interesting ways to do this by wrapping existing NFTs to extend functionality. It raises questions about who is allowed to extend functionality and how to use that functionality which we're working on
Aleissia
 — 
Today at 10:06 AM
Great question! 

As of right now, this is a way to add additional metadata to NFT collections. That is currently saved off-chain with using all the authentication / etc of what the owner of the NFT sets for it. 

We are also building out standard templates so NEW nft creators can utilize that as well. 

Goal is to be allow any creator / developer to treat an NFT like a game object. Read/Write based on the permissions the owner sets.
Future workshop JUST on Dynamic Metadata would be fun!
WillCarter
 — 
Today at 10:07 AM
Oh yeah Dynamic Metadata workshop would be cool
BeforeCrypto
 — 
Today at 10:08 AM
⁠Unreal 5.3.1
MAiWORLD
 — 
Today at 10:08 AM
super cool, thank you, and yes need that dynamic metadata workshop haha
﻿