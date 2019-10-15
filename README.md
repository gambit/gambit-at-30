# gambit-at-30

This repository contains the Gambit@30 talks and related documents.

Content
=======

Directory `talks` contains the PDFs of the talks.

Directory `mimosa` contains the compressed image of mimosa for running Gambit
on bare metal.  You can copy the image to a real IDE HDD and use it to boot a
real PC, or use the QEMU emulator like this:

    % gunzip -c mimosa.img.gz > mimosa.img
    % qemu-system-i386 -m 1G -hda mimosa.img

Once booted, here are some interesting things to type
at the Gambit REPL:

    > (current-directory)
    > (directory-files)
    > (load "fact.scm")
    > (load "fib.scm")             ;; run it interpreted
    > (compile-and-load "fib.scm") ;; run it compiled to x86
    > (load "x86-asm.scm")         ;; x86 assembler example
    > (load "x86-os.scm")          ;; read RTC with in/out instructions
    > (edit "fib.scm")             ;; save/exit with ESC key

The state of the filesystem is preserved in mimosa.img.  This includes
the REPL history and any files generated or edited with `(edit ...)`.
