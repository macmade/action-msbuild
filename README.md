action-msbuild
==============

[![Issues](http://img.shields.io/github/issues/macmade/action-msbuild.svg?logo=github)](https://github.com/macmade/action-msbuild/issues)
![Status](https://img.shields.io/badge/status-active-brightgreen.svg?logo=git)
![License](https://img.shields.io/badge/license-mit-brightgreen.svg?logo=open-source-initiative)  
[![Contact](https://img.shields.io/badge/follow-@macmade-blue.svg?logo=twitter&style=social)](https://twitter.com/macmade)
[![Sponsor](https://img.shields.io/badge/sponsor-macmade-pink.svg?logo=github-sponsors&style=social)](https://github.com/sponsors/macmade)

### About

GitHub Action for msbuild.

**Usage**:

    - uses: macmade/action-msbuild@v1.0.0

**Matrix configuration**:

  - **platform**: `String`  
    The target architecture.
    
  - **toolset**: `String`  
    The architecture of the compiler toolchain (eg `x64`, `x86`).
    
  - **configuration**: `String`  
    The configuration to use.
    
  - **solution**: `String`  
    The Visual Studio solution to build.  
    
**Complete example**:

    name:   ci
    on:     [push]
    jobs:
        ci:
            runs-on: windows-latest
            strategy:
                matrix:
                    run-config:
                        - { platform: 'x64', toolset: 'x64', configuration: 'Debug',   solution: 'App.sln' }
                        - { platform: 'x86', toolset: 'x64', configuration: 'Release', solution: 'App.sln' }
            steps:
                - uses: actions/checkout@v1
                - uses: macmade/action-msbuild@v1.0.0

License
-------

Project is released under the terms of the MIT License.

Repository Infos
----------------

    Owner:          Jean-David Gadina - XS-Labs
    Web:            www.xs-labs.com
    Blog:           www.noxeos.com
    Twitter:        @macmade
    GitHub:         github.com/macmade
    LinkedIn:       ch.linkedin.com/in/macmade/
    StackOverflow:  stackoverflow.com/users/182676/macmade
