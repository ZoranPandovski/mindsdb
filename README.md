<h1 align="center">
	<img width="300" src="https://github.com/mindsdb/mindsdb_native/blob/stable/assets/MindsDBColorPurp@3x.png?raw=true" alt="MindsDB">
	<br>

</h1>
<p align="center">
	<a href="https://github.com/mindsdb/mindsdb/actions"><img src="https://github.com/mindsdb/mindsdb/workflows/MindsDB%20workflow/badge.svg" alt="MindsDB workflow"></a>
  <a href="https://www.python.org/downloads/"><img src="https://img.shields.io/badge/python-3.6%20|%203.7|%203.8-brightgreen.svg" alt="Python supported"></a>
   <a href="https://pypi.org/project/MindsDB/"><img src="https://badge.fury.io/py/MindsDB.svg" alt="PyPi Version"></a>
  <a href="https://pypi.org/project/MindsDB/"><img src="https://img.shields.io/pypi/dm/mindsdb" alt="PyPi Downloads"></a>
  <a href="https://community.mindsdb.com/"><img src="https://img.shields.io/discourse/posts?server=https%3A%2F%2Fcommunity.mindsdb.com%2F" alt="MindsDB Community"></a>
  <a href="https://www.mindsdb.com/"><img src="https://img.shields.io/website?url=https%3A%2F%2Fwww.mindsdb.com%2F" alt="MindsDB Website"></a>	
</p>

MindsDB is an open-source AI layer for existing databases that allows you to effortlessly develop, train and deploy state-of-the-art machine learning models using SQL queries. [![Tweet](https://img.shields.io/twitter/url/http/shields.io.svg?style=social)](https://twitter.com/intent/tweet?text=Machine%20Learning%20in%20one%20line%20of%20code%21&url=https://www.mindsdb.com&via=mindsdb&hashtags=ai,ml,machine_learning,neural_networks)

<h2 align="center">
   Predictive AI layer for existing databases
   <br/>
  <img width="600" src="https://assets.website-files.com/5f500135c5852524c3845958/5f5024f70d3e5f408250a4a9_Mindsdb%20AI%20tables.gif" alt="MindsDB">	
</h2>


## Try it out

* [Installing MindsDB](https://docs.mindsdb.com/Installing/)
* [AI Tables](https://docs.mindsdb.com/databases/)
	* [AI Tables in MariaDB](https://docs.mindsdb.com/databases/MariaDB/)
	* [AI Tables in ClickHouse](https://docs.mindsdb.com/databases/Clickhouse/)
* [Learning from Examples](https://docs.mindsdb.com/tutorials/BasicExample/)
* [MindsDB Explainability GUI](http://mindsdb.com/product)
* [Frequently Asked Questions](https://docs.mindsdb.com/FAQ/)

### Installation


* **Desktop**: You can use MindsDB on your own computer in under a minute, if you already have a python environment setup, just run the following command:

```bash
 pip install mindsdb --user
```

>Note: Python 64 bit version is required. Depending on your environment, you might have to use `pip3` instead of `pip` in the above command.*

  If for some reason this fail, don't worry, simply follow the [complete installation instructions](https://docs.mindsdb.com/Installing/) which will lead you through a more thorough procedure which should fix most issues.

* **Docker**: If you would like to run it all in a container simply:  

```bash
sh -c "$(curl -sSL https://raw.githubusercontent.com/mindsdb/mindsdb/master/distributions/docker/build-docker.sh)"
```

## MindsDB AI tables demo using MariaDB (Video tutorial)

Please click on the image below to load the tutorial:

[![here](https://img.youtube.com/vi/a49CvkoOdfY/0.jpg)](https://www.youtube.com/watch?v=Tguat5jjD4g&feature=youtu.be)  

(Note: Please manually set it to 720p or greater to have the text appear clearly)

## Contributing

In order to make changes to mindsdb, the ideal approach is to fork the repository than clone the fork locally `PYTHONPATH`.

For example: `export PYTHONPATH=$PYTHONPATH:/home/my_username/mindsdb`.

Too test your changes you can run unit tests (fast) and CI tests (slightly longer) locally.

To run the unit tests:
* Install pytest: `pip install -r requirements_test.txt`
* Run: `pytest`

To run the CI tests: `cd tests/ci_tests && python3 full_test.py`

Once you have specific changes you want to merge into master, feel free to make a PR.

Due to some repository restructuring the "old" Mindsdb repository is now Mindsdb Native (https://github.com/mindsdb/mindsdb_native). This repository is the "old" Mindsdb Server repository, though from a user's perspective everything should work just the same.

Thanks for Max Stepanov (@StpMax) , Zoran Pandovski (@ZoranPandovski), Jorge Torres(@torrmal) for their contributions to Mindsdb Server, even though their contributions to those particular components may not show up in the commit history.

## Running mindsdb as a developer

1. Make your you have python3 and pip3 installed (one some environments pip3 might be called pip instead, if you don't have the `pip3` command just run `pip --version` and if it says something with `(python 3.x)` in there that means you can use that). The version of python3 should be > 3.4.

2. If you already installed mindsdb via pip uninstall it and all related mindsdb packages by running:

`pip3 uninstall mindsdb; pip3 uninstall mindsdb_native; pip3 uninstall lightwood; sudo pip3 uninstall mindsdb; sudo pip3 uninstall mindsdb_native; sudo pip3 uninstall lightwood;`

That should get rid of all local versions of mindsdb you have.

3. Pick a directory (here I'll call it `/home/my_user` and clone the repository you want to use there).

For mindsdb this would be `git clone git@github.com:mindsdb/mindsdb.git`
For native: `git clone git@github.com:mindsdb/mindsdb_native.git`
For lightwood: `git clone git@github.com:mindsdb/lightwood.git`

4. Install everything in the `requirements.txt` files of the project.

For mindsdb this would be `cd mindsdb && pip3 install -r requirements.txt --user`

5. Add the projects you want to use to your `PYTHONPATH` env variable by running:

`export PYTHONPATH=/home/my_user/mindsdb` (replace `mindsdb` with `mindsdb_native` and `lightwood` for those packages)

If you want to use multiple projects at once you can add `:` between the directories to pythonpath, e.g.

`export PYTHONPATH=/home/my_user/mindsdb_native:/home/my_user/lightwood:/home/my_user/mindsdb`

Add that same `export` command in a new line at the end of your `~/.bashrc` files to have this exported when the computer boots up in all terminals.

6. Note, when running a script importing these libraries or running them as a python module (e.g. `python3 -m mindsdb`) make sure you are in a directory other than `/home/my_user` or `/home/my_user/package_name` (where `package_name` is mindsdb, lightwood or mindsdb_native). Otherwise the python importer will fail to properly import them

7. If you want to install a version of mindsdb, lightwood ... etc from pip, do it in a virtualenv where you run `export PYTHONPATH=''`, otherwise the `PYTHONPATH` exports will override the version installed via pip

## Report Issues

Please help us by [reporting any issues](https://github.com/mindsdb/mindsdb/issues/new/choose) you may have while using MindsDB.

## License

* [MindsDB License](https://github.com/mindsdb/mindsdb/blob/master/LICENSE)
