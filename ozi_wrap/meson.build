# OZI 0.1 meson.build:source_files,source_children
# Part of OZI.wrap.
# See LICENSE.txt in the project root for details.
# DO NOT EDIT BY HAND - This file was generated for use with OZI tools.
# ozi-fix -> meson rewrite is the standard editing pipeline.
source_files = [
    '__init__.py',
]
python_files = source_files
foreach file: source_files
    python_files += file+'i'
endforeach
python_files += ['py.typed']
foreach file: python_files
    fs.copyfile(file)
    python.install_sources(file, subdir: 'ozi-wrap')
endforeach
if false
    executable('source_files', source_files)
endif
source_children = []
foreach child: source_children
    subdir(child)
endforeach
if false
    executable('source_children', source_children)
endif