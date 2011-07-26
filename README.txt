Introduction
============

This is a package that shows a bug in Plone 4.1 / plone.app.discussion. If an add-on package contains 'Products.CMFPlone' in its dependencies, the dicussion workflows are missing after a Plone site has been created.

Trac ticket / bug report: http://dev.plone.org/plone/ticket/12058

Steps to reproduce
------------------

1) Create a Plone 4.1 buildout

  $ paster create -t plone3_buildout (Plone 4.1)

2) Create a new plone package (Register GS Profile: True; This is important!)

  $ paster create -t plone example.breakpad 

3) Add 'Products.CMFPlone', to install_requires

4) Add '<includeDependencies package="." />' to configure.zcml

5) Create a new Plone site (no need to install the example.breakpad package)

6) Go to the types control panel and you will see the error message: 

   * Module plone.app.discussion.browser.controlpanel, line 128, in settings
   IndexError: tuple index out of range l
