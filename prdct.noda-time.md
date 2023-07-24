---
id: 85nltdweybeqpecpcjeyntw
title: Noda Time
desc: 'an alternative date and time API for .NET'
updated: 1689965610606
created: 1689963158118
---

#url  https://nodatime.org

## c.Documentation

### https://nodatime.org/3.1.x/userguide/concepts

- Time is measured with a granularity of nanoseconds. This is 100 times finer than the granularity used in DateTime and TimeSpan in .NET, which is the tick.
- Instant is a good type to use for "when something happened" - a timestamp in a log file, for example. The instant can then be interpreted in a particular time zone and calendar system, in a way which is useful to the person looking at the log.
- 

## [[c.Resource]]

- https://blog.nodatime.org/2011/08/what-wrong-with-datetime-anyway.html