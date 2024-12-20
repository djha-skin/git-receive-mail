# `git-receive-mail`: The People's Git Email Patch Tool

This project attempts to make it _dead simple_ for _mere mortals_ to consume git
patch emails. It aims to be The People's git email patch tool.

Just run `git receive-mail`, pick the patches you want, and they are
automatically applied to the current branch.

![Demo of `git receive-mail`](git-receive-mail.gif)

Feature requests and bug reports are welcome!

## Usage

1. Check out the branch to which you wish to apply email patches sent via [`git
send-mail`](https://git-send-email.io).
2. Navigate to your git repository and branch in the terminal.
2. Run `git receive-mail`.
3. Use the arrow keys to move around and the tab key to select/deselect patches.
4. Hit Enter.

The patches in the emails will be applied to the currently checked out git
branch.

# Goals and Non-Goals

**Goals**:

  * Support the masses.
      * Usable on pretty much any OS.
      * Permissively licensed (MIT).
  * No dependencies on specific email workflows.
  * Simple to use in most cases, possible to use in all cases.

**Non-Goals**:

  * The ability for maintainers of popular projects to consume vast
    numbers of patches. Other projects exist for that, such as [aerc](https://aerc-mail.org/)
    and [b4](https://github.com/mricon/b4).
  * The ability for patch submitters to participate on a mailing list. That is,
    this tool does not make it easy to reply to plain-text emails with plain
    text, something [many email providers don't
    provide](https://www.kernel.org/doc/html/v4.10/process/email-clients.html).
    However, there is hope! Users can use
    [`himalaya`](https://pimalaya.org/himalaya/cli/latest/usage/basic/message/send.html#reply-to-a-message-interactively)
    as a for-purpose tool to send plain text emails. This allows the users to
    use whatever they normally use to check email for everything else.

## Supported OS's

* Windows (via Git Bash)
* Mac
* Linux
* All other platforms that support Golang, Rust, and POSIX shell (since the
  project depends on `himalaya` and `fzf`, and this version is written in POSIX
  shell).

## Set-Up

1. Install [himalaya](https://github.com/soywod/himalaya.git). It can be
   downloaded from its releases page. Often, this can simply be installed with
   your favorite package manager, either the system package manager or e.g.
   homebrew.
2. Set up `himalaya` with your IMAP credentials by running `himalaya`. A wizard
   will walk the user through setting this up.
2. Install [fzf](https://github.com/junegunn/fzf). It can be downloaded from its
   releases page. Often, this can simply be installed with your favorite package
   manager, either the system package manager or e.g. homebrew.
4. Download the `git-receive-mail` script included herein and put it on on the
   PATH.

## Advanced Usage

The script passes whatever arguments sent to it into Himalaya, so reading the
[documentation](https://pimalaya.org/himalaya/cli/latest/configuration/) for
that tool will enable the user to construct more advanced workflows, grab
patches from folders other than their INBOX, etc. For example, `git receive-mail
-a <account>` lets the user grab the email from a specific email account.

## Contributions

Contributions welcome. I don't expect this to remain a POSIX script; I'm open to
PRs or patches that rewrites this simple script. Future directions might include
getting rid of dependencies or rewriting entirely in golang or Python.
