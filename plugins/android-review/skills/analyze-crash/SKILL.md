---
description: Analyze an Android crash stack trace and identify likely root cause, affected lifecycle path and practical Kotlin fixes
disable-model-invocation: true
---

Analyze the provided Android crash, ANR snippet or logcat output as a senior Android production-debugging engineer.

## Method
1. Find the deepest meaningful `Caused by` exception; do not treat wrapper exceptions such as `Unable to stop activity` or `Failed to call observer method` as the root cause.
2. Map the stack to Android lifecycle timing, framework/SDK ownership and likely application trigger.
3. Separate confirmed facts from hypotheses.
4. Search project code for relevant usage only when project access is available.
5. Recommend minimal safe fixes and diagnostic logging.

## Special attention
- Activity/Fragment lifecycle and view lifecycle.
- Glide, Coil, Picasso, RecyclerView, ViewPager2 and image lifecycle.
- Firebase/Braze/AppsFlyer registration or callback issues.
- Receivers, observers, network callbacks, dialogs, services and handler leaks.
- Android OS/API-version-specific behavior.

## Output format

# Crash Diagnosis
- Root exception:
- Crashing lifecycle phase:
- Owning library/module:
- Most likely trigger:
- Confidence:

# Evidence From Stack
Explain the stack path concisely.

# Recommended Fixes
List fixes in implementation order and include Kotlin examples where appropriate.

# What to Collect Next
State only the missing log/code needed to confirm remaining uncertainty.
