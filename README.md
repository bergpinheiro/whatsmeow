# whatsmeow
[![Go Reference](https://pkg.go.dev/badge/go.mau.fi/whatsmeow.svg)](https://pkg.go.dev/go.mau.fi/whatsmeow)

whatsmeow is a Go library for the WhatsApp web multidevice API.

> **About this fork** — whatsmeow is created and maintained by
> [Tulir Asokan](https://github.com/tulir) ([upstream](https://github.com/tulir/whatsmeow), MPL-2.0).
> This fork carries a few patches ahead of / diverging from upstream, used by the
> [bergpinheiro/gows](https://github.com/bergpinheiro/gows) engine builds:
> passkey (WebAuthn) pairing (upstream PR#1186), the 463-LID history-sync privacy-token fix,
> and `call: don't attach tctoken to call rejects` (a stored caller privacy token attached to
> `<call><reject>` makes the server silently drop the stanza). All credit for the library
> belongs to upstream.

## Discussion
Matrix room: [#whatsmeow:maunium.net](https://matrix.to/#/#whatsmeow:maunium.net)

For questions about the WhatsApp protocol (like how to send a specific type of
message), you can also use the [WhatsApp protocol Q&A] section on GitHub
discussions.

[WhatsApp protocol Q&A]: https://github.com/tulir/whatsmeow/discussions/categories/whatsapp-protocol-q-a

## Usage
The [godoc](https://pkg.go.dev/go.mau.fi/whatsmeow) includes docs for all methods and event types.
There's also a [simple example](https://pkg.go.dev/go.mau.fi/whatsmeow#example-package) at the top.

## Features
Most core features are already present:

* Sending messages to private chats and groups (both text and media)
* Receiving all messages
* Managing groups and receiving group change events
* Joining via invite messages, using and creating invite links
* Sending and receiving typing notifications
* Sending and receiving delivery and read receipts
* Reading and writing app state (contact list, chat pin/mute status, etc)
* Sending and handling retry receipts if message decryption fails
* Sending status messages (experimental, may not work for large contact lists)

Things that are not yet implemented:

* Sending broadcast list messages (this is not supported on WhatsApp web either)
* Calls
