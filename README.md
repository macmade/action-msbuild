action-msbuild
==============

[![Issues](http://img.shields.io/github/issues/macmade/action-msbuild.svg)](https://github.com/macmade/action-msbuild/issues)
![Status](https://img.shields.io/badge/status-active-brightgreen.svg)
![License](https://img.shields.io/badge/license-mit-brightgreen.svg)
[![Contact](https://img.shields.io/badge/contact-@macmade-blue.svg)](https://twitter.com/macmade)  
[![Donate-Patreon](https://img.shields.io/badge/donate-patreon-yellow.svg)](https://patreon.com/macmade)
[![Donate-Gratipay](https://img.shields.io/badge/donate-gratipay-yellow.svg)](https://www.gratipay.com/macmade)
[![Donate-Paypal](https://img.shields.io/badge/donate-paypal-yellow.svg)](https://paypal.me/xslabs)

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
