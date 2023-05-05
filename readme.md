<h1 align="center">
  <a href="https://github.com/codustry/Emoji-Prefix"><img src="https://user-images.githubusercontent.com/960133/120058277-31849580-c063-11eb-80f7-d92ff54560d8.png" /></a>

`EMOJI-PREFIX`

</h1>

> An adaptation of [Emoji-Log](https://github.com/ahmadawais/Emoji-Log) by [Ahmad Awais](https://AhmadAwais.com/)

After utilizing Emoji-Log for several years, I've decided to modify it to better align with my mental model.

## What's Different?

1. change from `‼️` to `⚠️` since it is not working on Windows well.
2. remove the space between emoji and text `⚠️BREAK: remove function read_csv()`
3. new wording, prefer verb, short form, dev friendly word and start with unique charactor.
    1. 🌟ADD
    2. 💡IMPROVE
    3. 🐛FIX
    4. �NOTE
    5. 🤖TEST
    6. ⚠️BREAK
    7. 🚀RELEASE

4. Develop an automated tool to facilitate this process.

## Philosophy

A commit msg is a form of communication between devs(and him/herself). It conveys, group and stress what is happening.

1. **IMPERATIVE** ↓
    - Make your Git commit messages imperative.
    - Write a commit message like you're giving an order.
    - E.g., Use ✅ `Add` instead of ❌ `Added`.
    - E.g., Use ✅ `Create` instead of ❌ `Creating`.
1. **RULES** ↓
    - A small number of categories — easy to memorize.
    - Nothing more nothing less.
        1. 🌟ADD
        2. 💡IMPROVE
        3. 🐛FIX
        4. 📝NOTE
        5. 🤖TEST
        6. ⚠️BREAK
        7. 🚀RELEASE

1. **ACTIONS** ↓
    - Make git commits based on the actions you take.
    - Use a good editor like [VSCode](https://code.visualstudio.com/) to commit the right files with commit messages.

### GETTING STARTED

Only use the following Git Commit Messages. A simple and small footprint is critical here.

1. `🌟ADD: IMPERATIVE_MESSAGE_GOES_HERE`
    > Use when you add something entirely new.
    > E.g. `🌟ADD: Add Git ignore file`

1. `💡IMPROVE: IMPERATIVE_MESSAGE_GOES_HERE`
    > Use when you improve/enhance piece of code like refactoring etc.
    > E.g. `💡IMPROVE: Remote IP API Function`

1. `🐛FIX: IMPERATIVE_MESSAGE_GOES_HERE`
    > Use when you fix a bug — need I say more?
    > E.g. `🐛FIX: Case conversion`

1. `�NOTE: IMPERATIVE_MESSAGE_GOES_HERE`
    > Use when you add documentation like `README.md`, or even inline docs.
    > E.g. `�NOTE: API Interface Tutorial`

1. `🚀RELEASE: IMPERATIVE_MESSAGE_GOES_HERE`
    > Use when you release a new version.
    > E.g. `🚀RELEASE: Version 2.0.0`

1. `🤖TEST: IMPERATIVE_MESSAGE_GOES_HERE`
    > Use when it's related to testing.
    > E.g. `🤖TEST: Mock User Login/Logout`

1. `⚠️BREAK: IMPERATIVE_MESSAGE_GOES_HERE`
    > Use when releasing a change that breaks previous versions.
    > E.g. `⚠️BREAK: Change authentication protocol`

_— That's it for now. Nothing more nothing less._

<br>

![More](https://user-images.githubusercontent.com/960133/120058303-5547db80-c063-11eb-87ae-17f758a4e43b.png)

#### THE WORKFLOW & MEANINGS

I'd like to share what each of these emojis mean.

- `🌟ADD:` Emoji meaning: A "package emoji" — which can contain new stuff.
- `💡IMPROVE:` Emoji meaning: An "OK Hand emoji" — which is meant to appreciate an improvement.
- `🐛FIX:` Emoji meaning: A "bug emoji" — which means there was a bug that got fixed.
- `📝NOTE:` Emoji meaning: A "book emoji" — which means documentation or notes just like in a book.
- `🚀RELEASE:` Emoji meaning: A "rocket emoji" — which is meant to show a new release/launch.
- `🤖TEST:` Emoji meaning: A "robot emoji" — which says some test were run successfully.
- `⚠️BREAK:` Emoji meaning: A "bangbang emoji" — which attracts attention to a breaking change.

##### VSCode Extension

If you use VSCode, then I have built an extension [Emoji-Log for VSCode](https://marketplace.visualstudio.com/items?itemName=ahmadawais.emoji-log-vscode). This can help you write git commit messages quickly.

##### Bash/Zsh Workflow

For quick prototyping, I have made the following functions that you can add to your `.bashrc`/`.zshrc` files and use Emoji-Log quickly.

```sh
#.# Better Git Logs.
### Using EMOJI-LOG (https://github.com/ahmadawais/Emoji-Log).

# Git Commit, Add all and Push — in one step.
gcap() {
    git add . && git commit -m "$*" && git push
}

# NEW.
gnew() {
    gcap "🌟ADD: $@"
}

# IMPROVE.
gimp() {
    gcap "💡IMPROVE: $@"
}

# FIX.
gfix() {
    gcap "🐛FIX: $@"
}

# RELEASE.
grlz() {
    gcap "🚀RELEASE: $@"
}

# DOC.
gdoc() {
    gcap "📝NOTE: $@"
}

# TEST.
gtst() {
    gcap "🤖TEST: $@"
}

# BREAKING CHANGE.
gbrk() {
    gcap "⚠️BREAK: $@"
}
gtype() {
NORMAL='\033[0;39m'
GREEN='\033[0;32m'
echo "$GREEN gnew$NORMAL — 🌟ADD
$GREEN gimp$NORMAL — 💡IMPROVE
$GREEN gfix$NORMAL — 🐛FIX
$GREEN grlz$NORMAL — 🚀RELEASE
$GREEN gdoc$NORMAL — 📝NOTE
$GREEN gtst$NORMAL — 🧪️ TEST
$GREEN gbrk$NORMAL — ⚠️BREAK"
}
```

##### Fish Shell Workflow

To install these functions for the fish shell, run the following commands:

```sh
function gcap; git add .; and git commit -m "$argv"; and git push; end;
function gnew; gcap "🌟ADD: $argv"; end
function gimp; gcap "💡IMPROVE: $argv"; end;
function gfix; gcap "🐛FIX: $argv"; end;
function grlz; gcap "🚀RELEASE: $argv"; end;
function gdoc; gcap "📝NOTE: $argv"; end;
function gtst; gcap "🤖TEST: $argv"; end;
function gbrk; gcap "⚠️BREAK: $argv"; end;
funcsave gcap
funcsave gnew
funcsave gimp
funcsave gfix
funcsave grlz
funcsave gdoc
funcsave gtst
funcsave gbrk
```

##### Git Aliases

If you prefer, you can paste these aliases directly in your `~/.gitconfig` file:

```sh
# Make sure you're adding under the [alias] block.
[alias]
  # Git Commit, Add all and Push — in one step.
  cap = "!f() { git add .; git commit -m \"$@\"; git push; }; f"

  # NEW.
  new = "!f() { git cap \"🌟ADD: $@\"; }; f"
  # IMPROVE.
  imp = "!f() { git cap \"💡IMPROVE: $@\"; }; f"
  # FIX.
  fix = "!f() { git cap \"🐛FIX: $@\"; }; f"
  # RELEASE.
  rlz = "!f() { git cap \"🚀RELEASE: $@\"; }; f"
  # DOC.
  doc = "!f() { git cap \"📝NOTE: $@\"; }; f"
  # TEST.
  tst = "!f() { git cap \"🤖TEST: $@\"; }; f"
  # BREAKING CHANGE.
  brk = "!f() { git cap \"⚠️BREAK: $@\"; }; f"
```

<br>

![Using](https://user-images.githubusercontent.com/960133/120058311-61339d80-c063-11eb-9853-da0905b7c288.png)

### USING `EMOJI-LOG`

Here's a list of repos that make use of Emoji-Log.

- [Create-Guten-Block Toolkit →](https://github.com/ahmadawais/create-guten-block/commits/)
- [VSCode Shades of Purple Theme →](https://github.com/ahmadawais/shades-of-purple-vscode/commits/)
- [Ahmad Awais GitHub Repos →](https://github.com/ahmadawais) — _Latest repos on this account._
- [CaptainCore CLI (WordPress Management Toolkit) →](https://github.com/CaptainCore/captaincore-cli/commits/)
- [CaptainCore GUI (WordPress plugin) →](https://github.com/CaptainCore/captaincore-gui/commits/)
- **You?!** Add your repo to the list after adding the Emoji-log badge to your readme.

<br>

![AlfredSnippets](https://user-images.githubusercontent.com/960133/120058316-685aab80-c063-11eb-8bfd-cb0d4b3e34c2.png)

### Alfred Snippets

[Alfred](https://www.alfredapp.com/) [PowerPack](https://www.alfredapp.com/powerpack/) users can use the Snippets feature to quickly call Emoji-Log, or use the text expand feature for even quicker creation.

To setup:

1. Have Alfred 3 with PowerPack installed
2. For auto expansion, in _Alfred Settings » Features » Snippets_ ensure the "Automatically expand snippets by Keyword" box is checked
3. Download & open [`Emoji-Log.alfredsnippets`](Emoji-Log.alfredsnippets), deselecting "Strip snippets of 'auto expand' flag" when prompted

This will give the following text expander keywords for the Emoji-Log:

| Keyword |   Snippet    |
| ------- | ------------ |
| `;gnew` | 🌟ADD:      |
| `;gimp` | 💡IMPROVE:  |
| `;gfix` | 🐛FIX:      |
| `;grlz` | 🚀RELEASE:  |
| `;gdoc` | 📝NOTE:      |
| `;gtst` | 🤖TEST:     |
| `;gbrk` | ⚠️BREAK:  |

To edit the `;` prefix to your preferred expansion flag, double click right click the Emoji-Log Collection in _Alfred Settings » Features » Snippets_.

> TextExpander Snippets are also available. Download & open [`Emoji-Log.textexpander`](Emoji-Log.textexpander) to import.

<br>

![badge](https://user-images.githubusercontent.com/960133/120058320-6ee92300-c063-11eb-834c-20463fdfb0dd.png)

### `EMOJI-LOG` BADGE COLLECTION

If your repo uses `EMOJI-LOG` then you can add any of the following badges to your read me and send me a PR to list your repo here.

<br>

![emoji-log](https://cdn.rawgit.com/ahmadawais/stuff/ca97874/emoji-log/flat.svg)

- **STYLE**: Flat Square
- **MARKDOWN** ↓

```markdown
[![emoji-log](https://cdn.rawgit.com/ahmadawais/stuff/ca97874/emoji-log/flat.svg)](https://github.com/ahmadawais/Emoji-Log/)
```

- **HTML** ↓

```html
<a href="https://github.com/ahmadawais/Emoji-Log/"><img alt="emoji-log" src="https://cdn.rawgit.com/ahmadawais/stuff/ca97874/emoji-log/flat.svg" /></a>
```

<br>

![emoji-log](https://cdn.rawgit.com/ahmadawais/stuff/ca97874/emoji-log/flat-round.svg)

- **STYLE**: Flat Rounded
- **MARKDOWN** ↓

```markdown
[![emoji-log](https://cdn.rawgit.com/ahmadawais/stuff/ca97874/emoji-log/flat-round.svg)](https://github.com/ahmadawais/Emoji-Log/)
```

- **HTML** ↓

```html
<a href="https://github.com/ahmadawais/Emoji-Log/"><img alt="emoji-log" src="https://cdn.rawgit.com/ahmadawais/stuff/ca97874/emoji-log/flat-round.svg" /></a>
```

<br>

![emoji-log](https://cdn.rawgit.com/ahmadawais/stuff/ca97874/emoji-log/non-flat-round.svg)

- **STYLE**: Non-flat Rounded
- **MARKDOWN** ↓

```markdown
[![emoji-log](https://cdn.rawgit.com/ahmadawais/stuff/ca97874/emoji-log/non-flat-round.svg)](https://github.com/ahmadawais/Emoji-Log/)
```

