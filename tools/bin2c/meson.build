src = [
  'bin2c.cpp',
]

includes = [

]

dependencies = [
  bx_dep,
]

# if host_machine.system() == 'darwin'
# 	appleframeworks_dep = dependency('appleframeworks', modules : ['Metal', 'QuartzCore', 'Cocoa'])
# 	dependencies += appleframeworks_dep
# endif

bin2c_exe = executable(
  'bin2c',
  src,
  include_directories: includes,
  dependencies: dependencies
)
