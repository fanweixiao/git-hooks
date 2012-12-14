# git hooks demo

## post-receive

hope this framework could simplify your git-hooks-writing-job

### `repos` file

may be you have many remote repos, iterate them in this file as a array for saving time.

### `post-receive` file

use `post-receive` as a **post-receive hub**, running all post-receive jobs. There are two ways run jobs:

- `echo "$input" | hooks/post-receive-three` will run `post-receive-three` script
- `for i in `ls hooks/post-receive-job-* 2>/dev/null`; do` will run all script which name start w/ **post-receive-job-**

### `post-receive-job` file

This hook script will execute proper command you want in senarios below:
+ git push origin new_branch_name
+ git push origin some_branch
+ git push origin :some_branch_to_be_delete
+ git push --tags
