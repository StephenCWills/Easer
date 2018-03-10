Event Types will be dropped in v0.5.7 (article written for v0.5.6). They can be replaced by advanced Scenario conditions.

Generally, Event Types have these direct mappings:
* is / any <--> nothing to do (i.e. set *reverse* to `false` & set *retriggerable* to `false` & set *volatile*)
* is_not / none <--> set *reverse* to `true`
* after <--> set *persistent* & (maybe) set *retriggerable* to `true`
* before <--> combination of *is_not* and *after*