# devnotes.md

Private repo; T5 fork (via GH GUI) == https://github.com/gitpitch/gitpitch -> https://github.com/Tonic5/gitpitch.git

## Reference:
* [T5 foodtech repo's README](https://github.com/Tonic5/foodtech/README.md)
* [Gitpitch wiki Server-Build-Instructions](https://github.com/gitpitch/gitpitch/wiki/Server-Build-Instructions)
* [PlayFramework 2.5 background info](https://playframework.com/documentation/2.5.x/Anatomy)

TECH STACK PIVOT Reveal-md -> GITPITCH
(bc features, even within context of markdown!)

See https://github.com/gitpitch/gitpitch/wiki/Server-Build-Instructions

```sh
# install jdk8u144
# recall jdk is for devs, incl jre + dev tools

$ java -version
javac 1.8.0_144

# install sbt (scala build tool) via homebrew:
$ brew install sbt@1

$ cd ~/repos/github
$ git clone git@github.com:Tonic5/gitpitch.git
$ cd ~/repos/github/Tonic5/gitpitch

```

```sh
# BUILD the (default-configured) 'production' bundle:
$ sbt dist
....
[info] Your package is ready in /Users/cweekly/repos/github/Tonic5/gitpitch/target/universal/server-1.1.zip
[info]
[success] Total time: 24 s, completed Aug 23, 2017 11:40:53 AM
# note this ^ took a lot longer the 1st time (several minutes)
```

```sh
# DEPLOY
# TBD. tabled for now, low-priority
# CW Note - shelved WIP proving this is easy enough; have 'localdev' branch of parent gitpitch.git repo, w/ custom conf WIP
```

```sh
# LOCAL DEV WORKFLOW
# instead of deploying, can simply run in dev mode, directly from local source
# cf https://playframework.com/documentation/2.5.x/Deploying#Running-a-production-server-in-place

$ sbt run
....
[info] Loading project definition from /Users/cweekly/repos/github/Tonic5/gitpitch/project
[info] Set current project to server (in build file:/Users/cweekly/repos/github/Tonic5/gitpitch/)
--- (Running the application, auto-reloading is enabled) ---
[info] p.c.s.NettyServer - Listening for HTTP on /0:0:0:0:0:0:0:0:9000
(Server started, use Ctrl+D to stop and go back to the console...)

# point browser to the 'kitchen-sink' demo (fetched from github)
http://gitpitch.local:9000/gitpitch/kitchen-sink

# point browser to T5 'foodtech-pitchdeck' preso
http://gitpitch.local:9000/Tonic5/presos/foodtech-pitchdeck

```