# ModuleNotFoundError: No module named '_lzma'

간혹 Ubuntu에서 Python을 apt로 설치하지 않고 wget으로 설치해서 make 할 시. APT에 등록되지 않은 기본 라이브러리들이 설치가 안되는경우가 있따. 

```
burin@boss-WS-C621E-SAGE-Series:/data/workspace/AICoverGen$ python3.9 src/webui.py
Traceback (most recent call last):
  File "/data/workspace/AICoverGen/src/webui.py", line 10, in <module>
    from main import song_cover_pipeline
  File "/data/workspace/AICoverGen/src/main.py", line 12, in <module>
    import librosa
  File "/home/burin/.local/lib/python3.9/site-packages/librosa/__init__.py", line 209, in <module>
    from . import core
  File "/home/burin/.local/lib/python3.9/site-packages/librosa/core/__init__.py", line 5, in <module>
    from .convert import *  # pylint: disable=wildcard-import
  File "/home/burin/.local/lib/python3.9/site-packages/librosa/core/convert.py", line 7, in <module>
    from . import notation
  File "/home/burin/.local/lib/python3.9/site-packages/librosa/core/notation.py", line 8, in <module>
    from ..util.exceptions import ParameterError
  File "/home/burin/.local/lib/python3.9/site-packages/librosa/util/__init__.py", line 78, in <module>
    from .files import *  # pylint: disable=wildcard-import
  File "/home/burin/.local/lib/python3.9/site-packages/librosa/util/files.py", line 11, in <module>
    import pooch
  File "/home/burin/.local/lib/python3.9/site-packages/pooch/__init__.py", line 19, in <module>
    from .processors import Unzip, Untar, Decompress
  File "/home/burin/.local/lib/python3.9/site-packages/pooch/processors.py", line 14, in <module>
    import lzma
  File "/home/burin/Documents/Python-3.9.0/Lib/lzma.py", line 27, in <module>
    from _lzma import *
ModuleNotFoundError: No module named '_lzma'
```



아래 링크를 참조해서 pip를 설치 한 후 

https://support.huawei.com/enterprise/en/doc/EDOC1100289998/db0db8f0/modulenotfounderror-no-module-named-_lzma-

make를 다시해주면 됨