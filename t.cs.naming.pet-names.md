---
id: cvte4qrydz9ln9x45ea2bp0
title: Pet Names
desc: 'do not confuse the nickname-as-proposal with the petname-as-decided. Never in a true petname system is the nickname presented or employed as if it were a petname.'
updated: 1713148451295
created: 1713148342618
---

Each name set consists of three elements: a key that is global and securely unique (but not necessarily memorable); a nickname that is global and memorable (but not at all unique) , and a petname that is securely unique and memorable (but private, not global):

    Keys lie at the heart of the security properties of the petname system. Nicknames and petnames exist to make it easy for human beings to manipulate keys. The security of the system can be no stronger than the unforgeability of the keys. Self-authenticating public/private key pairs make excellent keys since they have strong unforgeability properties. But there are other ways of achieving unforgeability. A trusted path can also work well as the key: the full pathname to a file on a specific computer is also unforgeable (or at least, as unforgeable as the designation of the specific computer, which can be quite strong in some cases). It does not make any difference in a petname system whether a key can be mimicked: keys are handled only by the computer, the human being handles the keys only indirectly via petnames. For a particular person, for a particular application, there is a one-to-one mapping between a key and a petname.

    Nicknames can be used to assist in discovery of keys, and for help in selecting a petname. Nicknames are chosen by the owners of  keys in hopes of creating a distinctive, if not unique, mapping from the memorable nickname to the key. Such nicknames often are promulgated throughout the world in the hopes of making the nickname stick in the mind as a reference to the key. Since there are strong incentives to "take ownership" of a nickname, even though true ownership is not possible, nicknames are the most often misunderstood part of a petname system.

    In the simple case, a nickname has a one-to-many mapping to keys The name John Smith is obviously a nickname: there are many John Smiths.Other nicknames produce the illusion of being globally unique: the name Marc Stiegler appears to be globally unique at the time of this writing. But there is no security property in this accident of global uniqueness. The uniqueness of the name Marc Stiegler would change quite quickly if, through the mysterious forces of human whimsy, the name suddenly became desirable. Sometimes the desirability of a nickname is not whimsical, but venal. It is already desirable for some applications to call themselves Quicken, for example, and draw windows that request a Quicken password.

    Petnames are our private bidirectional references to keys. There are many Mark Millers, but there is one specific Mark Miller that the name means to me, the Mark Miller who works with object-capabilities for secure cooperation. "Mark Miller" is Mark Miller's nickname; it also happens to be my petname for the same individual. My private pet name for my wife is not recognizably similar to the public nickname used by my wife. In the computer setting, for a specific person with a specific application, petnames are unique, each petname refers to exactly one key, and each key is represented by exactly one petname. In all places in the application where the app wants to designate the key, the petname is displayed -- which is to say, a true petname is a bidirectional one-to-one mapping to a key. All references to the key by the user interface are represented by petname. A key cannot have two petnames; if a single key had two petnames, under what circumstances would the user interface use petname1 as the representation of the key, and under what circumstances would it bring up petname2?



## References

- http://www.skyhunter.com/marcs/petnames/IntroPetNames.html