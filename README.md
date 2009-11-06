# Leiningen

    "Leiningen!" he shouted. "You're insane! They're not creatures you can
    fight--they're an elemental--an 'act of God!' Ten miles long, two
    miles wide--ants, nothing but ants! And every single one of them a
    fiend from hell...
    -- from Leiningen Versus the Ants by Carl Stephenson

Leiningen is a build tool for Clojure designed to not set your hair on fire.

## Install

For now, you will need http://p.hagelb.org/leiningen-deps.tar unpacked
in the root and http://p.hagelb.org/lancet.clj on the classpath.

## Usage

    $ lein deps # install dependencies in lib/

    $ lein test [PRED] # run the project's tests, optionally filtered on PRED

    $ lein compile # ahead-of-time compile into classes/

    $ lein repl # launch a REPL with the project classpath configured

TODO: jar, uberjar, swank, new, help, deploy

## Configuration

Place a build.clj file in the project root that looks something like this: 

    (defproject leiningen
      :version "1.0-SNAPSHOT"
      :dependencies [["org.clojure" "clojure" "1.1.0-alpha-SNAPSHOT"]
                     ["org.clojure" "clojure-contrib" "1.0-SNAPSHOT"]
                     ["org.clojure" "lancet" "1.0-SNAPSHOT"]
                     ["org.apache.ant" "ant" "1.7.1"]
                     ["org.apache.ant" "ant-launcher" "1.7.1"]
                     ["org.apache.maven" "maven-ant-tasks" "2.0.10"]])

## FAQ

**Q:** How do you pronounce Leiningen?  
**A:** It's LINE-ing-en. I think.

**Q:** What does this offer over [Lancet](http://github.com/stuarthalloway/lancet)?  
**A:** Lancet is more of a library than a build tool. It doesn't predefine
   any tasks apart from what Ant itself offers, so there is nothing
   Clojure-specific there. In addition, Leiningen includes some Maven
   functionality for dependencies.

**Q:** But Maven is terrifying!  
**A:** That's not a question. Anyway, Leiningen only uses the dependency
   resolution parts of Maven, which are quite tame. For the actual
   task execution cycles it uses Ant under the covers via Lancet.

**Q:** But Ant is terrifying!  
**A:** That's [true](http://www.defmacro.org/ramblings/lisp.html). Ant is
   an interpreter for a [procedural language with a regrettable 
   syntax](http://blogs.tedneward.com/2005/08/22/When+Do+You+Use+XML+Again.aspx).
   But if you're able to write it with a more pleasing syntax, it's
   not so bad.

**Q:** What happened to [Corkscrew](http://github.com/technomancy/corkscrew)?  
**A:** I tried, but I really couldn't make the wine metaphor work. That,
   and the Plexus Classworlds container was an ornery beast causing
   much frustration.

**Q:** What about Windows?  
**A:** Patches welcome.

## License

Copyright (C) 2009 Phil Hagelberg

Distributed under the Eclipse Public License, the same as Clojure
uses. See the file COPYING.
