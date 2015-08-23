# Branches #

After each new feature release of the forum plugin, a quality assurance branch for it is opened in the repository. The name of this branch starts with "QA" and is followed by the first two digits of the release number separated by underscores. For example, after the release of forum 2.8.0, it's quality assurance branch will be called QA\_2\_8.

In this example, the QA\_2\_8 branch will be used to develop the 2.8.1 version and the default branch will be used to develop the next feature release, 2.9.0.

_**The QA branches are meant for urgent bugfixes and security fixes only. Any features and non-urgent fixes should be committed to the "default" branch.**_


# How to commit an urgent bugfix to the forum repository #

First check-out the Quality Assurance branch:

**`hg update -c QA_2_8`**

Now apply your bugfix:

**`*`hack`*` `*`hack`*` `*`hack`*`**

Commit it:

**`hg commit`**

Now go back to the default branch:

**`hg update -c default`**

Merge in the bugfix:

**`hg merge QA_2_8`**

And now commit the merge:

**`hg commit`**

That's it, you have committed your super-urgent bugfix to both the Quality Assurance branch and the Feature Release branch. Well done!

More information on named branches from the official mercurial documentation: http://mercurial.selenic.com/wiki/NamedBranches

**_IMPORTANT:_** Never merge the "default" branch into a "Quality Assurance" branch. It will make people's life very difficult!!!!!