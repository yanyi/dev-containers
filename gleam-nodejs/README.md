# gleam-nodejs

This dev container utilizes the Gleam's pre-built Erlang image 
`ghcr.io/gleam-lang/gleam:v1.4.1-erlang-slim` and installs Node.js in it.

## Why Erlang -> Node.js?

As a beginner to the language and ecosystem, I wanted to explore more. I started
off with using the Node.js image built by Gleam but learned that in order to
compile and run the Gleam tests or files, there is a requirement for Erlang to
be installed.

I had some issues installing Erlang using the
`ghcr.io/gleam-lang/gleam:v1.4.1-node-slim` image, so I opted to go straight to
the Erlang image first and installed Node.js thereafter.

## Why a Need for Node.js?

I wanted to try to run Gleam applications in Node.js, also, while learning more
about the language and ecosystem.
