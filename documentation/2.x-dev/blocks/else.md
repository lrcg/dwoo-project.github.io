---
layout: documentation
title: Blocks:else
---

Generic else block, it supports all builtin optional-display blocks which are [if](/documentation/2.x-dev/blocks/if.html), [loop](/documentation/2.x-dev/blocks/loop.html), [for](/documentation/2.x-dev/blocks/for.html), [foreach](/documentation/2.x-dev/blocks/foreach.html) and [with](/documentation/2.x-dev/blocks/with.html).


If any of those block contains an else statement, the content between `{else}` and `{/*blockname*}` (you do not need to close the else block) will be shown if the block's condition has no been met.

##Example
{% highlight smarty %}
{foreach $array val}
  $array is not empty so we display it's values : {$val}
{else}
  if this shows, it means that $array is empty or doesn't exist.
{/foreach}
{% endhighlight %}
