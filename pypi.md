# PyPI

Brief guide to publish/release packages to PyPI. Credit: https://www.youtube.com/watch?v=GIF3LaRqgXo

## Setup

1. [Choose a license.](https://choosealicense.com/)
2. Add build files to `.gitignore`, at least:
   ```
   build/
   dist/
   *.egg-info/
   ```
3. Create `setup.py`.
   ```python
   from setuptools import setup

   with open("README.md", "r") as f:
       readme = f.read()
   
   setup(
       name="package",  # PyPI name, must be available
       version="0.0.1",
       description="A useful description.",
       long_description=readme,
       long_description_content_type="text/markdown",
       py_modules=["mymodule"],  # actual module name used in imports
       package_dir={"": "src"},  # root directory of source code
       classifiers=[  # add applicable classifiers, see https://pypi.org/classifiers/
           "Programming Language :: Python :: 3",
           "Programming Language :: Python :: 3.6",
           "Programming Language :: Python :: 3.7",
           "Programming Language :: Python :: 3.8",
           "Programming Language :: Python :: 3.9",
           "License :: OSI Approved :: MIT License",
           "Operating System :: OS Independent"
       ],
       install_requires=[
           "dependency1~=1.7",
           "dependency2~=3.14"
       ],
       url="https://github.com/author/repo",
       author="name",
       author_email="name@email.com"
   )
   ```
4. Ensure folder structure.
   ```
   .
   ├── src
   │   └── my_module.py
   ├── .gitignore
   ├── LICENSE
   ├── README.md
   └── setup.py
   ```
5. Install `check-manifest` to include all repository files in source distribution tarball.
   ```bash
   $ pip install check-manifest
   $ check-manifest --create
   $ git add MANIFEST.in
   ```
6. Build.
   ```bash
   $ python setup.py bdist_wheel sdist
   ```
7. Push to PyPI.
   ```bash
   $ pip install twine
   $ twine upload dist/*
   ```

## Update/Release

1. Check dependencies in `setup.py`.
2. Update version number in `setup.py`.
3. Update `MANIFEST.in`.
   ```bash
   $ check-manifest --update
   ```
4. Re-build.
   ```bash
   $ python setup.py bdist_wheel sdist
   ```
5. Push to PyPI.
   ```bash
   $ twine upload dist/*
   ```