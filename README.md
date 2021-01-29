# misc-notes
miscellaneous tactics to fight the incurable

### Use Python 3 instead of 2 when a .py file is double-clicked on Windows

This may be needed when you first install Python 3, and then Python 2 on Windows.

Run `regedit` and find `HKEY_CLASSES_ROOT\Python.File\Shell\open\command`. Set the value to `"C:\Windows\py.exe" "%1" %*` instead of `"C:\Python27\python.exe" "%1" %*`. With the setting you can associate your double-click action with the default version used by `py.exe`, the Python launcher. Alternatively, use values like `"C:\Python37\pythonw.exe" "%1" %*` to set a fixed version.

You may also change the value of `HKEY_CLASSES_ROOT\Python.File\DefaultIcon` to `C:\Program Files\Python37\DLLs\py.ico`. Do not forget that you may by the way change the `DefaultIcon` of other `HKEY_CLASSES_ROOT\Python.*`

Alternatively, watch your registry with `FileTypesMan` http://www.nirsoft.net/utils/file_types_manager.html. Find the `.py` association and open the registry from `FileTypesMan`, or directly edit the registry with `FileTypesMan`.

Reference: https://superuser.com/questions/606916/windows-insists-associating-py-files-with-the-wrong-version-of-python

### Google Colaboratory using Python 2 and potentially Tensorflow 1

https://colab.research.google.com/notebook#create=true&language=python2