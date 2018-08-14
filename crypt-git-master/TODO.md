- It is important to do `cg pull` after every `cg push` if you want to continue working remotely, because after long time span you may forget to perform `cg pull` (i.e. decrypting of your important files) and you may perform `cg push` again(which will lead in change of iv) which will cause problem in decryption of files because the iv will get replaced by a new random 16 bytes. Automating it is not a big deal and this will be taken care in next release.

- When you do `cg push`, all the files are encrypted again with the newly generated 'iv' which leads changes in all the encrypted files. Thus while commiting them the unchanged files also get added. So this creates improper commit history on git.