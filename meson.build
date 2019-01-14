project('fxc2', 'cpp')

if host_machine.system() != 'windows' or not host_machine.cpu_family().startswith('x86')
  error('only compilation for windows i686/x86_64 is supported')
endif

executable(
  'fxc2',
  'fxc2.cpp',
  override_options : [
    'b_lundef=false',
    'b_asneeded=false'
  ],
  link_args: ['-static'],
  install: true
)

d3dcompiler_dll = []
if host_machine.cpu_family() == 'x86'
  d3dcompiler_dll += 'dll/d3dcompiler_47_32.dll'
else
  d3dcompiler_dll += 'dll/d3dcompiler_47.dll'
endif

install_data(d3dcompiler_dll,
  rename: ['d3dcompiler_47.dll'],
  install_dir : 'bin'
)
