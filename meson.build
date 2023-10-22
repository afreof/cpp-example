#
# Copyright OpenEmbedded Contributors
#
# SPDX-License-Identifier: MIT
#

project('meson-example', 'cpp',
    version: '1.0.0',
    license : 'MIT',
    default_options: ['cpp_std=c++17']
    )


jsoncdep = dependency('json-c')

inc = include_directories('src')

subdir('src')
subdir('tests')
