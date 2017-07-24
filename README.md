A series of `bash` scripts (et cetera) for use with [`madonctl`][1], the best solution for command line usage of Mastodon available, in my honest opinion.

Don't expect heavily polished stuff here. I generally make things as I go. `madonctl` is meant to be easily scriptable, which lends itself well to quick solutions.

Here's what you'll find:

 * `toot` will either take toot, create a direct message with the `dm` argument, or reply to a toot using appropriate visibility and including appropriate mentions by using the status id. All input from stdin, please.
 * `untoot` will take a status-id and delete it.
 * `mytoots` will show recent mentions.
 * `follows` looks for follow requests and allows the option of accepting as well as following back.
 * `follow` will take a user-id or account-id and follow that user.
 * `favboost` takes status id and both favorites and boosts it.
 * `boost` takes status id and boosts it. I pretty much never just favorite something, so that's not included.

Also, I'm working on a set of templates tweaked to my liking. I usually `madonctl stream` in one [`tmux`][2] pane, `madonctl stream local` in another, and then `madonctl stream --notifications-only --notification-types=mentions` in a 3rd. Using a fair amount of real estate, I like to keep things simple. That said, here's what we've got so far:

 * mynotifications.tmpl to use with `--template-file` for notifications. Included a bell at the beginning, which `tmux` makes visual. You'll notice it's trimmed down to remove anything except stuff relevant to mentions. I don't care being notified about reblogs or favorites (but thank you for them!), so none of that is there. Emojis for `sensitive: true` and `visibility: direct`, no names, no attachment links. Leads with status id (reply to id as relevant), account and id, link to status, then spoiler (if available) followed by message. 

Further questions and comments may be addressed to [@wxl@soc.ialis.me][3] 

[1]: https://github.com/McKael/madonctl
[2]: https://github.com/tmux/tmux
[3]: https://soc.ialis.me/@wxl
