---
id: 62uvt4wq44gamu00zfnuhqx
title: HLA Time Management Services
desc: ''
updated: 1676931268202
created: 1676930953143
---

## [[p.referredFrom]] https://en.wikipedia.org/wiki/High_Level_Architecture#Time_Management_Services

Some important concepts in HLA Time Management are:

**Logical time**: A time axis in HLA, starting at zero. Logical time is used for Time Management timestamps and operations. The logical time axis can be mapped to the scenario time of the federation. An example of such a mapping is to let zero represent the scenario time 8:00 of the 1-Jan-[1066](https://en.wikipedia.org/wiki/1066) and let an increment by one represent one second of the scenario.

**Lookahead**: A time interval specifying the lowest time in the future for which a federate will produce messages. For a federate with a fixed time step, this is usually the length of the time step.

**Granted**: A federate is granted (allowed to advance) to a particular logical time by the RTI, when all time-stamped messages up to that time have been delivered. The federate can then safely start calculating messages with a timestamp in the future. This timestamp may not be earlier than the granted time plus the federates lookahead.

**Advancing**: When a federate has finished producing data for the granted time plus the lookahead, it may request to be advanced to a later time, which also means that it promises not to produce any more messages with a time stamp less than the requested time plus the lookahead. The federate is now in the advancing state.

**Time Regulating**: A federate that sends time stamped events is considered Time Regulating since the time advance by other federates may be regulated by this.

**Time Constrained**: A federate that receives time managed events is considered Time Constrained since the reception of time stamped messages, constrains its time advance.

The main principles of HLA Time Management are that:

-   Each time-regulating federate assigns a time stamp to messages (updates and interactions) when they are sent, indicating the scenario time at which the message is valid.
-   The RTI manages delivery of messages to time-constrained federates, with messages from time-regulating federates delivered at the appropriate time using a Time Stamp Order queue.
-   Time-constrained federates request permission from the RTI to advance their time.
-   The RTI grants a time advance to a time-constrained federates when it is sure that the federate cannot receive a message with a time stamp in its past.

Example of Lookahead, granted and advancing:

1.  A federate uses a fixed time step of 10 and has a Lookahead of 10.
2.  The federate is granted to logical time 50 by the RTI. The RTI thus guarantees that all messages with time step less or equal to 50 have been delivered to the federate.
3.  The federate now has all the necessary data to correctly calculate and send messages for the granted time plus Lookahead, i.e. 60.
4.  When the federate has sent all messages with timestamp 60, it requests to be advanced to time 60. It thereby promises not to send any messages with a timestamp less than 70.
5.  The RTI delivers all messages with timestamp less or equal to 60 to the federate. It then grants the federate to time 60.
6.  Etc.

If at least one federate in the federation performs pacing, i.e. correlates their time advance requests with a real time clock, the federation may run in real time or scaled real time. Without pacing, the federation will run as fast as possible (e.g., federations that do not require human interaction at runtime nor interfaces with systems that depend upon a real-time clock can run as fast as computing resources will allow).

Key services include:

-   EnableTimeConstrained and EnableTimeRegulating that enables theses modes for a federate
-   TimeAdvanceRequest whereby a federate requests to be advanced to a specified logical time
-   TimeAdvancedGrant whereby the RTI informs a federate that it is granted to a specified logical time.
-   EnableAsynchronousDelivery that enables delivery of Receive Order messages both when a federate is in the granted and advancing state.

For event driven simulation it is also possible for a federate to request to be advanced to the next event using the following service:

-   NextMessageRequest whereby a federate requests to be advanced to the timestamp of the next message due for delivery to the federate, or a specified logical time, whichever has a lower timestamp.

Another important concept is **Greatest Available Logical Time** (GALT). The greatest time that each federate can be granted to, depends on the time that other federates have been granted to as well as their lookahead. The GALT for a federate specifies how far a federate can be granted, without having to wait for other federates to be granted. This is particularly interesting for a federate that joins late into a time managed federation.

Key services for GALT are:

-   QueryGALT that returns the GALT for the calling federate.

More advanced services include:

-   FlushQueueRequest whereby a federate can request delivery of all queued, timestamped messages, no matter how far in the future their timestamp is.
-   Retract whereby a federate can request that an already sent message is retracted. This is useful in optimistic simulation.