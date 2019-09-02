# mytools
 a tools just for me

remember to push before commit
if you directly commit, all changes would be staged and automatically commit, so if you want to make another change, you have to go over again to make a comment before commit.

## update 9/2/2019

 nothing new except i have done some testing on the last version so the pycache might be different, that is.

one important discovery is that you can not import a function that is included in a class, the functions that can be imported are those outside of the class.

in our cases, path_convert() is located inside the class "string", so it cannot be imported. if the path_convert() was written outside the "string", it could be imported by:
 from mytools.mytools import path_convert

 or:

 from mytools import path_convert.

 the differences btw the above two import syntax lies in the order import searches from its path: the mytools file has a __init__.py, which says from .mytools import string, that is, the import first enter the __init__.py and found out that string should be imported from mytools.py not the mytools file.

 when using mytools.mytools, the import directly open the mytools.py from mytools file and import string directly.

 You can import both packages and modules. (Note that importing a package essentially imports the package’s __init__.py file as a module.) file also means package


    Syntax and Practical Examples
    Let’s say you have the following directory structure:

    └── project
        ├── package1
        │   ├── module1.py
        │   └── module2.py
        └── package2
            ├── __init__.py
            ├── module3.py
            ├── module4.py
            └── subpackage1
                └── module5.py
    There’s a directory, project, which contains two sub-directories, package1 and package2. The package1 directory has two files, module1.py and module2.py.

    The package2 directory has three files: two modules, module3.py and module4.py, and an initialization file, __init__.py. It also contains a directory, subpackage, which in turn contains a file, module5.py.

    Let’s assume the following:

    package1/module2.py contains a function, function1.
    package2/__init__.py contains a class, class1.
    package2/subpackage1/module5.py contains a function, function2.
    The following are practical examples of absolute imports:

    from package1 import module1
    from package1.module2 import function1
    from package2 import class1
    from package2.subpackage1.module5 import function2