# EGCL readtable iterator

This branch uses `EGCL-EXT:MAP-READTABLE-MACRO-CHARACTERS` to enumerate reader
macros without scanning the Unicode character space. It requires EGCL with
that extension (tested on 0.0.10, b94618ece). Other implementations retain
their existing iterators. Upstream: https://github.com/melisgl/named-readtables.

Run `egcl --no-init --load egcl-smoke.lisp` from this directory with it first
in ASDF's source registry. The test checks named table creation, ordinary
reading, Unicode macro characters, dispatch entries, nonterminating flags,
and empty dispatch tables through MERGE-READTABLES-INTO.

The original implementation exceeded a 20-second wall-clock cap loading the
library. The adapter loads and passes these checks within the same cap.
Full upstream suite unrun. Tracking: bliss-5egpd and bliss-yhct8.1.
