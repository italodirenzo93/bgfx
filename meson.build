project('bgfx', ['cpp', 'objcpp'])

bx_dep = dependency('bx', fallback: ['bx', 'bx_dep'])
bimg_dep = dependency('bimg', fallback: ['bimg', 'bimg_dep'])

sys_os = host_machine.system()

if sys_os == 'darwin'
	sources = ['src/amalgamated.mm']
else
	sources = ['src/amalgamated.cpp']
endif

bgfx = library(
	'bgfx',
	sources,
	include_directories: include_directories('include'),
	dependencies: [
		bx_dep,
		bimg_dep
	]
)

bgfx_dep = declare_dependency(
	include_directories: include_directories('include'),
	link_with: bgfx,
	dependencies: [
		bx_dep,
		bimg_dep
	]
)
