## texmf directory - user files for TeX

see an overview of tex related paths and variables with 
tlmgr conf --only-installed

TeX related things are in a couple places:
/usr/local/texlive - the installation directory
/Library/TeX - binaries and documentation
/Applications/TeX - where to install GUI applications (like LaTeXit)
~/texmf -  user global style and bib files (changed from macOS default of ~/Library/texmf)

install packages with 
[sudo] tlmgr install [--dry-run] [pkg]

change location of this directory with 
[sudo] tlmgr conf texmf TEXMFHOME=[path]
(normally it's stored under ~/Library/texmf in mac)
the file that this writes to is /usr/local/texlive/2020basic/texmf.cnf

directory for global .sty, .cls, .bib, .bst files, the order for searching is
/usr/local/texlive/2016/texmf
/usr/local/texlive/2016/texmf-dist
/usr/local/texlive/texmf-local

the first two are managed by the install, the second is local to all users 
on the computer

this directory is specific to a user, the path to be searched can be found at
tlmgr conf | grep 'TEXMFHOME'

place .sty, .cls files in [texmf]/tex/latex 
place .bib, .bst files in [texmf]/bibtex/bib
