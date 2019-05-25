# TON Research

This repo is **enthusiasts research place**. We will post news and updates there.

<!-- toc -->

- [Future steps:](#future-steps)
  * [Creating FAQ & Video tutorial:](#creating-faq--video-tutorial)
  * [Also you will find there:](#also-you-will-find-there)
  * [Git questions?](#git-questions)
- [Feedback / Contact us:](#feedback--contact-us)
- [Lite Client Releases: 🏗](#lite-client-releases-%F0%9F%8F%97)
  * [macOS 🍏](#macos-%F0%9F%8D%8F)
  * [Ubuntu 🐧](#ubuntu-%F0%9F%90%A7)
  * [Windows](#windows)
- [Installation](#installation)
  * [Mac:](#mac)
- [Setup](#setup)
- [Contributing](#contributing)
- [Project](#project)
- [Readme:](#readme)
- [Basic compilation and installation instructions](#basic-compilation-and-installation-instructions)

<!-- tocstop -->

## Future steps:

### Creating FAQ & Video tutorial:
_✨feel free to propose your topics_
- Step-by-step guide: **How to build a TON client** 🛠 (WIP)
- How to get test Grams 💸 (WIP)
- Development:
  - Write first hello-world smartcontract
  - How to deploy smart contract
  - How to send transactions

### Also you will find there:
- Future releases of binaries 🏗
- FAQ with most popular quesitons (WIP)

### Git questions?
⁉️ If you have any questions about project/installation - feel free to [open an issue!](https://github.com/copperbits/TON/issues/new)

## Feedback / Contact us:

- [Telegam public discussion group](https://t.me/copperbits)

## Lite Client Releases: 🏗

### macOS 🍏

[First release](https://github.com/copperbits/TON/releases/tag/test-1)

<!--
### Ubuntu 🐧
// TODO
### Windows
// TODO -->

## Installation

### Mac:

- Download [latest release](https://github.com/copperbits/TON/releases/)
- Go to command line, where binary placed
- Run: (`./test-lite-client -C ton-lite-client-test1.config.json`)
- Profit! 🎉
- run `help` to getting started
<!--
## Setup

// TODO -->

## Contributing

Your contributions are really appreciated. You can follow [CONTRIBUTING](https://github.com/zhuochun/md-writer/blob/master/CONTRIBUTING.md) guide to get everything started.

## Project

<!-- - View [CHANGELOG][] :notebook_with_decorative_cover: -->
- Bugs, suggestions or feature requests, [open an issue](https://github.com/copperbits/TON/issues/new) :octocat:
- Star [GitHub repo](https://github.com/copperbits/TON/) to support this project :+1:
- License in [GNU Lesser General Public License v2.1
](https://github.com/copperbits/TON/blob/master/LICENSE) :unlock:
- Shipped by [CooperBits team](https://t.me/copperbits) :sunny: and [contributors](https://github.com/copperbits/TON/graphs/contributors) :clap:



## Readme:
This is a distribution of a preliminary version of the TON Blockchain Lite Client along with the relevant portions of the TON Blockchain Library. It is not necessarily representative of the totality of the TON Blockchain code developed so far; rather it is a simplified stable version, containing only those files that are necessary for compiling the Lite Client, and sometimes outdated versions of these files sufficient for this purpose.

Use this software at your own risk; consult the DISCLAIMER for more information.

The software is licensed under GNU Lesser General Public License version 2 or later; consult LICENSE.LGPL and LGPL.v2 for more information. If you ever use any of these source files to develop your own versions of this or other software, you must attach a comment with the contents of LGPL.v2 to the beginning of each source file taken from this archive.

The software is likely to compile and work properly on most Linux systems. It should work on macOS and even Windows; however, we do not guarantee this for this preliminary version.

## Basic compilation and installation instructions

1) Download and unpack the newest version of this archive, available at

https://test.ton.org/download

The TON Blockchain Test Network is updated quite often, so we cannot guarantee that older versions of the Lite Client will always work. Backward compatibility is not enforced at this development stage.

2) Install the newest versions of make, cmake (version 3.0.2 or later), OpenSSL (including C header files), and g++ or clang (or another C++14-compatible compiler as appropriate for your operating system).

3) Suppose that you have unpacked this archive to directory ~/lite-client, where ~ is your home directory, and that you have created an empty directory ~/liteclient-build. Then run the following in a terminal on a Linux system:

```bash
cd ~/liteclient-build
cmake ~/lite-client
cmake --build . --target test-lite-client
```
You might also want to build some extra utilities useful for smart-contract development:

```bash
cmake --build . --target fift
```

4) Download the newest configuration file from https://test.ton.org/ton-lite-client-test1.config.json :

wget https://test.ton.org/ton-lite-client-test1.config.json

5) Run the Lite Client:

```bash
./test-lite-client -C ton-lite-client-test1.config.json
```

If everything was installed successfully, the Lite Client will connect to a special server (a full node for the TON Blockchain Test Network #1) and will send some queries to the server.
If you indicate a writeable "database" directory as an extra argument to the client, it will download and save the block and the state corresponding to the newest masterchain block:

```bash
./test-lite-client -C ton-lite-client-test1.config.json -D ~/ton-db-dir
```

Basic help info can be obtained by typing "help" into the Lite Client. Type "quit" or press Ctrl-C to exit.

6) Now you can create new smart contracts, examine the state of existing smart contracts, send external messages to smart contracts and so on. You can also use Fift (if you have compiled it) to compile, execute, and debug your smart contracts locally.

More details on these activities, including step-by-step instructions for creating a simple wallet smart contract (along with its source code), may be found in the HOWTO file included in this archive.

7) Some documentation on the TON Blockchain and TON Virtual Machine may be found at the download page https://test.ton.org/download . Be aware that this documentation may not be completely in sync with the version currently employed by the Test Network, because some minor implementation details are likely to be changed during the final development and testing phases.