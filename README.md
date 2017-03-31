<p align="center">
    <img src="Logo.png" width="480" max-width="90%" alt="Marathon" />
</p>

Welcome to **Marathon**, a command line tool that makes it easy to write, run and manage your Swift scripts. It's powered by the [Swift Package Manager](https://github.com/apple/swift-package-manager) and requires no modification to your existing scripts or dependency packages.

## Features

🐣 Create scripts
```
$ marathon create helloWorld "import Foundation; print(\"Hello world\")"
```

🏃‍♀️ Run scripts
```
$ marathon run helloWorld
> Hello world
```

📦 Hassle free dependency management. Simply add a package...
```
$ marathon add git@github.com:JohnSundell/Files.git
```

...and use it without any additional work
```swift
import Files

for file in try Folder(path: "MyFolder").files {
    print(file.name)
}
```

🚀 Update all of your scripting dependencies with a single call
```
$ marathon update
```

⚒ Edit, run & debug your scripts using Xcode...
```
$ marathon edit helloWorld
```

...or in your favorite text editor
```
$ marathon edit helloWorld --no-xcode
```

💻 Install scripts as binaries and run them independently from anywhere
```
$ marathon install helloWorld
$ helloWorld
> Hello world
```

👪 Share your scripts with your team and automatically install their dependencies:
```
$ echo "git@github.com:JohnSundell/Files.git" > Marathonfile
$ marathon run mySharedScript
```

## Installing

Using Make:
```
$ git clone git@github.com:JohnSundell/Marathon.git
$ cd Marathon
$ make
```

Using the Swift Package Manager:
```
$ git clone git@github.com:JohnSundell/Marathon.git
$ cd Marathon
$ swift build -c release -Xswiftc -static-stdlib
$ cp -f .build/release/Marathon /usr/local/bin/marathon
```

To update Marathon, simply repeat any of the above two series of commands, except cloning the repo.

## Requirements

Marathon requires the following to be installed on your system:

- Swift 3.1 or later (bundled with Xcode 8.3 or later)
- Git
- Xcode (if you want to edit scripts using it)

## Examples

Check out [this repository](https://github.com/JohnSundell/Marathon-Examples) for a few example Swift scripts that you can run using Marathon.

## Using a Marathonfile

To easily define dependencies for a script in a declarative way, you can create a `Marathonfile` in the same folder as your script. This file is simply a *new line separated list* of URLs pointing to packages that should be installed before running the script. By doing this you can ensure that the required dependencies will be installed when sharing your script with team members, friends or the wider community.

Here is an example of a `Marathonfile`:
```
git@github.com:JohnSundell/Files.git
git@github.com:JohnSundell/Unbox.git
git@github.com:JohnSundell/Wrap.git
```

## Help, feedback or suggestions?

- Run `$ marathon help` to display help for the tool itself or for any specific command.
- [Open an issue](https://github.com/JohnSundell/Marathon/issues/new) if you need help, if you found a bug, or if you want to discuss a feature request.
- [Open a PR](https://github.com/JohnSundell/Marathon/pull/new/master) if you want to make some change to Marathon.
- Contact [@johnsundell on Twitter](https://twitter.com/johnsundell) for discussions, news & announcements about Marathon.
