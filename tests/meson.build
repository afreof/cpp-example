#
# Copyright OpenEmbedded Contributors
#
# SPDX-License-Identifier: MIT
#

test_mesonex = executable('test-mesonex',
    'test-cpp-example.cpp',
    include_directories : inc,
    link_with : mesonexlib,
    install : true
)
test('meson example test', test_mesonex)
