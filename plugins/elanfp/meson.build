if gusb.found()
cargs = ['-DG_LOG_DOMAIN="FuPluginElanfp"']

plugin_quirks += files('elanfp.quirk')
plugin_builtins += static_library('fu_plugin_elanfp',
  sources: [
    cfu_rs[1], # header
    'fu-elanfp-plugin.c',
    'fu-elanfp-device.c',
    'fu-elanfp-firmware.c'  # fuzzing
  ],
  include_directories: [
    plugin_incdirs,
    plugincfu_incdir,
  ],
  link_with: [
    plugin_libs,
    plugin_builtin_cfu,
  ],
  c_args: cargs,
  dependencies: plugin_deps,
)
endif
