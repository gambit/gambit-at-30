# gambit-at-30

This repository contains the Gambit@30 talks and related documents.

Content
=======

Directory `talks` contains the PDFs of the talks, which are useful to
view simultaneously with the videos of the presentations:

  - Gambit30-History: https://youtu.be/bGqEO1Dm48k
  - Gambit30-Forensics: https://youtu.be/IcZnZuhDvWI
  - Gambit30-GVM: https://youtu.be/MNuDqF4tt24
  - Gambit30-UnivBE: https://youtu.be/CmzKMUudefk
  - Gambit30-Gamboling: https://youtu.be/RAYbI8FmtTA
  - Gambit30-NativeBE: https://youtu.be/t4jkDDGiTfc
  - Gambit30-BareMetal: https://youtu.be/2q6-dq_wsSY
  - Gambit30-Geiser: https://youtu.be/PpulgwWo1gQ
  - Gambit30-Modules: https://youtu.be/VKQAW4G5EnI
  - Gambit30-Gerbil: https://youtu.be/zuqzy_-KmkA
  - Gambit30-Yownu: https://youtu.be/6K8hvt-ugKI
  - Gambit30-Together: https://youtu.be/whWkw89DbgI
  - Gambit30-Compiler: https://youtu.be/FjrUpIg8M7o

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
