# pip install h5py

환경 파이썬 3.7

발생 원인: pip install 중 발생 HDF5모듈을 찾을 수 없음

실행 커맨드: pip install h5py

에러 로그:

```jsx
error: subprocess-exited-with-error

  × Building wheel for h5py (pyproject.toml) did not run successfully.
  │ exit code: 1
  ╰─> [71 lines of output]
      running bdist_wheel
      running build
      running build_py
      creating build
      creating build\\lib.win32-3.7
      creating build\\lib.win32-3.7\\h5py
      copying h5py\\h5py_warnings.py -> build\\lib.win32-3.7\\h5py
      copying h5py\\ipy_completer.py -> build\\lib.win32-3.7\\h5py
      copying h5py\\version.py -> build\\lib.win32-3.7\\h5py
      copying h5py\\__init__.py -> build\\lib.win32-3.7\\h5py
      creating build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\attrs.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\base.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\compat.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\dataset.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\datatype.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\dims.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\files.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\filters.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\group.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\selections.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\selections2.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\vds.py -> build\\lib.win32-3.7\\h5py\\_hl
      copying h5py\\_hl\\__init__.py -> build\\lib.win32-3.7\\h5py\\_hl
      creating build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\common.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\conftest.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_attribute_create.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_attrs.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_attrs_data.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_base.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_big_endian_file.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_completions.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_dataset.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_dataset_getitem.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_dataset_swmr.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_datatype.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_dimension_scales.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_dims_dimensionproxy.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_dtype.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_errors.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_file.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_file2.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_file_image.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_filters.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_group.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_h5.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_h5d_direct_chunk.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_h5f.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_h5o.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_h5p.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_h5pl.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_h5t.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_objects.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_selections.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\test_slicing.py -> build\\lib.win32-3.7\\h5py\\tests
      copying h5py\\tests\\__init__.py -> build\\lib.win32-3.7\\h5py\\tests
      creating build\\lib.win32-3.7\\h5py\\tests\\data_files
      copying h5py\\tests\\data_files\\__init__.py -> build\\lib.win32-3.7\\h5py\\tests\\data_files
      creating build\\lib.win32-3.7\\h5py\\tests\\test_vds
      copying h5py\\tests\\test_vds\\test_highlevel_vds.py -> build\\lib.win32-3.7\\h5py\\tests\\test_vds
      copying h5py\\tests\\test_vds\\test_lowlevel_vds.py -> build\\lib.win32-3.7\\h5py\\tests\\test_vds
      copying h5py\\tests\\test_vds\\test_virtual_source.py -> build\\lib.win32-3.7\\h5py\\tests\\test_vds
      copying h5py\\tests\\test_vds\\__init__.py -> build\\lib.win32-3.7\\h5py\\tests\\test_vds
      copying h5py\\tests\\data_files\\vlen_string_dset.h5 -> build\\lib.win32-3.7\\h5py\\tests\\data_files
      copying h5py\\tests\\data_files\\vlen_string_dset_utc.h5 -> build\\lib.win32-3.7\\h5py\\tests\\data_files
      copying h5py\\tests\\data_files\\vlen_string_s390x.h5 -> build\\lib.win32-3.7\\h5py\\tests\\data_files
      running build_ext
      Loading library to get build settings and version: hdf5.dll
      error: Unable to load dependency HDF5, make sure HDF5 is installed properly
      error: [WinError 126] 지정된 모듈을 찾을 수 없습니다
      [end of output]
note: This error originates from a subprocess, and is likely not a problem with pip.
  ERROR: Failed building wheel for h5py
Failed to build h5py
ERROR: Could not build wheels for h5py, which is required to install pyproject.toml-based projects
```

pip 는 원래 하위 모듈에 있는 패키지들을 자동으로 다운받는데 HDF5 모듈 자체가 pip 에 없고 Conda만 존재해서 conda를 설치 후 HDF5를 인스톨을 했다

그랬더니

```jsx
Loading library to get build settings and version: hdf5.dll
      error: Unable to load dependency HDF5, make sure HDF5 is installed properly
      error: [WinError 193] %1은(는) 올바른 Win32 응용 프로그램이 아닙니다
      [end of output]

  note: This error originates from a subprocess, and is likely not a problem with pip
```

다른 에러 로그가 떳다 ...

찾아보니 로컬에 환경변수가 엉망이였다 파이썬도 3.7 32bit로 설치 되어있었다

64비트로 업데이트서 설치하니 정상적으로 설치 됨

결론 conda target인 hdf5 문제로 인해 설치 오류임.