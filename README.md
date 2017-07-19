A series of `bash` scripts for use with `[madonctl][1]`, the best solution for command line usage of Mastodon available, in my honest opinion.

Don't expect heavily polished stuff here. I generally make things as I go. `madonctl` is meant to be easily scriptable, which lends itself well to quick solutions.

Here's what you'll find:

 * `toot` will either take toot, create a direct message with the `dm` argument, or reply to a toot using appropriate visibility and including appropriate mentions by using the status id. All input from stdin, please.
 * `mytoots` will show recent mentions.
 * `follows` looks for follow requests and allows the option of accepting as well as following back.
 * `favboost` takes status id and both favorites and boosts it.
 * `boost` takes status id and boosts it. I pretty much never just favorite something, so that's not included.

[1]: https://github.com/McKael/madonctl
