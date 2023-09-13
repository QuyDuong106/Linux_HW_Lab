# Using tab completion and the command history

## 3.1. Scrolling through your command history
At the command prompt, simply hit the Up Arrow and Down Arrow keys, ↑ and ↓, to scroll through your command history.

## 3.2. Using tab completion
Type cd /bi and press the Tab key. As you might expect, the command autocompletes to cd /bin. But what happens if you just type cd /b and press Tab?
```
theia@theia-quyduong106:/home/project$ cd /b
```

In this case, nothing happens. But if you hit Tab a second time, you'll see a list of all the valid candidates for autocompletion, namely bin/ and boot/.

Notice that cd /b reappears in the command prompt. You cannot use tab completion while there are multiple valid candidates for autocompletion. To narrow down your choices, add an i at the end of your line, then press Tab again. This time the prompt will fill with cd /bin, the only valid option remaining.

Tip: Tab completion only works when there is one valid candidate for autocompletion. When there are multiple possible options, the command prompt will prompt you to enter more letters until there is only one possible option.

You can even use tab completion repeatedly to "dig into" a directory tree.

Let's say you have used tab completion to get to the point where ls /home is displayed at the command prompt. You can press Tab twice to get a listing of all the directories under /home. As you did with cd /bin, use tab completion to complete the address of a subdirectory such as ls /home/theia. You can repeat this process as many times as you like until you reach the end of a chosen path.