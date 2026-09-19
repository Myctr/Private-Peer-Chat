# Private Peer Chat

A lightweight, browser-based peer-to-peer chat application built with vanilla HTML, CSS, JavaScript, and [PeerJS](https://peerjs.com/).

Create a chat room, share its peer ID, and start a direct conversation without creating an account or maintaining a central application server.

> **Security note:** This project currently applies a custom Affine cipher to supported message characters before sending them over the PeerJS connection. It is an educational demonstration, not production-grade end-to-end encryption. Do not use it for sensitive or confidential communication.

## Features

- Peer-to-peer connections through PeerJS
- Room creation with a shareable peer ID
- Direct chat joining with a peer ID
- Message history displayed in the current browser session
- Enter-key support for sending messages
- Responsive interface for desktop and mobile screens
- No account or application database required

## How it works

1. Open the application and choose **Create a chat**.
2. Share the generated peer ID with the person you want to chat with.
3. The other person chooses **Join a chat**, enters the peer ID, and selects **Connect**.
4. Once connected, both participants can send messages directly through the PeerJS data connection.
5. Click an encoded message to decode it in the interface.

## Run locally

This is a static web application. Serve the project directory with any local HTTP server:

```bash
git clone https://github.com/Myctr/Responsible-Encrypted-Chat-Application.git
cd Responsible-Encrypted-Chat-Application
python3 -m http.server 8000
```

Open [http://localhost:8000](http://localhost:8000) in two browser windows or on two devices.

The pages can also be hosted on static platforms such as GitHub Pages.

## Project structure

| File | Purpose |
| --- | --- |
| `index.html` | Landing page with create and join actions |
| `send.html` | Interface for joining an existing chat |
| `receive.html` | Interface for creating a chat room |
| `send.js` | Peer connection, outgoing messages, and decoding |
| `receive.js` | Room creation, incoming connections, and decoding |
| `index.css` | Shared responsive styles |

## Technology

- HTML5
- CSS3
- Vanilla JavaScript
- PeerJS 1.2.0

## Limitations

- The PeerJS cloud signaling service is loaded from a third-party CDN.
- A chat ends when the page is closed or the peer connection is lost.
- Messages are not persisted.
- The custom cipher only supports the character set defined in the JavaScript files.
- The current cipher is not a substitute for modern cryptographic protocols such as TLS or authenticated encryption.

## Contributing

1. Fork the repository.
2. Create a feature branch.
3. Test the application locally.
4. Open a pull request describing the change.

Small improvements to accessibility, connection handling, message encoding, and cryptography are especially welcome.

## License

No license has been specified for this repository yet.
