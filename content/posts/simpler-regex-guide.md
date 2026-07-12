---
title: "Simpler Regex Guide"
date: 2022-12-12T19:44:55+05:30
description: "An attempt to make regex remember me"
tags:
  - regex
  - ide
---

Did you ever find yourself repeating keystrokes when editing a long list of words, for example you want to replace that semicolon `;` with a colon `:`
And you think there should be a cooler way to do that OR you know the way but you never remember the old fabled regex when needed.
Here is a list of simple regex example that you can easily tweak to get things done faster.

<!--more-->

Why you should know this?
Most IDEs support find and replace with regex support and you will be surprised how easy this makes those tasks. Some basics first.

Using the tools

1. Find and replace
   1. Using IDE Find & Replace with regex

      ![VS Code find and replace](/images/vscode_find_replace.gif)

   2. Vim Substitue `:help substitue`

      ![Vim substitute](/images/vim_substitute.gif)

   3. Sed [gnu sed manual](https://www.gnu.org/software/sed/manual/sed.html)

      ```bash
      ✗ echo "hello world?" | sed 's/?/!/g'
      hello world!
      ```

2. Regex matching.

   Learn Regex pattern matching from web.

   I'll leave this link here for quick ref [regular-expression-language-quick-reference](https://learn.microsoft.com/en-us/dotnet/standard/base-types/regular-expression-language-quick-reference)

3. Capture Groups

   [Google Search](https://www.google.com/search?q=find+and+replace+capture+groups&oq=find+and+replace+capture+groups)
