project('bx', 'cpp', version : '1.0.0', license: 'BSD 2-Clause', default_options : ['cpp_std=c++14'])

includes = ['include', '3rdparty']

libplatform = host_machine.system()

thread_dep 			= dependency('threads')
dl_dep     			= meson.get_compiler('c').find_library('dl', required : false)
dep_appleframeworks = dependency('appleframeworks', modules : ['CoreFoundation', 'Foundation'])

cpp_args = [

]

deps = [
  thread_dep,
  dl_dep,
  dep_appleframeworks,
]

if libplatform == 'darwin'
  includes += 'include/compat/osx'
endif

# if libplatform == 'linux'
#   includes += 'include/compat/freebsd'
# endif

if libplatform == 'windows'
  includes += 'include/compat/mingw'
endif

src = ['src/amalgamated.cpp']

lib = static_library(
  'libbx',
  src,
  include_directories : includes,
  dependencies: deps,
  cpp_args: cpp_args,
)

bx_dep = declare_dependency(include_directories : includes, link_with: lib)
