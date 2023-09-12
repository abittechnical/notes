### Modules vs. Packages

 A __package__ is a collection of Python _modules_ while a __module__ is a ___single Python file___.

> Any directory with an `__init__.py` file is considered a Python package. The different modules in the package are imported in a similar manner as plain modules, but with a special behavior for the `__init__.py` file, which is used to gather all package-wide definitions.
>
> A file `modu.py` in the directory `pack/` is imported with the statement `import pack.modu`. **This statement will look for an `__init__.py` file in `pack`, execute all of its top-level statements. Then it will look for a file named `pack/modu.py` and execute all of its top-level statements**. After these operations, any variable, function, or class defined in `modu.py` is available in the pack.modu namespace. [^1][package-structure][THHGP]



> Note that when using `from package import item`, the item can be either a submodule (or subpackage) of the package, or some other name defined in the package, like a function, class or variable. The `import`statement first tests whether the item is defined in the package; if not, it assumes it is a module and attempts to load it. If it fails to find it, an [`ImportError`](https://docs.python.org/3/library/exceptions.html#ImportError) exception is raised.
>
> Contrarily, when using syntax like `import item.subitem.subsubitem`, each item except for the last must be a package; the last item can be a module or a package but can’t be a class or function or variable defined in the previous item.
>
> ...
>
> ###### importing * from a package
>
> The `import` statement uses the following convention:
>
> If a package's `__init__.py` code defines a list named `__all__`, it is taken to be the list of module names that should be imported when `from package import *` is encountered [^2][python-packages][DOC]



###### site-package locations

> These are the directories that contain any third-party Python modules which you may have installed( __including any written by you__ )

### Details of module distribution 

[![Python Packagin From Init to Deploy](http://img.youtube.com/vi/4fzAMdLKC5k/0.jpg)](http://www.youtube.com/watch?v=4fzAMdLKC5k)



 ###### Types

__Distribution Package__: This package is a single compressed file that contains everything required to install our module into site-packages

- Source Distribution [__sdist__]
  > _Contains python source and any c extensions. When installed by user the code is run to install_
- Built Distribution [__bdist_wheel__ (__!__bdist_egg)]



1. __Create a distribution description__

   - Requires creating a _minimum_ of two descriptive files for our module:
     - `setup.py` : describes the module in detail
     -  `README.txt` 

   > This identifies the module we want `setuptools` to install

2. __Generate a distribution file__:

   > Using Python at the command line, we'll create a shareable distribution file to contain our module's code

3. __Install the distribution file__:

   > Using Python cli, install the distribution file (which includes our module ) into __site-packages__ 

---

###### References

[^1]: [ excerpt from _The Hitchhiker's Guide to Python_]
[^2]: [from python docs entry on packages]



[THHGP]: https://docs.python-guide.org/writing/structure/#packages
[DOC]: https://docs.python.org/3/tutorial/modules.html#packages