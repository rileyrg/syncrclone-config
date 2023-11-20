
# Table of Contents



"""
syncrclone

Config File

This configuration file is read as Python so things can be customized as
desired. With few exception, any missing items will go to the defaults
already specified.

Flags should always be a list.
Example: \`&#x2013;exclude myfile\` will be ['&#x2013;exclude','myfile']

This is **ALWAYS** evaluated from the parent of this file.

"""
\## Remotes:

remoteA = "/home/rgr/cloud"
remoteB = "hetzner:cloud"

workdirA = None  # <remoteA>/.syncrclone
workdirB = None  # <remoteB>/.syncrclone

import subprocess
name = subprocess.check<sub>output</sub>("hostname").rstrip()
name = name.decode("utf-8")
import hashlib
name += hashlib.md5(f"{remoteA}{remoteB}".encode()).hexdigest()
\## rclone flags

rclone<sub>exe</sub> = "rclone"

filter<sub>flags</sub> = ["&#x2013;filter-from", "excludes.txt"]

rclone<sub>flags</sub> = [ "&#x2013;links", "&#x2013;check-first", "&#x2013;transfers", "1", "&#x2013;checkers",  "9"]
\#rclone<sub>flags</sub> = [ "&#x2013;links"]

rclone<sub>env</sub> = {}

rclone<sub>flagsA</sub> = []
rclone<sub>flagsB</sub> = ["&#x2013;sftp-disable-hashcheck"]

\## Sync Options

compare = "mtime"

dt = 1.1  # seconds

conflict<sub>mode</sub> = "newer"

tag<sub>conflict</sub> = False

reuse<sub>hashesA</sub> = False
reuse<sub>hashesB</sub> = False

always<sub>get</sub><sub>mtime</sub> = True

backup = True

backup<sub>with</sub><sub>copy</sub> = None

sync<sub>backups</sub> = False

hash<sub>fail</sub><sub>fallback</sub> = None  # {'size','mtime',None}

set<sub>lock</sub> = False

action<sub>threads</sub> = 1

cleanup<sub>empty</sub><sub>dirsA</sub> = None
cleanup<sub>empty</sub><sub>dirsB</sub> = None

avoid<sub>relist</sub> = True

\## Rename Tracking

renamesA = None
renamesB = None

\## Status

list<sub>status</sub><sub>dt</sub> = 10  # sec

\## Logs

save<sub>logs</sub> = True
local<sub>log</sub><sub>dest</sub> = ""  # NOT on a remote

\## Pre- and Post-shell commands to run

pre<sub>sync</sub><sub>shell</sub> = ""
post<sub>sync</sub><sub>shell</sub> = ""

stop<sub>on</sub><sub>shell</sub><sub>error</sub> = False

tempdir = None  # tempfile.TemporaryDirectory().name

\#######

\_syncrclone<sub>version</sub> = "20230310.0.BETA"

