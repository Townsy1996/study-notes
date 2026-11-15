Week 1: Bash Scripting basics and Git  GNU nano 6.2   

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
- Environment and tag will then be printed  GNU nano 6.2              

