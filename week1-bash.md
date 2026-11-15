Week 1: Bash Scripting basics and Git  GNU nano 6.2              week1-bash.md *

1. Log Parser: Started with a simple log parsing script. You in>
of ERROR, WARN and INFO there are.
- Used if-fi validation checks e.g. -z flag would check if inpu>
- Learnt about 'positional parameters', "$1", "$2" .... holds t>
- For loop in Bash in combination with grep -c command ( -c fla>
- >&2 sending error messages to stderr rather than stdout, usef>

Good first script, made some mistakes for example echo being ou>

2. Directory Archive: Takes two inputs, first being source dire>
- Again made use of validation checks if-fi, $# -ne 2 checks fo>
- Splitting the bath using dirname and basename, wrapping that >
- Used tar -czf, -c create, -z compress with gzip and -f being >
- On success, message is printed with the archive path
- Finally, using find command I checked the destination directo>

Would be good to make retention period its own variable

3. Health Checker: Takes a URL as a parameter, performs a curl >
- Saved the status code as a variable -- curl -s -o /dev/null ->
Simple but effective script

4. Deploy: Takes two parameters; environment and tag
- By using a case statement for environment it forces only 3 po>
- For tag validation, using a regex pattern to again force comp>
- Finally, if input env was "prod" script would print confirmat>
- Environment and tag will then be printed  GNU nano 6.2              week1-bash.md *

1. Log Parser: Started with a simple log parsing script. You in>
of ERROR, WARN and INFO there are.
- Used if-fi validation checks e.g. -z flag would check if inpu>
- Learnt about 'positional parameters', "$1", "$2" .... holds t>
- For loop in Bash in combination with grep -c command ( -c fla>
- >&2 sending error messages to stderr rather than stdout, usef>

Good first script, made some mistakes for example echo being ou>

2. Directory Archive: Takes two inputs, first being source dire>
- Again made use of validation checks if-fi, $# -ne 2 checks fo>
- Splitting the bath using dirname and basename, wrapping that >
- Used tar -czf, -c create, -z compress with gzip and -f being >
- On success, message is printed with the archive path
- Finally, using find command I checked the destination directo>

Would be good to make retention period its own variable

3. Health Checker: Takes a URL as a parameter, performs a curl >
- Saved the status code as a variable -- curl -s -o /dev/null ->
Simple but effective script

4. Deploy: Takes two parameters; environment and tag
- By using a case statement for environment it forces only 3 po>
- For tag validation, using a regex pattern to again force comp>
- Finally, if input env was "prod" script would print confirmat>
- Environment and tag will then be printed  GNU nano 6.2              week1-bash.md *

1. Log Parser: Started with a simple log parsing script. You in>
of ERROR, WARN and INFO there are.
- Used if-fi validation checks e.g. -z flag would check if inpu>
- Learnt about 'positional parameters', "$1", "$2" .... holds t>
- For loop in Bash in combination with grep -c command ( -c fla>
- >&2 sending error messages to stderr rather than stdout, usef>

Good first script, made some mistakes for example echo being ou>

2. Directory Archive: Takes two inputs, first being source dire>
- Again made use of validation checks if-fi, $# -ne 2 checks fo>
- Splitting the bath using dirname and basename, wrapping that >
- Used tar -czf, -c create, -z compress with gzip and -f being >
- On success, message is printed with the archive path
- Finally, using find command I checked the destination directo>

Would be good to make retention period its own variable

3. Health Checker: Takes a URL as a parameter, performs a curl >
- Saved the status code as a variable -- curl -s -o /dev/null ->
Simple but effective script

4. Deploy: Takes two parameters; environment and tag
- By using a case statement for environment it forces only 3 po>
- For tag validation, using a regex pattern to again force comp>
- Finally, if input env was "prod" script would print confirmat>
- Environment and tag will then be printed  GNU nano 6.2              week1-bash.md *

1. Log Parser: Started with a simple log parsing script. You in>
of ERROR, WARN and INFO there are.
- Used if-fi validation checks e.g. -z flag would check if inpu>
- Learnt about 'positional parameters', "$1", "$2" .... holds t>
- For loop in Bash in combination with grep -c command ( -c fla>
- >&2 sending error messages to stderr rather than stdout, usef>

Good first script, made some mistakes for example echo being ou>

2. Directory Archive: Takes two inputs, first being source dire>
- Again made use of validation checks if-fi, $# -ne 2 checks fo>
- Splitting the bath using dirname and basename, wrapping that >
- Used tar -czf, -c create, -z compress with gzip and -f being >
- On success, message is printed with the archive path
- Finally, using find command I checked the destination directo>

Would be good to make retention period its own variable

3. Health Checker: Takes a URL as a parameter, performs a curl >
- Saved the status code as a variable -- curl -s -o /dev/null ->
Simple but effective script

4. Deploy: Takes two parameters; environment and tag
- By using a case statement for environment it forces only 3 po>
- For tag validation, using a regex pattern to again force comp>
- Finally, if input env was "prod" script would print confirmat>
- Environment and tag will then be printed

Overview: I set out to learn some basic Bash to get more comfortable writing automation scripts.
I created a few scripts that would be useful when I start to work on my Game Review Site project that I started a 
few months ago.

1. Log Parser: Started with a simple log parsing script. You input a logfile and the script will count how many instances
of ERROR, WARN and INFO there are. 
- Used if-fi validation checks e.g. -z flag would check if input variable is not present
- Learnt about 'positional parameters', "$1", "$2" .... holds the values given in command line 
- For loop in Bash in combination with grep -c command ( -c flag being "count" ).
- >&2 sending error messages to stderr rather than stdout, useful if output of script is being redirected to another file for example, ./log_parser file.log > result.txt

Good first script, made some mistakes for example echo being outside for loop so only first ERROR count was printed

2. Directory Archive: Takes two inputs, first being source directory, second is destination directory. Script will take the source dir and be archived using tar command. In addition, checks if any archives are older than 7 days and deletes them
- Again made use of validation checks if-fi, $# -ne 2 checks for two arguments -ne = not equal. ! -d checking if parameter given is NOT a directory 
- Splitting the bath using dirname and basename, wrapping that in "$()" executes the command saves it in a variable just to tidy up the file name of the archive
- Used tar -czf, -c create, -z compress with gzip and -f being the file name, wrapping this in an if means branch depends on tar exit status 
- On success, message is printed with the archive path 
- Finally, using find command I checked the destination directory for any fies (-f) with -name backup_*.tar.gz -mtime +7 -delete, delete any file matching that file name pattern older than 7 days

Would be good to make retention period its own variable 

3. Health Checker: Takes a URL as a parameter, performs a curl on it and checks it status code, if 2xx then print success else print error
- Saved the status code as a variable -- curl -s -o /dev/null -w "%{http_code}" and then used -ge && -lt 200 to 300
Simple but effective script 

4. Deploy: Takes two parameters; environment and tag
- By using a case statement for environment it forces only 3 possible values, dev, test and prod 
- For tag validation, using a regex pattern to again force compliance v.0-10,0-10 etc 
- Finally, if input env was "prod" script would print confirmation message making sure user wants to proceed
- Environment and tag will then be printed 
