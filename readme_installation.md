# Hints for Installation

* first create and activate python venv
* then install with `pip install -r requirements.txt`
  * Note: `torch_scatter` might fail, cause require `torch` titself -> in this case install e.g. `torch` first and then complete requirement
* `torch_lydorn` and `lydorn_utils` are not pypi packes, and are included here as git submodules. Thus have to be installed differently
  * e.g. with `pip install ./pytorch_lydorn` and `pip install ./lydorn_utils`
  * Note: if still functions missing - hacky fix for full installation below
    * If the submodule exists in your repository but is missing in the virtual environment, copy it over, e.g. `cp -r $HOME/repos/Polygonization-by-Frame-Field-Learning/pytorch_lydorn/torch_lydorn /path/to/venv/lib/python3.10/site-packages/`
    * Reinstall the Package in Editable Mode: To avoid such issues in the future, reinstall the `torch_lydorn` package in editable mode so that changes in your local repository are reflected in the virtual environment:
      ```
      pip uninstall torch-lydorn
      pip install -e $HOME/repos/Polygonization-by-Frame-Field-Learning/pytorch_lydorn
      ```
* `osgeo` not available in python venv (even though GDAL installed):
  * check local GDAL version e.g. `gdalinfo --version`
  * install same GDAL with pip within python venv: `pip install GDAL==x.x.x`
