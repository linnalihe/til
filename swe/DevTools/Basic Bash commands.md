The command syntax is in the following order:
command options arguments

`ls -l`
when it starts with `-` it's a file, could be text, binary, etc
when it starts with `d` it's a directory
`c` is a character file
`b` is a block (block disk) file
`l` is link
`s` is socket
`p` is pipe

`ln -s` is a command to create a soft link
give it a source and a destination
`unlink destination` removes the link

`ls -lt` is sorted based on time
`ls -ltr` sorted in reverse

`history` to get vagrant user's command history
`sudo -i` then `history` to get history of root user

filters and redirections is very useful and important

`grep` to find the line of a text within a file
`grep quiz exam.txt` finds the line that contians `quiz` within `exam.txt`
`grep -i` for case insensitive

`grep -i firewall *` to find `firewall` in all files in directory

`grep -iR` to account for directories

`grep -vi firewall *` is reverse search to find everything that doesn't have `firewall` on the line

`less file-path-to-read` is a reader not an editor, can search with `/`, move with up and down arrow
`more file-path-to-read`, `q` to quit
`head file-path-to-read` to see first 10 lines or `head -20 file-path-to-read`
`tail -2 file-path-to-read` shows last 2 lines, default is last 10 lines
`tail -f file-path-to-read` is dynamic and good for reading logs as they come in

`cut -d: -f1 your-file-path` cut is only good if you have well defined delimiters separating columns like here with a colon in `etc/passwd` file

`awk -F':' '{print $1}' /etc/passwd` to get the first column. `awk` lets you use regular expressions and more advanced search

can use `vim` to find and replace by opening up the file in vim and then
`:%s/text-to-replace/replace-with-this-text`. This will only replace once per line to replace globally add a `g`, it will look like `:%s/text-to-replace/replace-with-this-text/g`

`sed 's/text-to-replace/replace-with-this-text/g' *` to do this on the terminal via bash. will print it on the screen without actually doing it yet
add `-i` to execute `sed -i 's/text-to-replace/replace-with-this-text/g' *`

Default for commands print it to the screen but we can add it to another file using redirection
`uptime > /tmp/sandbox-bash.txt` will create file if it doesn't exist and will overwrite if the file does exist. Use double arrows to append
`uptime >> /tmp/sandbox-bash.txt`

`/dev/null` is a black hole, if you don't want to print anything on screen or redirect to any files you can redirect to here
`cat /dev/null/ > /tmp/sandbox-bash.txt` to clear the file

`wrong-command -m > /dev/null` will still print out the error indicating command is not found
`wrong-command -m 2> /dev/null` for standard error
`wrong-command -m 1> /dev/null` for standard out
`&>>` redirect and append all output to file

`wc -l /etc/passwd` counts the line in the file
`ls | wc -l` to count how many files are in the directory. the output of `ls` is the input to the `wc -l` command
`ls | grep host` to find all file names that contain host

`free -m` to see the free memory space

Find the file itself rather than finding whats within files
`find /etc -name host*` where `/etc` is file path, `-name` is option and `host*` files that start with `host`

`yum install mlocate -y` to install another search command
`updatedb`
`locate host` is not a real time search, searches in the database that was created from `updatedb`