# okaru-archive: archive manager de OKARU. Se compila contra el núcleo instalado (paquete okaru-core).
project('okaru-archive', 'cpp',
  version: files('VERSION'),
  meson_version: '>=1.1',
  default_options: ['cpp_std=c++23', 'cpp_extensions=false', 'warning_level=0', 'b_ndebug=if-release'],
)

# El núcleo y sus bibliotecas son privados (/usr/lib/okaru): se enlazan con su ruta en el binario.
_okaru_libdir = get_option('prefix') / get_option('libdir') / 'okaru'
_deps = [dependency('okaru-apps'), dependency('libarchive'), dependency('libsecret-1')]
_inc = include_directories('src')
_args = ['-Wall', '-Wextra', '-Wno-missing-field-initializers', '-Wpedantic', '-Wconversion', '-Wshadow']

executable('okaru-archive',
  sources: files('src/apps/archive/archive_backend.cpp', 'src/apps/archive/archive_window.cpp', 'src/apps/archive/main.cpp'),
  include_directories: _inc,
  dependencies: _deps,
  cpp_args: _args,
  install_rpath: _okaru_libdir,
  install: true,
)

# Sus textos, que el núcleo busca en /usr/share/okaru/apps/archive/translations.
install_subdir('apps/archive/translations', install_dir: get_option('datadir') / 'okaru' / 'apps' / 'archive')
install_data('assets/dev.okaru.Archive.desktop', install_dir: get_option('datadir') / 'applications')

if get_option('tests').allowed()
  test('okaru_archive', executable('okaru_archive_test',
    sources: files('tests/okaru_archive_test.cpp', 'src/apps/archive/archive_backend.cpp'),
    include_directories: _inc,
    dependencies: _deps,
    build_rpath: _okaru_libdir,
    override_options: ['b_ndebug=false'],
  ))
endif
