# ops
Bash shell scripting framework/library that provides:
* Command grouping in code blocks called *op(s)*
* Command displaying before execution
* Summary in a tree structure
* Remote execution (ssh, docker, arch-chroot)
* Error handling and policies

## Limitations
* Cannot undo/override:
  * `set -o pipefail`
  * `shopt -s extdebug`
  * `stty -echoctl`
  * `trap 'o_abort' INT`
  * `trap 'o_err op' ERR`
  * `trap 'o_debug' DEBUG`
* Cannot use global names that start with "o_"
* Cannot use subshells $() `` in op(){} arguments

## TODO
* envr selection: cmd or env arg in apply and plan cmds
* ops paths / relative paths
* bug usr source traps
* bug don't display uncalled commands as skipped
* impl hide argument to ops to hide header
* impl parallel execution
* impv session stack?
