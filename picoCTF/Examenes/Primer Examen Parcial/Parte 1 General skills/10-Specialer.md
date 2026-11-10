## Descripción
Reception of Special has been cool to say the least. That's why we made an exclusive version of Special, called Secure Comprehensive Interface for Affecting Linux Empirically Rad, or just 'Specialer'. With Specialer, we really tried to remove the distractions from using a shell. Yes, we took out spell checker because of everybody's complaining. But we think you will be excited about our new, reduced feature set for keeping you focused on what needs it the most. Please start an instance to test your very own copy of Specialer. `ssh -p 16516 ctf-player@chatelaine.cylabacademy.net`. The password is `647e170e`

1.- What programs do you have access to?
## Solución
```
```
┌──(kali㉿kali)-[~]
└─$ ssh -p 16516 ctf-player@chatelaine.cylabacademy.net 
The authenticity of host '[chatelaine.cylabacademy.net]:16516 ([18.227.187.235]:16516)' can't be established.
ED25519 key fingerprint is: SHA256:TMzuFX+tQxG+rVL0CK63ywMGkWGIsWZEgT7sWWAVfMg
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:4: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? 647e170e
Please type 'yes', 'no' or the fingerprint: yes
Warning: Permanently added '[chatelaine.cylabacademy.net]:16516' (ED25519) to the list of known hosts.
ctf-player@chatelaine.cylabacademy.net's password: 
Specialer$ help
GNU bash, version 5.2.21(1)-release (x86_64-pc-linux-gnu)
These shell commands are defined internally.  Type `help' to see this list.
Type `help name' to find out more about the function `name'.
Use `info bash' to find out more about the shell in general.
Use `man -k' or `info' to find out more about commands not in this list.

A star (*) next to a name means that the command is disabled.

 job_spec [&]                                                                                                         history [-c] [-d offset] [n] or history -anrw [filename] or history -ps arg [arg...]
 (( expression ))                                                                                                     if COMMANDS; then COMMANDS; [ elif COMMANDS; then COMMANDS; ]... [ else COMMANDS; ] fi
 . filename [arguments]                                                                                               jobs [-lnprs] [jobspec ...] or jobs -x command [args]
 :                                                                                                                    kill [-s sigspec | -n signum | -sigspec] pid | jobspec ... or kill -l [sigspec]
 [ arg... ]                                                                                                           let arg [arg ...]
 [[ expression ]]                                                                                                     local [option] name[=value] ...
 alias [-p] [name[=value] ... ]                                                                                       logout [n]
 bg [job_spec ...]                                                                                                    mapfile [-d delim] [-n count] [-O origin] [-s count] [-t] [-u fd] [-C callback] [-c quantum] [array]
 bind [-lpsvPSVX] [-m keymap] [-f filename] [-q name] [-u name] [-r keyseq] [-x keyseq:shell-command] [keyseq:readl>  popd [-n] [+N | -N]
 break [n]                                                                                                            printf [-v var] format [arguments]
 builtin [shell-builtin [arg ...]]                                                                                    pushd [-n] [+N | -N | dir]
 caller [expr]                                                                                                        pwd [-LP]
 case WORD in [PATTERN [| PATTERN]...) COMMANDS ;;]... esac                                                           read [-ers] [-a array] [-d delim] [-i text] [-n nchars] [-N nchars] [-p prompt] [-t timeout] [-u fd] [name ...]
 cd [-L|[-P [-e]] [-@]] [dir]                                                                                         readarray [-d delim] [-n count] [-O origin] [-s count] [-t] [-u fd] [-C callback] [-c quantum] [array]
 command [-pVv] command [arg ...]                                                                                     readonly [-aAf] [name[=value] ...] or readonly -p
 compgen [-abcdefgjksuv] [-o option] [-A action] [-G globpat] [-W wordlist] [-F function] [-C command] [-X filterpa>  return [n]
 complete [-abcdefgjksuv] [-pr] [-DEI] [-o option] [-A action] [-G globpat] [-W wordlist] [-F function] [-C command>  select NAME [in WORDS ... ;] do COMMANDS; done
 compopt [-o|+o option] [-DEI] [name ...]                                                                             set [-abefhkmnptuvxBCEHPT] [-o option-name] [--] [-] [arg ...]
 continue [n]                                                                                                         shift [n]
 coproc [NAME] command [redirections]                                                                                 shopt [-pqsu] [-o] [optname ...]
 declare [-aAfFgiIlnrtux] [name[=value] ...] or declare -p [-aAfFilnrtux] [name ...]                                  source filename [arguments]
 dirs [-clpv] [+N] [-N]                                                                                               suspend [-f]
 disown [-h] [-ar] [jobspec ... | pid ...]                                                                            test [expr]
 echo [-neE] [arg ...]                                                                                                time [-p] pipeline
 enable [-a] [-dnps] [-f filename] [name ...]                                                                         times
 eval [arg ...]                                                                                                       trap [-lp] [[arg] signal_spec ...]
 exec [-cl] [-a name] [command [argument ...]] [redirection ...]                                                      true
 exit [n]                                                                                                             type [-afptP] name [name ...]
 export [-fn] [name[=value] ...] or export -p                                                                         typeset [-aAfFgiIlnrtux] name[=value] ... or typeset -p [-aAfFilnrtux] [name ...]
 false                                                                                                                ulimit [-SHabcdefiklmnpqrstuvxPRT] [limit]
 fc [-e ename] [-lnr] [first] [last] or fc -s [pat=rep] [command]                                                     umask [-p] [-S] [mode]
 fg [job_spec]                                                                                                        unalias [-a] name [name ...]
 for NAME [in WORDS ... ] ; do COMMANDS; done                                                                         unset [-f] [-v] [-n] [name ...]
 for (( exp1; exp2; exp3 )); do COMMANDS; done                                                                        until COMMANDS; do COMMANDS-2; done
 function name { COMMANDS ; } or name () { COMMANDS ; }                                                               variables - Names and meanings of some shell variables
 getopts optstring name [arg ...]                                                                                     wait [-fn] [-p var] [id ...]
 hash [-lr] [-p pathname] [-dt] [name ...]                                                                            while COMMANDS; do COMMANDS-2; done
 help [-dms] [pattern ...]                                                                                            { COMMANDS ; }
Specialer$ echo *
abra ala sim
Specialer$ echo */*
abra/cadabra.txt abra/cadaniel.txt ala/kazam.txt ala/mode.txt sim/city.txt sim/salabim.txt
Specialer$ echo "$(<ala/kazam.txt)"
return 0 academy{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_221ea859}
Specialer$ Connection to chatelaine.cylabacademy.net closed by remote host.
Connection to chatelaine.cylabacademy.net closed.


academy{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_221ea859}
```
```

## Notas Adicionales

## Referencias
-