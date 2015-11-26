---
layout: post
title: Binding return in vim for instant feedback
---

Let me share with you my favorite line of my `.vimrc`. This is my secret
sauce. It has honestly changed the way I think, and it is the main
reason why SublimeText or Atom will just never be good enough for me.

```
nnoremap c<cr> :nmap <c-v><cr> :wa\\|<c-v><cr><left>
```

This is a keybinding for `c->return`. I use it to bind a command to
return. I've ingrained in myself that you smash the enter key to get
feedback. Writing this post, I've bound enter to `jekyll build`, reload
chrome, and bring it to the foreground. When I'm writing ruby or
javascript, it will run my specs. If I'm editing html or css, it will
reload the browser.

I even have keybindings to set up the most common return bindings!
`<leader>blog` binds the `jekyll build` process I mentioned.
`<leader>tr` runs my ruby specs (**t**est **r**uby). And I add new ones
all the time, whenever it makes sense.

I took this technique from [Gary Bernhardt][@garybernhardt], while
watching his amazing series of screencasts on software development,
[Destroy All Software][DAS]. I highly recommend it.

<figure>
  <img title="instant spec feedback" alt="instant spec feedback" src="/img/vim_instant_feedback.gif">
  <figcaption><em>Go go gadget rspec!</em></figcaption>
</figure>


[@garybernhardt]: https://twitter.com/garybernhardt
[DAS]: https://www.destroyallsoftware.com/screencasts
