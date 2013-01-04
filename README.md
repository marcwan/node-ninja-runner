# node-ninja-runner

Node ninja runner is a bash script to run Node.js servers. It will automagically restart crashed servers, and will monitor memory usage for you. To prevent out-of-control servers, you can:

* Control the number of restarts it does in a certain period of time before it gives up.
* Monitor the amount of memory used by the process and kill it if it exceeds a specified amount.


To use:

    bash node_ninja_runner.sh max_mem max_restarts time_period script_name [other args]

For example:

    bash node_ninja_runner.sh 100 10 2 personal_blog.js production

This will run _personal_blog.js_ passing in the argument _production_, with a memory limit of 100M, and will permit no more than 10 crashes within a 2 minute period.


Parameters:

1. **max_mem** -- The maximum amount of memory the node process should be allowed to consume. If it exceeds this, it will be terminated and restarted.
1. **max_restarts** -- This combines with the next param, **time_period**, to determine if the app is "runaway" or not. Normally, when node exits because of an uncaught error, node_ninja_runner starts it. If it exceeds _max_restarts_ in _time_period_ minutes, however, then the app is considered runaway and will no longer be restarted.
1. **time_period** -- See previous.
1. **script_name** -- The name of the node script to run.
1. You can provide optional arguments to the script to run. These are currently limited to 10 in count.



# License

Node ninja runner is freely distributable under the terms of the MIT license.

Copyright (c) 2013 Marc Wandschneider

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

