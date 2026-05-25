# ETOOMANYFUNCTIONS

Un autre challenge de la catégorie reverse fournissait un exécutable linux nommé ``etoomanyfinction``.

## Résolution du challenge

On ouvre le fichier dans Ghidra. On se rend compte qu'il y a au moins des centaines de fonction. Cool.



![image](function-fun.png)

En regardant la première fonction appelée après l'entrée du programme, on remarque qu'elle affiche le flag d'elle-même après un if.

![image](function-ifunpatched.png)

Pourquoi s'embêter à tout lire alors qu'on pourrait simplement patcher ce if afin de toujours tomber sur l'affichage du flag ? Le saut conditionnel vers le flag est remplacé par un saut inconditionnel.

![image](function-ifunpatchedassembly.png)
Avant.
![image](function-ifpatchedassembly.png)
Après.

En appelant simplement le programme après le patch, le flag apparaît : ``BZHCTF{100k_func_aint_too_many_4_u}``.

![image](function-end.png)

