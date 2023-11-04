# OZI 0.1 meson.build:test_files,test_children
# Part of OZI.wrap.
# See LICENSE.txt in the project root for details.
# DO NOT EDIT BY HAND - This file was generated for use with OZI tools.
# ozi-fix -> meson rewrite is the standard editing pipeline.
config_files = []
foreach file: config_files
  fs.copyfile(file)
  python.install_sources(file, subdir: 'ozi-wrap'/'tests')
endforeach
if false
  executable('test_files', config_files)
endif
children = []
foreach child: children
    subdir(child)
endforeach
if false
    executable('test_children', children)
endif