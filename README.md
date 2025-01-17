# js-multi-threading

## Set up

To install dependencies:

```bash
bun install
```

To run:

```bash
bun run index.ts
```

This project was created using `bun init` in bun v1.1.8. [Bun](https://bun.sh) is a fast all-in-one JavaScript runtime.

# Background

Node.js is a JavaScript runtime environment. It executes JavaScript outside of
the browser. And most of the time, we use it to build back-end applications.

Given a Node.js server with 4GB of ram and 2 CPUs.

Since our app is written in JavaScript, it is a single-thread
application. That means even if we have 2 CPUs, we can only utilize one at
time, which is a big waste of resources. This is why we typically run multiple
Node.js processes, each server running on a different port. And for that to
work, we have to use a load balancer (e.g. NGINX), a process manager
(e.g. PM2), a container manager (Kubernetes), and a cloud platform for hosting
(e.g. AWS, Heroku). But all of these are a solution to the load balancer
problem.

Now, if we decide to choose any other mainstream languages (e.g. Rust, Go, Java).
Then we can use true multi-threading, meaning the application that runs on
one processor can utilize all of the CPUs in the machine. Additionally, threads
are a lot lighter than processes. They are faster to spin up and they take up
less memory. Essentially, making your application a lot more efficient.
