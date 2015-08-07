+++
date = "2014-02-06"
draft = false
title = "Contenido de prueba"
summary = "Leeme para conocer los elementos que puedes hacer en markdown"
author_user_devhunter = "uzi200"
author_mail = "julioc255io@gmail.com"
+++

<blockquote class="imgur-embed-pub" lang="en" data-id="o3HT4dc" data-context="false"><a href="//imgur.com/o3HT4dc">Most Viral Edit: Thanks so much!I will try to add the rest of the clip when I get some time. Gotta do some work first. Thanks again for the love!</a></blockquote><script async src="//s.imgur.com/min/embed.js" charset="utf-8"></script>

**Lorem ipsum dolor**


Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.


<iframe src="https://ghbtns.com/github-btn.html?user=devhunterco&repo=blog&type=star&count=true&size=large" frameborder="0" scrolling="0" width="160px" height="30px"></iframe>

> Excepteur sint occaecat cupidatat non proident!!


<script src="https://gist.github.com/juliocesar-io/fee642c05a9b95a5bc09.js"></script>


`Lorem`


```
$lorem = Copyright (c) 2015 Copyright Holder All Rights Reserved.

```


Amamos python

<pre><code class="language-python">

def LetterChanges(str):
    s = ""
    v = ["a", "e", "i", "o", "u"]
    for letra in str:
        if ord('a') <= ord(letra) and ord(letra) < ord('z'):
            c = ord(letra) + 1
            if c in map(ord, v):
                s += chr(c).upper()
            else:
                s += chr(c)
        else:
            s += letra
    return s

</code></pre>



Colons can be used to align columns.

| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |

The outer pipes (|) are optional, and you don't need to make the raw Markdown line up prettily. You can also use inline Markdown.

Markdown | Less | Pretty
--- | --- | ---
*Still* | `renders` | **nicely**
1 | 2 | 3

Three or more...

---

Hyphens

***

Asterisks

___

Underscores


1. First ordered list item
2. Another item
⋅⋅* Unordered sub-list.
1. Actual numbers don't matter, just that it's a number
⋅⋅1. Ordered sub-list
4. And another item.

⋅⋅⋅You can have properly indented paragraphs within list items. Notice the blank line above, and the leading spaces (at least one, but we'll use three here to also align the raw Markdown).

⋅⋅⋅To have a line break without a paragraph, you will need to use two trailing spaces.⋅⋅
⋅⋅⋅Note that this line is separate, but within the same paragraph.⋅⋅
⋅⋅⋅(This is contrary to the typical GFM line break behaviour, where trailing spaces are not required.)

* Unordered list can use asterisks
- Or minuses
+ Or pluses

`Tambien Javascript`

<pre><code class="language-javascript">

var express = require('express'),
    app = express(),
    http = require('http').Server(app),
    io = require('socket.io')(http),
    fs = require('fs'),
    five = require("johnny-five"),
    path = require('path');

var spawn = require('child_process').spawn;
var proc;


app.use('/', express.static(path.join(__dirname, 'stream')));

http.listen(3000, function() {
  console.log('Servidor escuchando en puerto 3000');
});


app.get('/', function(req, res) {
  res.sendFile(__dirname + '/index.html');
});

app.get('/keypress.js', function(req, res) {
  res.sendFile(__dirname + '/keypress.js');
});

var sockets = {};

io.on('connection', function(socket) {

  sockets[socket.id] = socket;
  console.log("Clientes conectados ", Object.keys(sockets).length);

  socket.on('disconnect', function() {
    delete sockets[socket.id];

    // no more sockets, kill the stream
    if (Object.keys(sockets).length === 0) {
      app.set('watchingFile', false);
      if (proc) proc.kill();
      fs.unwatchFile('./stream/image_stream.jpg');
    }
  });

  socket.on('start-stream', function() {
    startStreaming(io);
  });

});

function stopStreaming() {
  if (Object.keys(sockets).length === 0) {
    app.set('watchingFile', false);
    if (proc) proc.kill();
    fs.unwatchFile('./stream/image_stream.jpg');
  }
}

function startStreaming(io) {

  if (app.get('watchingFile')) {
    io.sockets.emit('liveStream', 'image_stream.jpg?_t=' + (Math.random() * 100000));
    return;
  }

  var args = ["-w", "640", "-h", "480", "-o", "./stream/image_stream.jpg", "-t", "999999999", "-tl", "100"];
  proc = spawn('raspistill', args);

  console.log('Watching for changes...');

  app.set('watchingFile', true);

  fs.watchFile('./stream/image_stream.jpg', function(current, previous) {
    io.sockets.emit('liveStream', 'image_stream.jpg?_t=' + (Math.random() * 100000));
});

}


board = new five.Board({ port: "/dev/ttyACM0" });

</code></pre>
