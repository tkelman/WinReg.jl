# WinReg.jl

[![Build status](https://ci.appveyor.com/api/projects/status/4v53ctinmukaljbe?svg=true)](https://ci.appveyor.com/project/simonbyrne/winreg-jl)

Julia interface to the Windows registry.

## Usage

At the moment, this just exports one function, `querykey`, which queries the Windows registry.

```julia
querykey(base, path, valuename)
```
where
* `base` is one of the base paths:
 * `WinReg.HKEY_CLASSES_ROOT`
 * `WinReg.HKEY_CURRENT_USER`
 * `WinReg.HKEY_LOCAL_MACHINE`
 * `WinReg.HKEY_USERS`
 * `WinReg.HKEY_PERFORMANCE_DATA`
 * `WinReg.HKEY_CURRENT_CONFIG`
 * `WinReg.HKEY_DYN_DATA`

* `path` is the the path from `base` to the desired key
* `valuename` is the name of the value to retrieve

## Example

```julia
using WinReg

querykey(WinReg.HKEY_LOCAL_MACHINE,"System\\CurrentControlSet\\Control\\Session Manager\\Environment","PROCESSOR_ARCHITECTURE")
```

If further functionality is required, please open an issue.
