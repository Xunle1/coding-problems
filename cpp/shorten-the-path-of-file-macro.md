# Shorten The Path Of File Macro

The `__FILE__` macro shows the absolute path of file, and it is too long.

```
file: /home/xxx/a/b/src/hello.cc
```

Shorten the path of `__FILE__` macro.

**Cmake**

```Cmake
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -D__FILENAME__='\"$(subst $(dir $<),,$<)\"'")
```

Using `__FILENAME__` instead of `__FILE__`.