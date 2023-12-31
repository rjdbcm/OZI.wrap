# OZI 0.1 meson.build:root_files,root_children
# Part of OZI.wrap.
# See LICENSE.txt in the project root for details.
# DO NOT EDIT BY HAND - This file was generated for use with OZI tools.
# ozi-fix -> meson rewrite is the standard editing pipeline.
project(
    'ozi-wrap',
    default_options: ['warning_level=3'],
    license: 'Apache-2.0 WITH LLVM-exception',
    license_files: ['LICENSE.txt'],
    meson_version: '>=1.1.0',
    version: run_command(
        'python3',
        [
            '-c',
            'from setuptools_scm import get_version;print(get_version(normalize=False))',
        ],
        check: true,
    ).stdout().strip(),
)
env = environment()
source_root = meson.current_source_dir()
build_root = meson.current_build_dir()
fs = import('fs')
pymod = import('python')
project_name = get_option('project-name').auto() ? meson.project_name() : 'todo'
build_dir = get_option('build-dir').auto() ? fs.stem(build_root) : 'todo'
source_to_build = (
    get_option('source-to-build').auto() ? configuration_data() : 'todo'
)
docs_source = get_option('docs-source').auto() ? 'subprojects/docs' : 'todo'
test_source = get_option('test-source').auto() ? 'tests' : 'todo'
dev = subproject('ozi')
foreach var : get_option('variables')
    name = var.replace('-', '_')
    set_variable(name, dev.get_variable(name))
endforeach
scm_version = run_command(
    python,
    ['-c', scm_version_snip],
    check: true,
).stdout().strip()
semantic_version = meson.project_version().split('.')
maj_version = semantic_version.get(0)
min_version = semantic_version.get(1)
pat_version = semantic_version.get(2)
configure_file(
    input: 'pyproject.toml',
    output: 'pyproject.toml',
    configuration: configuration_data(
        {
            'PROJECT_NAME': project_name,
            'MESON_DIST_FALLBACK_VERSION': '.'.join(
                maj_version,
                min_version,
                pat_version,
            ),
        },
    ),
)
root_files = [
    'README.rst',
    'CHANGELOG.md',
    'LICENSE.txt',
    'pyproject.toml',
    'PKG-INFO'
]
foreach source : root_files
    fs.copyfile(source)
endforeach
if false
    executable('root_files', root_files)
endif
root_children = [
    project_name.underscorify(),
    test_source,
]
foreach child: root_children
    subdir(child)
endforeach
if false
    executable('root_children', root_children)
endif