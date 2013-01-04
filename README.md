# node-ninja-runner

Node ninja runner is a bash script to run Node.js servers. It will automagically restart crashed servers, and will monitor memory usage for you. To prevent runaway servers, you can:

* Control the number of restarts it does in a certain period of time before it gives up.
* Monitor the amount of memory used by the process and kill it if it exceeds a specified amount.


To use:

    bash node_ninja_runner.sh max_mem max_restarts time_period script_name [other args]


Parameters:

1. **max_mem** -- The maximum amount of memory the node process should be allowed to consume. If it exceeds this, it will be terminated and restarted.
1. **max_restarts** -- This combines with the next param, **time_period**, to determine if the app is "runaway" or not. Normally, when node exits because of an uncaught error, node_ninja_runner starts it. If it exceeds _max_restarts_ in _time_period_ minutes, however, then the app is considered runaway and will no longer be restarted.
1. **time_period** -- See previous.
1. **script_name** -- The name of the node script to run.
1. You can provide optional arguments to the script to run. These are currently limited to 10 in count.


