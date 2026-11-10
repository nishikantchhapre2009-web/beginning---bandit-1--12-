# Bandit Level 12: hex dump and layered compression

**Status:** In progress. This level is hard for me, and I am still working through the first part.

**Idea:** the file is a hex dump of a file that was compressed several times, like nesting dolls. You rebuild it, then open one layer at a time.

- **Goal:** rebuild the original file and keep unpacking it until readable text appears.
- **Clues I spotted:** a hex dump starting `1f8b` marks gzip, and the text `BZh` marks bzip2. A filename stored inside the data (like `data2.bin`) also hints at the layers.
- **Tools I learned:** `xxd -r` to reverse a hex dump, `file` to identify each layer, `gzip`, `bzip2` and `tar` to unpack them, `mv` to rename when a tool wants a certain ending, and `mktemp -d` for a scratch folder, since the home folder is read-only.
- **Shortcuts I tried:** `zcat` and `bzcat` read compressed data straight from a pipe, so the renaming step disappears.
- **Where I am:** I reached the final gzip layer, then the connection dropped and my scratch folder was cleaned up. I still need to redo the chain and read the last layer.
- **What I learned:** run `file` before `cat` on unknown data, work in a scratch folder, and read each error message before changing anything.
