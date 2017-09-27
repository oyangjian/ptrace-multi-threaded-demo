# ptrace-demo
Simple commented program which demonstrates using ptrace(2)

## Usage
```bash
cd ptrace-demo
make
./ptrace-demo 1> stdout 2> stderr
```
In another terminal, do
```bash
cd ptrace-demo
tail --follow stdout
```
to follow output from the child and
```bash
cd ptrace-demo
tail --follow stderr
```
to follow output from the parent. You should see output like the following:
```
parent: forking...
parent: setting ptrace options...
ptrace options set!
parent: SYSCALL [rt_sigprocmask] = 0
parent: SYSCALL [fstat] = 0
parent: SYSCALL [write] = 9
parent: SYSCALL [clock_nanosleep] = 0
parent: SYSCALL [write] = 9
parent: SYSCALL [clock_nanosleep] = 0
parent: SYSCALL [write] = 9
parent: SYSCALL [clock_nanosleep] = 0
...
```
```
child: 1
child: 2
child: 3
child: 4
child: 5
...
```
