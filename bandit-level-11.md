# Bandit Level 11: ROT13

**Status:** Completed.

**Idea:** ROT13 shifts every letter 13 places along the alphabet. Because the alphabet has 26 letters, doing it twice gets the original back, so one operation both scrambles and unscrambles.

- **Goal:** decode a file where every letter was rotated by 13.
- **What I tried first:** the Base64 decoder from Level 10. It said "invalid input", which told me this file used a different disguise.
- **What I learned:** each level can use a different encoding, so a failed decode is useful information. The `tr` command swaps characters one-to-one, and its second set must be the same length as the first, which I missed the first time.
