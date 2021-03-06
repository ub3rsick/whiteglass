---
tags:
  - cheatsheet
  - pentesting
layout: post
title: Spawning a TTY Shell
---
Often during pen tests you may obtain a shell without having tty, yet wish to
interact further with the system. Here are some commands which will allow you to
spawn a tty shell. Obviously some of this will depend on the system environment
and installed packages.

**Shell Spawning**

```python
python -c 'import pty; pty.spawn("/bin/sh")'
```

```bash
echo os.system('/bin/bash')
```
<!-- more -->
```bash
/bin/sh -i
```

```perl
perl —e 'exec "/bin/sh";'
```

```perl
perl: exec "/bin/sh";
```

```ruby
ruby: exec "/bin/sh"
```

```
lua: os.execute('/bin/sh')
```

From within IRB - Interactive Ruby Shell

```ruby
exec "/bin/sh"
```

From within vi

```
:!bash
```

From within vi

```
:set shell=/bin/bash:shell
```

From within nmap (nmap --interactive)

```
!sh
```

Many of these will also allow you to escape jail shells.

Original Post: [NETSEC - Spawning a TTY shell](http://netsec.ws/?p=337)
