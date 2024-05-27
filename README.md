# `git-receive-mail`: The People's Git Email Patch Tool

This project attempts to make it _dead simple_ for _mere mortals_ to consume git
patch emails. It aims to be The People's git email patch tool.

Just run `git receive-mail`, pick the patches you want, and they are
automatically applied to the current branch.

![Demo of `git receive-mail`](git-receive-mail.gif)

Goals:

  * Ability to be used on pretty much any OS, so as to support the masses.
  * No dependencies on specific email workflows.
  * Simple to use in most cases, possible to use in all cases.

Non-Goals:

  * Make it really fast for maintainers of popular projects to consume vast
    numbers of patches. Other projects exist for that, such as [aerc](https://aerc-mail.org/)
    and [b4](https://github.com/mricon/b4) exist for that. This project is not
    for the Benevolent Dictators, but for The People.
  * Make it easy for patch submitters to participate on a mailing list. That is,
    this tool does not make it easy to reply to plain-text emails with plain
    text, something many email providers don't provide. However, there is hope!
    Users can use
    [`himalaya`](https://pimalaya.org/himalaya/cli/latest/usage/basic/message/send.html#reply-to-a-message-interactively)
    as a for-purpose tool to send plain text emails. This allows the users to
    use whatever they normally use to check email for everything else. Again,
    this is a tool for The People.

## Supported OS's

* Windows (via Git Bash)
* Mac
* Linux
* All other platforms that support golang, rust, and POSIX shell (since the
  project depends on `himalaya` and `fzf`, and this version is written in POSIX
  shell).

## Set-Up

1. Install [himalaya](https://github.com/soywod/himalaya.git). If you have Rust
   on your machine, this is just `cargo install himalaya`.
2. Set up `himalaya` with your IMAP credentials by running `himalaya`. You will
   be walked through it via a wizard.
2. Install [fzf](https://github.com/junegunn/fzf). This can typically be done
   with homebrew/scoop/your OS package manager.
4. Place the `git-receive-mail` included herein on your PATH.

## Usage

1. Check out the branch to which you wish to apply email patches sent via [`git
send-mail`](https://git-send-email.io).
2. Run `git receive-mail`.
3. Use the arrow keys to move around and the tab key to select/deselect patches.
4. Hit Enter.

The patches will be sorted lexicographically and applied in that order.
