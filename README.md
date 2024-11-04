# first module test for uv 
## init module 
```bash 

rustam@rustam-zenbook:~/test-uv-lib$ uv init --lib module-uv 
Initialized project `module-uv` at `/home/rustam/test-uv-lib/module-uv`
rustam@rustam-zenbook:~/test-uv-lib$ ll
total 12
drwxrwxr-x  3 rustam rustam 4096 Nov  4 19:52 ./
drwxr-x--- 26 rustam rustam 4096 Nov  4 19:52 ../
drwxrwxr-x  4 rustam rustam 4096 Nov  4 19:52 module-uv/
rustam@rustam-zenbook:~/test-uv-lib$ tree .
.
└── module-uv
    ├── pyproject.toml
    ├── README.md
    └── src
        └── module_uv
            ├── __init__.py
            └── py.typed

4 directories, 4 files
rustam@rustam-zenbook:~/test-uv-lib$ cd module-uv/
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ cat pyproject.toml 
[project]
name = "module-uv"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
authors = [
    { name = "rustam", email = "rustamaxm@gmail.com" }
]
requires-python = ">=3.12"
dependencies = []

[build-system]
requires = ["hatchling"]
build-backend = "hatchling.build"
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ cat src/module_uv/
__init__.py  py.typed     
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ cat src/module_uv/py.typed 
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ ls
pyproject.toml  README.md  src
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ uv add pytest numpy pyserial poethepoet
Using CPython 3.12.3 interpreter at: /usr/bin/python3
Creating virtual environment at: .venv
Resolved 11 packages in 17ms
   Built module-uv @ file:///home/rustam/test-uv-lib/module-uv
Prepared 1 package in 516ms
Installed 10 packages in 37ms
 + iniconfig==2.0.0
 + module-uv==0.1.0 (from file:///home/rustam/test-uv-lib/module-uv)
 + numpy==2.1.3
 + packaging==24.1
 + pastel==0.2.1
 + pluggy==1.5.0
 + poethepoet==0.29.0
 + pyserial==3.5
 + pytest==8.3.3
 + pyyaml==6.0.2
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ cat pyproject.toml 
[project]
name = "module-uv"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
authors = [
    { name = "rustam", email = "rustamaxm@gmail.com" }
]
requires-python = ">=3.12"
dependencies = [
    "numpy>=2.1.3",
    "poethepoet>=0.29.0",
    "pyserial>=3.5",
    "pytest>=8.3.3",
]

[build-system]
requires = ["hatchling"]
build-backend = "hatchling.build"
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ ll
total 52
drwxrwxr-x 5 rustam rustam  4096 Nov  4 19:54 ./
drwxrwxr-x 3 rustam rustam  4096 Nov  4 19:52 ../
drwxrwxr-x 7 rustam rustam  4096 Nov  4 19:52 .git/
-rw-rw-r-- 1 rustam rustam   109 Nov  4 19:52 .gitignore
-rw-rw-r-- 1 rustam rustam   388 Nov  4 19:54 pyproject.toml
-rw-rw-r-- 1 rustam rustam     5 Nov  4 19:52 .python-version
-rw-rw-r-- 1 rustam rustam     0 Nov  4 19:52 README.md
drwxrwxr-x 3 rustam rustam  4096 Nov  4 19:52 src/
-rw-rw-r-- 1 rustam rustam 19438 Nov  4 19:54 uv.lock
drwxrwxr-x 4 rustam rustam  4096 Nov  4 19:54 .venv/
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ uv build 
Building source distribution...
Building wheel from source distribution...
Successfully built dist/module_uv-0.1.0.tar.gz and dist/module_uv-0.1.0-py3-none-any.whl
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ ls
dist  pyproject.toml  README.md  src  uv.lock
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ ll dist/
total 24
drwxrwxr-x 2 rustam rustam 4096 Nov  4 19:56 ./
drwxrwxr-x 6 rustam rustam 4096 Nov  4 19:56 ../
-rw-rw-r-- 1 rustam rustam    1 Nov  4 19:56 .gitignore
-rw-r--r-- 1 rustam rustam 1243 Nov  4 19:56 module_uv-0.1.0-py3-none-any.whl
-rw-r--r-- 1 rustam rustam 7563 Nov  4 19:56 module_uv-0.1.0.tar.gz
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ ls
dist  pyproject.toml  README.md  src  uv.lock
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ cat README.md 
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ cat pyproject.toml 
[project]
name = "module-uv"
version = "0.1.0"
description = "Add your description here"
readme = "README.md"
authors = [
    { name = "rustam", email = "rustamaxm@gmail.com" }
]
requires-python = ">=3.12"
dependencies = [
    "numpy>=2.1.3",
    "poethepoet>=0.29.0",
    "pyserial>=3.5",
    "pytest>=8.3.3",
]

[build-system]
requires = ["hatchling"]
build-backend = "hatchling.build"
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ nano src/module_uv/main.py
```
## python script run 
```
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ uv run hi 
   Built module-uv @ file:///home/rustam/test-uv-lib/module-uv
Uninstalled 1 package in 1ms
Installed 1 package in 3ms
hi from script
```
## poethepoet
``` 
rustam@rustam-zenbook:~/test-uv-lib/module-uv$ uv run poe hi 
   Built module-uv @ file:///home/rustam/test-uv-lib/module-uv
Uninstalled 1 package in 1ms
Installed 1 package in 2ms
Poe => echo 'Hi from poethepoet'
Hi from poethepoet

```
