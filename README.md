mks5
====

My ancient HTML/S5 based slide generation system.

You probably don't want to use this.

This is based on Ruby 1.8, RedCloth 3 (!), and lots of spit and
cellotape.

mks5 is the script for turning an input slide set into HTML.  You also
need the [S5](http://meyerweb.com/eric/tools/s5/) system to complete
this (and optionally [S6](http://tzi.org:2000) — yes, this stuff is
that old).

A slide set might look like this:

        =title. AWE: Agile Entwicklung
        =author. Carsten Bormann
        =presdate. 2010-02-16
        =company. TZI.org
        =revision. $Id: agile.sld,v 1.2 2010/02/15 23:04:40 cabo Exp $

        =slide.			AWE: Agile Entwicklung

        h2. Universität Bremen 2010-02-16

        h3. Carsten Bormann

        h4. cabo@tzi.org

        =slide.  Why Waterfall Projects Fail

        !>{width: 100px}.waterfall_2.jpg!

        !>350px-Waterfall_model.png!

        Prozesswissen:

        * oft implizit
        * nicht auf Abruf zu artikulieren<br/>
        (&#x2794; Process confabulation)

        Wasserfallmodell:

        * erfordert *vollständige* Erfassung von Anforderungen *vor* der Verfügbarkeit des Systems

        =slide.    Dokumente produzieren?

        Dokumente dienen zur *Kommunikation*.

        * zwischen Kunde und Entwicklern?

        * zwischen Entwicklern und Entwicklern?

        * zwischen Gegenwart und Zukunft?

The slides are written in [textile syntax](http://redcloth.org/textile) (RedCloth 3, alas).
Non-textile "commands" are lines starting with a `=`.
So, `=slide` starts a slide. `=(` and `=)` delimit code blocks, where
`=(` can be followed by a language name (for selection of syntax hightlighting).
`=<` and `=>` create a `div`, which can be right-aligned by adding `>`
after the `=<`; see the code for other parameters.
`=/` splits a slide into two (repeating the title with a counting
number).
`=#` leads in to a (rest of line) comment.
`=` with an identifier after it sets a parameter.
`==` stands for a line with a single `=` at the start (i.e., escapes
the `=`).
Read the code for the rest.
