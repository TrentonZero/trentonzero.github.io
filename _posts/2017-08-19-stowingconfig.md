---
    layout: post
    category: Personal
    tagline: "Using GNU Stow"
    title: Linux and MacOS Configuration Syncing
    tags: [computer, stow, gnu, open source, linux]
    image: /assets/images/gnu.png
    customimagestyle: "box-shadow:0 0 0"
---

The weekend is here and I am anxious to go and organize all my system configurations using GNU Stow.

Incidentally, anyone else had that moment where you realized that you had a problem, and wondered what you could contrive to solve it. Then figured out that the GNU project solved this problem almost twenty years ago? That the solution is free and, truth be told, works pretty well? Yeah, that's me right now. That's me a lot actually.

<!-- more -->

GNU Stow starts as the solution to a different problem: in a typical Linux install, user application files are all thrown in a giant heap in a single directory (typically /usr/ or /usr/local). Making things worse is that they then create the same subpaths within those directories (typicaly things like /usr/bin and /usr/lib, for the executables and the libraries, respectively). And that makes keeping track of what's installed a royal pain.

All sorts of technologies have been invented in Linux land in order to make this somehow managable. GNU Stow was intended to allow users to create "packages" of applications wherever they liked on the system, and stow would maintain symlinks in, say, /usr/bin and /usr/lib. That way, a user who wanted to, say, try out different versions of the same application could simple stow away one version and put another in its place, without worrying that they would be losing anything.

Better techniques have come about for handling much of this, but GNU Stow is a life saver for a slightly different, but related problem. Linux evolved around a standard where user-specific configuration files would all be dropped directly into the user's home directory. That's...a mess, and it makes it very difficult to share configuration files across multiple computers (say, your workstation and your laptop) without also sharing your Pictures, movies, music, and other things that you may not want syncing across all your computers. My workstation has four terabytes of storage. My little Dell Ultrabook just has 225 GB SSD. And as tempting as it is to synchronize private RSA and GPG keys through a public cloud service (like Github)...yeah, no. I don't think it matters if someone sees my vimrc file or my emacs.d directory, but my RSA keys? No and no and no.

With GNU Stow, the files you want to synchronize, and only those files, you stow in a "dotfiles" directory, in sensible packages. Those you synchronize via a third-party cloud service. And, wowza, when you are headed on your business trip, or have already left, and you suddenly realize that some configuration option you like has been left behind, you just need to do a "git pull" from Github and a fast "stow -t ~ vim" and you are all set to resume with all your existing settings. 
