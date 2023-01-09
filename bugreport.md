# # [BUG] Spellqueue doesnt work if heroic strike is queued. 

### 1. Current Behavior
  #### 1.1. Description
The way that spellqueue currrently works for warriors, is that as long as HS is not queued you can queue up your next ability correctly. However once HS is queued you are unable to do so. Resulting in no spellqueue window, which increases delay on abilities and therefore lowering dps. 
This forces the warrior to spam abilities to counter some of the delay, but it will still result in some delay depending on human factors and your own latency. 

There has also been other mentions of this.
https://streamable.com/g8kbue
https://us.forums.blizzard.com/en/wow/t/this-bug-is-one-of-the-reasons-why-fury-warriors-are-so-bad-at-the-moment/1408439
https://us.forums.blizzard.com/en/wow/t/warrior-spell-queue-not-working/1421625

  #### 1.2. How to Reproduce
  To reproduce it does requires you to attempt several times, as we are talking about a small window of where you can queue your ability and therefore it is not always transparent when you are using the spellqueue system.
     
           1. First ensure that your spellqueuewindow is set to default (400) 
           2. Gain full rage
           3. Attack a dummy and queue a HS when your main hand hit the target
           4. Press a GCD ability (Ex: Bloodthirst)
           5. Once GCD timer is below 0.4s press a different GCD ability before HS goes off
           6. This will result in second GCD ability not being cast
           7. Same can be repeated without HS, where second GCD ability will cast}
  #### 1.3  Source Material
  The red bar is the GCD of the ability and I am casting BT and WW.
  https://streamable.com/1warwp
  https://streamable.com/shr169
  https://streamable.com/90hpo4
  Here we see it working without HS
  https://streamable.com/g8kbue
  
https://www.youtube.com/watch?v=l--e74c9v48&t=21s

### 2. Expected Behavior
  #### 2.1. Description
The spell queue functions as a system for lag mitigation, allowing users to queue an ability while waiting for GCD cooldown to come off. This removes the local delay and system delay one would typically get. The spellqueue window can be set from 0-400, and 400 is the default that most players are using. The spellqueue window timing can be found using:
```
/dump GetCVar("SpellQueueWindow")
```
It is a system that benefits everyone, as no matter how good your system is you will always have different degree's of delay. 

The expected behaviour is therefore that when you use a GCD ability, while having HS queued, you would expect that you could queue up your next ability and it would cast. However if HS is queued while this happens, it does not work, forcing you to spam buttons and experience delay in your casts. Resulting in a decent dps loss. 

Older videos seem to display that it was not a bug back then, but as video quality is bad, and the systems generally had more latency it can be hard to determine.

  #### 2.2 Source Material
  http://thedefiantguild.com/forums/discussion/15431.html
  https://streamable.com/g8kbue
  https://www.youtube.com/watch?v=OQwT1gYSDVk&t=50s
  https://youtu.be/jQxQ7TJQJQg
