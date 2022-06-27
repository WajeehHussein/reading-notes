# Reading Day 13

## [Home Page](/README.md)

## Rooms
A room is an arbitrary channel that sockets can join and leave. It can be used to broadcast events to a subset of clients:

Joining and leaving
You can call join to subscribe the socket to a given channel:

```
io.on("connection", (socket) => {
  socket.join("some room");
});
```
And then simply use to or in (they are the same) when broadcasting or emitting:

```
io.to("some room").emit("some event");
```
You can emit to several rooms at the same time:

```
io.to("room1").to("room2").to("room3").emit("some event");
```

To leave a channel you call leave in the same fashion as join.

## Room events
Starting with `socket.io@3.1.0` , the underlying Adapter will emit the following events:

- `create-room` (argument: room)

- `delete-room` (argument: room)

- `join-room` (argument: room, id)

- `leave-room` (argument: room, id)

## Namespaces
A Namespace is a communication channel that allows you to split the logic of your application over a single shared connection (also called "multiplexing").

```
const nsp = io.of("/my-namespace");

nsp.on("connection", socket => {
  console.log("someone connected");
});

nsp.emit("hi", "everyone!");
```