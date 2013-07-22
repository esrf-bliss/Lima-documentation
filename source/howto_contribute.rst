Prerequisite
============


For collaborative development, we use the "Fork & Pull" model from github.com. So anyone who wants to contribute needs an account on github.com. Then you need to fork the project you want to contribute.


| If you want to contribute with a new camera plug-in you should first request us (by email @ lima@esrf.fr) to get the new
| plug-in camera sub-module created. We will provide:

 - a default structure of directories (<mycamera>/src /include sip/ doc/ python/ test/)
 - the Makefile files (<mycamera>/Makefile, <mycamera>/src/Makefile, <mycamera>/test/Makefile)
 - templates files (src and include) for the mandatory classes: 

  - <MyCamera>Interface
  - <MyCamera>DetInfoCtrlObj 
  - <MyCamera>SyncCtrlObj

 - a standard .gitignore file
 - a template index.rst for the documentation

 In addition we will update with new entries other files needed to compile the plugin library and the python module:

 - Lima/config.inc_default
 - Lima/camera/Makefile 
 - build/Makefile
 - sip/Makefile
 - sip/configure.py

  As above do not forget to fork the new sub-module project.


Create a github account
```````````````````````

This is an easy task, you have to go to `Sign up - Github`_

  .. _Sign up - Github: https://github.com/signup/free

Fork a project
``````````````

On the `github`_ site, It is far better explained than we could do ;)

   .. _github: https://help.github.com/articles/fork-a-repo

Contribute guideline
====================

It is very simple to contribute, you should follow the steps below. 

 1. Branch

  First of all you have to create a branch for a new feature or for a bug fix, use an explicit
  branch name, for instance "soleil_video_patch" .

 2. Code/patch
 
  | If it's a patch from an existing module, respect and keep the coding style of the previous programmer (indentation,variable naming,end-line...).
  | If you're starting a new camera project, you've just to respect few rules:

    - Class member must start with '**m\_**'
    - Class method must be in **CamelCase**
    - You must define the camera's namespace

 3. Commit
 
  | Do as many commit as you need with clear comments.
  | Prefer an atomic commit with a single change rather than a huge commit with too many changes.

 4. Pull Request

  Then submit a `pull request`_

     .. _pull request: https://help.github.com/articles/using-pull-requests

   | At this stage you have to wait, we need sometimes to accept or reject your request.
   | So there are two possible issues:

    1. The Pull-request is accepted:

    we merge your branch with the the main project master branch, then everything is fine and you can
    now synchronize your forked project with the main project.
  
    2. The pull-request is rejected:
    
    The pull request could be rejected if:

      - the new code doesn't compile
      - it breaks backward compatibility
      - the python wrapping is missing or not updated
      - the commit log message doesn't describe what you actually do
    
      In case of a new camera plug-in sub-module the first pull request will be rejected if:

      - as above
      - the documentation is missing or if it does not fit with the guidelines (e.i :ref:`guidelines`)

      We will tell you (github interface and/or email)  about the reason and we will give some advises
      to improve your next tentative of pull-request.
      
      | So at this point you have to loop to item 2 (Code/Patch) again.
      | Good luck !!


..  LocalWords:  namespace repo Github github
