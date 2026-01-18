---
{"publish":true,"created":"2025-10-21T16:34:54.615+05:45","modified":"2025-11-16T15:17:57.220+05:45","cssclasses":""}
---

 Pipe - it is a kernel-managed buffer acting as a temporary queue. 
 "Write programs that do one thing well, and connect them"
 A pipe connects the output of one process to input of another, without using intermediate files. This means no extra [[Inode]]
 
 Pipes are one way. 
 ```
 int fds[2]; 
 pipe(fds);
 
 fds[0] will be populated with Read end
 fds[1] will be populated with write end
 ```

using `|` means calling pipe syscall. 

- Anonymous pipe
- Named pipe: 
- [[Socketpair]]/ UNIX domain socket (bi directional pipes)
 
 