---
title: Puppet Testing
---
### What's up with this whole testing thing?

So, a couple months ago our DevOps team introduced us to this concept of testing Puppet code. And, though I knew
(albeit remotely) what testing was, this felt weird.

The idea was to use this "kitchen" thingie to check that after applying a manifest like this:

```puppet
service { 'nginx':
  ensure => running,
  enable => true,
}
```

you'll get a running nginx service.

Now, why would we do that? Isn't the whole purpose of using service resource to make sure we have a running service?
Why would we complicate things by having to write extra code to make sure it actually worked?

Silly me.

Good thing I didn't give up right away. I spent a weekend trying to get kitchen to work using Docker on macOS, started
reading up on beaker and wondering why wouldn't we use that.

When my first test passed, it was a bliss. I didn't quite know what I was getting into back then. It all seemed really
bulky. The test suite would take ages to start up, there was a lot of set up involved, I never had any
Ruby/Gemfile/Rakefile experience. Everything seemed like a mess.

But I was hooked.

### What to test for?

Basically, everything.

The more logic you have, the more test cases are appropriate.
