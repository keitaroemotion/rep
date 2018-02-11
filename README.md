# rep

rep is the powerful tool to temporarily change the specific lines of code.
it does not harm your changes.

## Installation

```
./installer
```

## Usage

the repository has to be the git repo.

Then in order to set up the DSL, type as follows:
```
$ rep -e
```

Then, need something like:
```
app/controllers/moomin_controller.rb
include KeymakerAuthentication ||| # 
include Raisable               ||| #
before_action :moomin_gate    ||| #

config/routes.rb
  scope module: "moomin", constraints: { subdomain: /^moomin(-staging)?$/ } ||| scope module: "moomin"
```

`|||` is the separator, and the structure is such as:

```
[file name target(to swap temporarily)]
[target code line] ||| #  << means it is going to be commented out


[file name target(to swap temporarily)]
[target code line to be replaced] ||| [target code line to replace]
```

Then, type

```
$ rep
```

Now your codebase has been replaced.
(take care, if you typed the file name which does not actually exist, the script might blow up at this point)

To roll back,

```
$ rep -b
```


# Author

```
Kei Sugano <tobasojyo@gmail.com>
```

