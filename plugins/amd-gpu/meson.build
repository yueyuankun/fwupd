if get_option('plugin_amdgpu').disable_auto_if(not gudev.found() or not amdgpu).allowed()
cargs = ['-DG_LOG_DOMAIN="FuPluginAmdGpu"']

plugin_quirks += files('amd-gpu.quirk')
plugin_builtins += static_library('fu_plugin_amd_gpu',
  rustgen.process(
    'fu-amd-gpu-atom.rs',          # fuzzing
    'fu-amd-gpu-psp.rs',           # fuzzing
  ),
  sources: [
    'fu-amd-gpu-plugin.c',
    'fu-amd-gpu-device.c',
    'fu-amd-gpu-psp-firmware.c',
    'fu-amd-gpu-atom-firmware.c',
  ],
  include_directories: plugin_incdirs,
  link_with: plugin_libs,
  c_args: cargs,
  dependencies: plugin_deps,
)
endif
