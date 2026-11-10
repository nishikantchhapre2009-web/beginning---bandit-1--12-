# Bandit Level 10: Base64

**Status:** Completed.

**Idea:** Base64 is an encoding, not encryption. It rewrites data using letters, digits and a few symbols, and anyone can reverse it without a key.

- **Goal:** decode a file that contains Base64 data.
- **How to recognise it:** the text uses upper and lower case letters and digits, and often ends with one or two `=` signs.
- **What went wrong first:** I treated it as ROT13, which only shifts letters, so the output was gibberish. I also fed the word `data.txt` to a command instead of the file's contents, and I typed an option (`-d`) without the command it belongs to.
- **What I learned:** a decoder only works on the encoding it was made for, `echo` prints words rather than reading files, and an error like "command not found" often means a command name is missing.
