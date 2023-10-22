#
# Copyright OpenEmbedded Contributors
#
# SPDX-License-Identifier: MIT
#


subdir('cpp-example-lib')

mesonexlib = shared_library('mesonexlib',
    'cpp-example-lib.cpp',
    include_directories : inc,
	version: meson.project_version(),
	soversion: meson.project_version().split('.')[0],
    dependencies : jsoncdep,
    install : true
)

executable('mesonex',
    'cpp-example.cpp',
    link_with : mesonexlib,
    install : true
)
