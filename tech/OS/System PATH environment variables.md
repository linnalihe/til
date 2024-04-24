How to set up PATH variable in Linux: https://opensource.com/article/17/6/set-path-linux
Adding Path to Linux path variable: https://www.baeldung.com/linux/path-variable
To persist PATH permanently add `export PATH$PATH:/place/with/the/file`  to `~/.zshrc`

To be able to run application from any directory, move it to the following location
```bash
sudo mv YOUR-APPLICATION /usr/local/bin
```
On Windows machines, add the program to a directory in the C:// directory and
Go to Start > Edit the system environment variables (control panel) 
Select the Path environment variable > select New 
Paste in the C:// path to your application