---
title: EPP templates in Puppet
---

These are seriously cool.

You can do all these nifty thingies worthy of a mature language:
* pass values to it
* accept only a specific set of values
* parameters support types!
* call regular puppet functions

```puppet
<%- |
  String         $name,
  Cron::Minute   $minute,
  Cron::Hour     $hour,
  Cron::Monthday $monthday,
  Cron::Month    $month,
  Cron::Weekday  $weekday,
  String         $user,
  String         $command,
| -%>
# <%= $name %> cron job

<%

  # cron::cron2string
  # converts the cron time instance to a string ready to be put into cron file

  $cron_time = join([
      cron::cron2string($minute),
      cron::cron2string($hour),
      cron::cron2string($monthday),
      cron::cron2string($month),
      cron::cron2string($weekday),
  ], ' ')

-%>
<%= $cron_time %> <%= $user %> <%= $command %>
```
