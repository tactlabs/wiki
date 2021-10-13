# Updating Packages in PyPi

- Make sure you have maintainer or owner access to a project repository
- git clone the source code repo
- make necessary changes to source code
- update version number
- build wheel:

```
pip install realpython-reader twine

python setup.py sdist bdist_wheel
```

- Check if Wheel has been built without errors or warnings:

```
twine check dist/*
```

- Upload to the PyPi Project Repo:

```
twine upload --repository-url https://upload.pypi.org/legacy/ dist/*
```

- Check if Changes have been updated on https://pypi.org/project/prettymetrics/