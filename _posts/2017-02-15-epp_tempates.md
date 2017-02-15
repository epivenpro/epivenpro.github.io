---
title: EPP templates in Puppet
---

These are seriously cool.

Templates support all these nifty thingies worthy of a mature language:
* accept a specific set of parameters
* parameters support types!
* call regular puppet functions inside

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
