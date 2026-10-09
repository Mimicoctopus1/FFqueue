# FFqueue
These scripts are designed to allow the queueing of files to be played by FFplay (from FFmpeg), but they can be easily modified to work with other programs which don't support queueing natively. To use it, navigate to the parent directory of your files in **two** shells. With one, run
```bash
ffqueued
```
This starts a daemon which will read the file `.queue`, checking for filenames listed in it. You can specify a different queue file like this:
```bash
ffqueued queue-file.txt
```
If it detects that the queue file contains a filename, it will try to play the specified file. Otherwise, it waits five seconds before trying again to save resources. If it plays the file, it will remove that line from the file. It reads the lines from top to bottom. Now, the reason you needed two shells is because, unless you already have a queue file, you will want to be able to edit it while `ffqueued` is running in the other shell. Run
```bash
ffqueue
```
to start. If you specified a non-default queue file with `ffqueued`, you will need to do the same thing here. From the `ffqueue` TUI, you can use commands to view and edit the queue. Run `help` to see these commands. Note that, to use the `add` utility, you will need the `fzf` program.
