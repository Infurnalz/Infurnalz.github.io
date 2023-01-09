# # [BUG] Spellqueue doesnt work if heroic strike or Cleave is queued. 

### 1. Current Behavior
  #### 1.1. Description
The way that spellqueue currrently works for warriors, is that as long as HS/cleave is not queued you can queue up your next ability correctly. However once HS is queued you are unable to do so. Resulting in no spellqueue window, which increases delay on abilities and therefore lowering dps. 
This forces the warrior to spam abilities to counter some of the delay, but it will still result in some delay depending on human factors and your own latency. 

Display of it not working.

https://streamable.com/38p7j6

https://streamable.com/g8kbue

There has also been other mentions of this.

https://us.forums.blizzard.com/en/wow/t/this-bug-is-one-of-the-reasons-why-fury-warriors-are-so-bad-at-the-moment/1408439

https://us.forums.blizzard.com/en/wow/t/warrior-spell-queue-not-working/1421625

  #### 1.2. How to Reproduce
  To reproduce it does requires you to attempt several times, as we are talking about a small window of where you can queue your ability and therefore it is not always transparent when you are using the spellqueue system.
     
       1. Ensure that spellqueuewindow is set to the default value of 400 
       2. Gain a full rage bar.
       3. Attack a dummy and use Heroic Strike (or Cleave) right after your main hand has struck the target~.
       4. Use an ability that's on the GCD, for example Bloodthirst.
       5. Once the GCD cooldown timer is below the spellqueuwindow (400ms in this example) press another ability on the GCD, whirlwind.
       6. Once the GCD cooldown is over, the next ability should be cast, but it doesnt.
       7. Repeat this process without using Heroic Strike (or Cleave) and notice how Whirlwind does fire.
      
  #### 1.3  Source Material
  The red bar is the GCD of the ability and I am casting BT and WW.
  https://streamable.com/1warwp
  
  https://streamable.com/shr169
  
  https://streamable.com/90hpo4
  
  Here we see it working without HS
  
  https://streamable.com/g8kbue
  
https://www.youtube.com/watch?v=l--e74c9v48&t=21s

Video of Cleave showing the same bug
https://streamable.com/38p7j6

### 2. Expected Behavior
  #### 2.1. Description
The spell queue functions as a system for lag mitigation, allowing users to queue an ability while waiting for GCD cooldown to come off. This removes the local delay and system delay one would typically get. The spellqueue window can be set from 0-400, and 400 is the default that most players are using. The spellqueue window timing can be found using:
```
/dump GetCVar("SpellQueueWindow")
```
It is a system that benefits everyone, as no matter how good your system is you will always have different degree's of delay. 

The expected behaviour is therefore that when you use a GCD ability, while having HS queued, you would expect that you could queue up your next ability and it would cast. However if HS/cleave is queued while this happens, it does not work, forcing you to spam buttons and experience delay in your casts. Resulting in a decent dps loss. 

Older videos seem to display that it was not a bug back then, but as video quality is bad, and the systems generally had more latency it can be hard to determine.

  #### 2.2 Source Material
  http://thedefiantguild.com/forums/discussion/15431.html
  
  https://streamable.com/g8kbue
  
  https://www.youtube.com/watch?v=OQwT1gYSDVk&t=50s
  
  https://youtu.be/jQxQ7TJQJQg
