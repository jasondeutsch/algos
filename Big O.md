1. **how quickly the runtime grows**—It's hard to pin down the *exact runtime* of an algorithm. It depends on the speed of the processor, what else the computer is running, etc. So instead of talking about the runtime directly, we use big O notation to talk about *how quickly the runtime grows*.
2. **relative to the input**—If we were measuring our runtime directly, we could express our speed in seconds. Since we're measuring *how quickly our runtime grows*, we need to express our speed in terms of...something else. With Big O notation, we use the size of the input, which we call "nn." So we can say things like the runtime grows "on the order of the size of the input" (O(n)O(n)) or "on the order of the square of the size of the input" (O(n^2)O(n​2​​)).
3. **as the input gets arbitrarily large**—Our algorithm may have steps that seem expensive when nn is small but are eclipsed eventually by other steps as nn gets huge. For big O analysis, we care most about the stuff that grows fastest as the input grows, because everything else is quickly eclipsed as nn gets very large. (If you know what an asymptote is, you might see why "big O analysis" is sometimes called "asymptotic analysis.")

space complexity
----------------

We simply look at the total size (relative to the size of the input) of any new variables we're allocating.

**Usually when we talk about space complexity, we're talking about *additional space***, so we don't include space taken up by the inputs. For example, this function takes constant space even though the input has nn items:

Big O ignores constants, but **sometimes the constants matter**. If we have a script that takes 5 hours to run, an optimization that divides the runtime by 5 might not affect big O, but it still saves you 4 hours of waiting.