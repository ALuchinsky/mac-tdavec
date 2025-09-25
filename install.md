# Setup

`TDAvec.py` is available on `pypi`. To install it simply type

    pip install tdavec

into your environment. 

You can also install the current verion from the GitHub with

    pip install -e "git+https://github.com/uislambekov/TDAvec.git#egg=tdavec&subdirectory=python"

Alternatively, you can install it from the source. In order to do this clone mentioned above github repository and run the followin commants from the project root directory:


    pip install numpy==1.26.4 ripser==0.6.8
    python3 setup.py build_ext --inplace
    pip install .

after that you should have `tdavec` package installed in your environment. 


In order to check if the intallation process was completed, you can run python and evaluate the following lines:

    > from tdavec import test_package
    > X, D, PS = test_package()

This function will create a simple point cloud, build a persistence diagram, caclulate the Persistence Silhouette vectorization from it, and return these three objects.


# Installing on PyPi

Note that you have to have your API token created and saved to ~/.pypic file

    # cleaning
    rm -rf dist/ *.egg-info/
    rm mac_tdavec/*.so
    # build
    python -m build
    twine check dist/*
    # intall on testpypi
    pip install --index-url https://test.pypi.org/simple/ --no-deps mac_tdavec
