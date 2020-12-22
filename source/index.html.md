---
title: Relay Chat Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - javascript

toc_footers:
  - <a href='/'>Back to main website</a>

# includes:
#   - errors

search: true

code_clipboard: true
---

# Introduction

Welcome to Relay, the future of website communities! Relay adds live chat to any website with just a script tag. It creates a chatroom unique to each pathname on which the script tag is loaded. Everyone who visits that page will have access to the same live chat. Relay comes with threads, mentions, emoji reactions, admin tools, push notifications, and more. Best of all, it's completely free.

This documentation outlines how to add the Relay script tag to your website and explains how to become an admin and leverage our admin tools. If you run into any problems, feel free to click the Relay button in the bottom right to chat with us and other visitors of our documentation.

# Installation

> When you've added the Relay script tag, you can access the global relay object:

```javascript
typeof window.relay; // => "object"

// check if Relay has been initialized
relay.initialized; // => true

// minimize Relay programmatically
if (relay.minimized) {
  relay.minimize();
}

// unminimize Relay programmatically
if (!relay.minimized) {
  relay.unminimize();
}

// directly access Relay's button and container (an iframe)
relay.button; // => button#relay-btn
relay.container; // => iframe#relay-iframe
```

Add this script tag to the `head` of any pages where you'd like to enable Relay: `<script src="https://chat.relaychat.app"></script>`. Voila! You have your own chat community.

The Relay script tag adds a global object `relay` to your webpage. You can use it to programmatically minimize and expand Relay. Normally, the user would click the Relay button to open the chat. You may also check whether Relay has been initialized and can even access Relay's DOM elements.

# Overriding the Chat Channel's Location

By default, Relay creates a chatroom specific to each pathname (e.g., relaychat.app, relaychat.app/docs). In order to override the location of the chatroom, you can add a `path` query string value to the script tag. **This path must be a valid pathname. In other words, your domain + the value of path must be a valid URL.**

```html
<!-- for every page with this script tag, the chatroom will simply be relaychat.app -->
<script src="https://chat.relaychat.app?path="></script>

<!-- for every page with this script tag, the chatroom will be relaychat.app/isnt-this-chat-awesome -->
<script src="https://chat.relaychat.app?path=/isnt-this-chat-awesome"></script>
```

# Other Configuration Options (Color and Position)

By adding query string parameters to the script tag, you can change the color of the button as well as its position:

- `button_color`: this value must be hexcode **without the #**;
- `position`: this value must be `left` or `right` (the default);
- `button_bottom`: this value must be a valid value for the CSS bottom property, e.g., `20px` or `10vh`.

```html
<!-- the button will be white -->
<script src="https://chat.relaychat.app?button_color=ffffff"></script>

<!-- the button and chat will be on the left-->
<script src="https://chat.relaychat.app?position=left"></script>

<!-- the button will be 50px up from the bottom and on the left-->
<script src="https://chat.relaychat.app?position=left&button_bottom=50px"></script>
```

# Admin

## How to Become an Admin

To become an admin of your website you simply need to:

1. sign up for Relay (within the chat app itself) using an email with the same domain as your website;
2. confirm your email.

## Admin Tools

After you've become an admin, you'll automatically see an admin option in your Relay nav. You'll also have the option to moderate any message within the standard chat interface.

Within the admin page, we've collected a queue of messages to be moderated as well as a log of any moderation actions you or the automoderator have taken. The messages in your queue have been flagged by your users as inappropriate. We use an automoderator powered by artificial intelligence, but some unsuitable messages might still slip through. As a moderator, you may:

1. delete a message;
2. delete all messages by a given user;
3. ban a user.

All of these moderation actions are reversible from the moderation action log.

In addition to moderation tools, you can:

1. pin a message to all the chatrooms in your domain;
2. change the background color of the Relay button.

We're always building more admin tools, so if you have any special requests, please let us know at hello@relaychat.app or chat with us using Relay on this website.
