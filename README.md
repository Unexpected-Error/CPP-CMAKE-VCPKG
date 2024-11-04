# CPP CMAKE VCPKG

## Common

Update these files with project Names/Descriptions

1. vcpkg.json
2. CMakeLists

Uncomment some items in .gitignore


## VCPKG

### Install vcpkg


1. Pick a directory you want to install in and cd into it
2. git clone vcpkg, and run its install script
3. Add vcpkg to path OR add a symbolic link to vcpkg/vcpkg

```
git clone https://github.com/microsoft/vcpkg.git
cd vcpkg && ./bootstrap-vcpkg.sh -disableMetrics

# Optional (Can just add vcpkg to Path)
ln -s /path/to/vckpg/vckpg /usr/local/bin/vcpkg
```

#### Add vcpkg to project
1. create CMakeUserPresets.json in root directory, and update to point to your install

<details open>
    <summary>CMakeUserPresets.json</summary>
    
    {
        "version": 6,
        "configurePresets": [
            {
            "name": "default",
            "inherits": "vcpkg",
            "environment": {
                "VCPKG_ROOT": "/Path/To/vcpkg/install"
                }
            }
        ]
    }
    
</details>

## CMAKE

use your favorite package manager

`sudo port -t install cmake`
`brew install cmake`

or download [here](https://cmake.org/download/)

Then set cmake to use our default preset

`cmake --preset=default`


## Using


### Dependencies

`vcpkg add port fmt`
Add any required CMake targets to CMakeLists.txt (in this case `target_link_libraries(Endorphin PRIVATE fmt::fmt)`)


### Building

Make sure to configure the correct preset
`cmake --preset=default`


After that, enjoy

`CMake --build .`
`./build/<Name>`

