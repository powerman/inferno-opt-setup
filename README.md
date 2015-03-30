Scripts to setup projects installed in `/opt` (bind their commands, man pages, etc. to standard places).


---


To install system-wide (if your Inferno installed in your home directory or if you root):

```
hg clone https://code.google.com/p/inferno-opt-setup/ $INFERNO_ROOT/opt/setup
```

To install locally for some project:

```
$ cd YOUR_PROJECT_DIR
$ mkdir -p opt/
$ hg clone https://code.google.com/p/inferno-opt-setup/ opt/setup
$ emu
; cd YOUR_PROJECT_DIR_INSIDE_EMU
; bind opt /opt
```

To use add this into `profile` file in your Inferno home dir:

```
/opt/setup/cmd
/opt/setup/man
```

The `/opt/setup/cmd` will bind all commands provided by /opt packages into `/dis/`, to let you run these commands by their name, without long `/opt/provider/package/dis/cmd/` prefix.
The `/opt/setup/man` will bind all man pages provided by /opt packages into `/man/*/` and union provided man indexes with `/man/*/INDEX`.