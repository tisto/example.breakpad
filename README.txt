Introduction
============

1) Create a Plone 4.1 buildout

  $ paster create -t plone3_buildout (Plone 4.1)

2) Create a new plone package (Register GS Profile: True; This is important!)

  $ paster create -t plone example.breakpad 

3) Add 'Products.CMFPlone', to install_requires

4) Add '<includeDependencies package="." />' to configure.zcml