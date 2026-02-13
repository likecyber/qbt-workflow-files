
# Introduction

This is an action based repo to collect, process and release current versions of the source code build dependencies for the [qbittorrent-ut-nox static build script](https://github.com/likecyber/qbittorrent-ut-nox-static).

They are used as for three main purposes:

- To reduce unnecessary bandwidth usage for hosts when using matrix builds as they may be doing hundreds of unique builds, all  repeatedly downloading the same remotes files over and over. The standard build and release workflow has 16 jobs downloading 15  dependencies each. This means each file is downloaded 16 times from the remote host per workflow run.

- As an alternative URL location for downloading the dependencies when this variable is set `export qbt_workflow_files=yes` and the script is run as an action or by the end user.

- To be used in workflows and uploaded as artifacts in the matrix build which allows the matrix builds to download the artifacts. This option is specific and unique to specially crafted workflows and is not meant to be used by the end user.

It runs every 2 hours and only keeps the most current versions of the dependencies.
