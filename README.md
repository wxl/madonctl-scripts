Introduction
============

This repo consists of `bash` scripts (et cetera) for use with [`madonctl`][1], the best solution for command line usage of [Mastodon][4] available, in my honest opinion.

Don't expect heavily polished stuff here. I generally make things as I go. `madonctl` is meant to be easily scriptable, which lends itself well to quick solutions.

Also, I'm working on a set of templates tweaked to my liking. I usually `madonctl stream` in one [`tmux`][2] pane, `madonctl stream local` in another, and then `madonctl stream --notifications-only --notification-types=mentions` in a 3rd. Using a fair amount of real estate, I like to keep things simple.

Scripts
=======

 * **`toot [ dm`*****`| status-id | URL`*****`]`** has 3 forms, all of which take input from stdin:
   1. **`toot dm`** creates a direct message. don't forget to include the mention.
   1. **`toot`*****`status-id | URL`*** will reply with appropriate visibility and mentions.
   1. **`toot`** will create a new toot.
 * **`untoot`*****`status-id | URL`*** deletes toots.
 * **`mytoots`** shows recent mentions.
 * **`follows`** deals with follow requests. For each, you can accept/deny and assuming the former, follow back if you like.
 * **`follow`*****`status-id | user-id`*** follows a user.
 * **`boost`*****`status-id | URL`*** just boosts. 
 * **`favboost`*****`status-id | URL`*** boosts and favorites. I pretty much never just favorite something, so that's not included.

Templates
=========

 * **mynotifications.tmpl** to use with `--template-file` for notifications.
   ![pic of mynotifications.tmpl in action](https://raw.githubusercontent.com/wxl/madonctl-scripts/master/assets/images/mynotifications.png "direct, sensitive toot with content warning")
   * Bell at the beginning, which `tmux` makes visual.
   * Trimmed down to remove anything except stuff relevant to mentions. I don't care being notified about reblogs or favorites (but thank you for them!), so none of that is there.
   * Emojis for `sensitive: true` and `visibility: direct`
   * No names, no attachment links. 
   * As little as 2 lines (default can be up to 10 times that):
     1. status-id (reply-to-id as relevant), account and id, link to status
     2. spoiler (if available) followed by message.

Support
=======

Further questions and comments may be addressed to [@wxl@soc.ialis.me][3] 

Shout outs
==========

 * Super big thank yous to [@McKael@mamot.fr][7] for not only creating [`madonctl`][1] but for being so darn responsive to my many questions and suggestions. Someone give this guy a raise!
 * A special thank you to [@redwolf@masto.io][5] for the lovely example toot to show off my notifications template. It does seem to suggest that he (and/or me) is a perv, but in fact, it was a lovely picture of [mating iguanas][6]. Of course, he still *might* be a perv, but…

[1]: https://github.com/McKael/madonctl
[2]: https://github.com/tmux/tmux
[3]: https://soc.ialis.me/@wxl
[4]: https://github.com/tootsuite/mastodon
[5]: https://masto.io/@redwolf
[6]: https://pictor.ialis.me/media_attachments/files/000/218/734/original/79069ce1b3ea6da5.jpg
[7]: https://mamot.fr/@McKael
