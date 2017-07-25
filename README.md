Introduction
============

This repo consists of `bash` scripts (et cetera) for use with [`madonctl`][1], the best solution for command line usage of [Mastodon][4] available, in my honest opinion.

Don't expect heavily polished stuff here. I generally make things as I go. `madonctl` is meant to be easily scriptable, which lends itself well to quick solutions.

Also, I'm working on a set of templates tweaked to my liking. I usually `madonctl stream` in one [`tmux`][2] pane, `madonctl stream local` in another, and then `madonctl stream --notifications-only --notification-types=mentions` in a 3rd. Using a fair amount of real estate, I like to keep things simple.

Scripts
=======

 * `toot` will either toot, create a direct message with the `dm` argument, or reply to a toot using appropriate visibility and including appropriate mentions by using the status id or URL. All input from stdin, please.
 * `untoot` will take a status-id and delete it.
 * `mytoots` will show recent mentions.
 * `follows` looks for follow requests and allows the option of accepting as well as following back.
 * `follow` will take a user-id or account-id and follow that user.
 * `favboost` takes status id or URL and both favorites and boosts it.
 * `boost` takes status id or URL and boosts it. I pretty much never just favorite something, so that's not included.

Templates
=========

 * mynotifications.tmpl to use with `--template-file` for notifications. Included a bell at the beginning, which `tmux` makes visual. You'll notice it's trimmed down to remove anything except stuff relevant to mentions. I don't care being notified about reblogs or favorites (but thank you for them!), so none of that is there. Emojis for `sensitive: true` and `visibility: direct`, no names, no attachment links. Leads with status id (reply to id as relevant), account and id, link to status, then spoiler (if available) followed by message.

![pic of mynotifications.tmpl in action](https://raw.githubusercontent.com/wxl/madonctl-scripts/master/assets/mynotifications.png "direct, sensitive toot with content warning")

Support
=======

Further questions and comments may be addressed to [@wxl@soc.ialis.me][3] 

Shout outs
==========

A special thank you to [@redwolf@masto.io][5] for the lovely example toot to show off my notifications template. It does seem to suggest that he (and/or me) is a perv, but in fact, it was a lovely picture of [mating iguanas][6]. Of course, he still *might* be a perv, but…

[1]: https://github.com/McKael/madonctl
[2]: https://github.com/tmux/tmux
[3]: https://soc.ialis.me/@wxl
[4]: https://github.com/tootsuite/mastodon
[5]: https://masto.io/@redwolf
[6]: https://pictor.ialis.me/media_attachments/files/000/218/734/original/79069ce1b3ea6da5.jpg
