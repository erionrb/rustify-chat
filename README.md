# Rustify Chat

Rustify chat is a simple chat application developed using the Rust programming language and the Rocket web framework. It allows users to post messages to chat rooms and retrieve messages from those rooms in real-time using Server-Sent Events (SSE).

## Installation
Before running the application, ensure that you have Rust and Cargo installed on your system. You can install Rust and Cargo by following the instructions provided on the official Rust website: https://www.rust-lang.org/tools/install

Once Rust and Cargo are installed, clone the project repository from GitHub:

```bash
git clone <repository-url>
cd simple-chat-application
```
Build and run the project using Cargo:
```bash
cargo run
```
This will compile the project and start the web server locally.

## Usage
Once the application is running, you can access it through a web browser or use HTTP client tools like cURL or Postman to interact with its endpoints.

- To post a message to a chat room, send a POST request to the /message endpoint with the following payload:
```json
{
  "room": "room_name",
  "username": "your_username",
  "message": "your_message"
}
```

- To retrieve messages from a chat room in real-time, open a connection to the /events endpoint using an SSE-compatible client. The server will stream messages to the client as they are posted.
Code Structure
The project consists of the following main components:

- **Message Struct**: Represents a chat message with fields for the room name, username, and message content.

- **POST Endpoint**: Handles incoming POST requests to submit messages to chat rooms. Validates the message data and sends it to a message queue for processing.

- **Event Stream Endpoint**: Handles incoming GET requests to retrieve messages from chat rooms in real-time. Subscribes to a message queue and streams messages to clients as Server-Sent Events (SSE).

- **Rocket Configuration**: Configures and launches the Rocket web application, setting up routes for message submission and retrieval, and serving static files.

## Conclusion
This chat application provides a basic example of building a real-time web application using Rust and Rocket. It demonstrates the use of Rocket's features for handling HTTP requests, managing state with message queues, and streaming data to clients using Server-Sent Events. Further enhancements can be made to improve the user interface, add authentication, and handle larger message volumes efficiently.

## License
This project is licensed under the terms of the MIT license. See the LICENSE file for details.

## Acknowledgements
**Rust Programming Language:** https://www.rust-lang.org/
**Rocket Web Framework:** https://rocket.rs/
**SSE (Server-Sent Events) Specification:** https://html.spec.whatwg.org/multipage/server-sent-events.html

**Note:** This documentation is intended to provide an overview of the project and guide users on how to install, use, and contribute to it. For detailed technical information, code explanations, and contribution guidelines, please refer to the project's source code and documentation.