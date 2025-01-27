# DevOps Day 4
- [DevOps Day 4](#devops-day-4)
    - [Linux](#linux)
    - [Environment Variables](#environment-variables)
      - [Basic Commands](#basic-commands)

### Linux

* mv = move & rename
* cp = copy
* rm = remove
* -r = before command to select entire directory
* cat = displays content in files
* rmdir = remove directory (only if contents are empty) 
* rm -rf = remove directory if folder has content (not advised)
* head = use number of lines you want to display from top (ex: head -2 goku.text)
* tail = use number of lines you want to display from bottom (ex: tail -2 goku.text)
* nl = displays number of lines
* | = pipe symbol. outputs first bit
* grep = highlights where specified line appears
  * e.g: cat goku.txt | grep saiyan
* ./ = to run file
  * e.g: if i have a file named provision.sh, run using:
    * ./provision.sh
   * you may need permissions to run. this can be done with:
      * chmod +x then the name of the script:
        * chmod +x provision.sh

### Environment Variables

* Environment variables are dynamic values that affect how processes and applications run in the Git Bash terminal. They store information like file paths, configuration settings, or system details.
* Global variables: Available across all processes in the system.
* Local variables: Available only in the current session or script.
Case Sensitivity:
* In Git Bash, environment variable names are case-sensitive (e.g., PATH ≠ path).

#### Basic Commands


* View All Variables:
  * env
* Print a Variable:
  * echo $VARIABLE_NAME
* Set/Export a Variable:
  * export VARIABLE_NAME=value
* Remove a Variable:
  * unset VARIABLE_NAME
  
