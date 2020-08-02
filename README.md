# Cmdline Utils
Some generic utils that I use on my mac to make my life easier.
May be not the best approach out there, but this has grown on me over the years. I initially created this back in the days
to use in my Windows XP with batch (and java).

# Setup
- Clone this repo to say `~/github.abeytom/cmdline-utils`
- Add `~/github.abeytom/cmdline-utils` to the $PATH
- Build `cd go && make`
- Give exec permissions cmd alias files `chmod +x bk csv ft goexec gw kc kcurl op opf`

# Core Utils `bk` bookmark
This is used to bookmark various FileSystem Paths and Command Aliases

### Add Path
```
# add a path
bk add path <alias> /path/to file
bk add path cu ~/github.abeytom/cmdline-utils

# List Paths
bk list paths

# cd to that dir
. op cu

# open a finder
opf cu
```

### Add command
```
# add a command
bk add cmd <alias> <abey@192.168.1.131>
bk add cmd ssh-dell "ssh -i /path/to/file abey@192.168.1.131"

# list commands
bk list cmd

# execute a command
bk exec ssh-dell

# execute a command by index
bk exec 0     # list command will show the index also

# with args
bk exec alias args1 arg2
```

# Kubernetes Utils 
This is just a wrapper around `kubectl`.


```
# export the namespace as env variable one time for this particular window
export k8ns=my-namespace

# all kubectl default commands will work with this like
kc get pods                         # wrapper for kubectl -n my-namespace get pods
kc get svc

# shortcut commands 
kc logs pod-name* [args]            # use wildcards in name
kc ssh pod-name*  [bash | sh]       # ssh to the pod
kc logs `kc pod pod-name* 0`        # get logs from the first matched pod-name* 
``` 













 



