---
layout: post
title: Using emoji to identify your iTerm tabs
excerpt: "How to use emoji to identify your iTerm tabs"
categories: articles
tags: [iterm, emoji, ohmyzsh, zsh, tab titles]
comments: true
share: true
---

I have a thing for colorful terminals. <examples>. 

I've been getting annoyed by the sheer number of open tabs on my terminal and how I have to cycle through them at least once to find one that I want. So I decided to display a random emoji in every tab title to visually remember which ones which.

This is how it looks now:
<figure>
  <img src="/images/emoji-tab-iterm.png">
</figure>


To achieve similar results add the following to the bottom of your `.zshrc`:   

{% highlight bash %}
emoji=("💩 " "👼 " "💋 " "🌺 " "♻️ " "🔞 " "👠 " "💾 " "🇮🇳 " "⛵️ " "🚀 " "🎄 " "🎃 " "🍺 " "🐙 ")
((TAB_TITLE_EMOJI_INDEX=$RANDOM%$#emoji+1))

precmd() {
	echo -ne "\e]1;$emoji[$TAB_TITLE_EMOJI_INDEX] ${PWD##*/}\a"
}
{% endhighlight %}

The snippet above is creating an array `emoji` with all the possible selections for your random emoji. You can edit this line and add your own emoji. On OSX Yosemite, you can press `Ctrl + Command + Space` to choose which ones you want.

The `TAB_TITLE_EMOJI_INDEX` variable is initialized to a random number for every new session and we use this to retrieve an emoji from our list. The `precmd` method is called before running any command on the terminal. I use this because I want to display the current directory in the title as well. If you only want to display the emoji, you can replace the entire `precmd` block with just this:

{% highlight bash %}
echo -ne "\e]1;$emoji[$TAB_TITLE_EMOJI_INDEX]\a"
{% endhighlight %}


If you are using [Oh My Zsh](http://ohmyz.sh/) you may also need to disable the auto title setting in your `.zshrc`:

{% highlight bash %}
# Uncomment the following line to disable auto-setting terminal title.
DISABLE_AUTO_TITLE="true"
{% endhighlight %}


