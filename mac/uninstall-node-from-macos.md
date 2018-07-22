# How to uninstall Node.js from macOS 
Every time I started Visual Studio Code and opened the integrated terminal, I got this annoying message saying:

```
nvm is not compatible with the npm config "prefix" option: currently set to "/usr/local"
Run `npm config delete prefix` or `nvm use --delete-prefix v8.9.1 --silent` to unset it 
```

Description of the problem over here: [Integrated Terminal in Visual Studio Code](https://code.visualstudio.com/docs/editor/integrated-terminal)
It also started the terminal with an older Node.js version (`v6.9.5`), which wasn’t installed with NVM. It was time to dig into it and remove this version completely. 

Turned out that I installed Yarn with Homebrew without the `--without-node` flag which also installed a Node.js version, and that there where some shady node directories in `usr/local/*`. Removing them with instructions from these two sources solved it:
[javascript - How do I completely uninstall Node.js, and reinstall from beginning (Mac OS X) - Stack Overflow](https://stackoverflow.com/questions/11177954/how-do-i-completely-uninstall-node-js-and-reinstall-from-beginning-mac-os-x)
[How to Uninstall Node.js from Mac OSX](http://stackabuse.com/how-to-uninstall-node-js-from-mac-osx/)