---
title: bundle config path ~/.bundle
---

This has seriously been bugging me. I even made this post to prove it.

I've been wondering why this never worked:

```bash
 % bundle config path ~/.bundle
 % bundle config
Settings are listed in order of priority. The top value will be used.
path
Set for the current user (/Users/pegas/.bundle/config): "/Users/pegas/.bundle"
```

Yet still every time I would try to install gems with `bundle install`, they will inevitably
end up in the system gem directory.

Well, having completely wiping out a bunch of `rvm` rubies and then installing them back again,
I decided to Google up and found this guy:

```bash
 % bundle config path.system false
 % bundle config
Settings are listed in order of priority. The top value will be used.
path
Set for the current user (/Users/pegas/.bundle/config): "/Users/pegas/.bundle"

path.system
Set for the current user (/Users/pegas/.bundle/config): false
```

And voila!

Now every time I run `bundle install`, it auto-magically works!
