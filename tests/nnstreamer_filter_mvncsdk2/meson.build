unittest_mvncsdk_helper = shared_library('mvncsdk_test',
  ['NCSDKTensorFilterTestHelper.cc'],
  dependencies : [glib_dep, gst_base_dep, gst_dep, nnstreamer_unittest_deps],
  install: get_option('install-test'),
  install_dir: nnstreamer_libdir
)

unittest_mvncsdk_helper_dep = declare_dependency(
  link_with: unittest_mvncsdk_helper,
)

unittest_mvncsdk_deps = [
  nnstreamer_unittest_deps,
  gst_base_dep,
  unittest_mvncsdk_helper_dep,
]

unittest_mvncsdk = executable('unittest_filter_mvncsdk2',
    ['unittest_filter_mvncsdk2.cc'],
    dependencies: unittest_mvncsdk_deps,
    install: get_option('install-test'),
    install_dir: unittest_install_dir
  )

filter_mvncsdk2_testenv = environment()
filter_mvncsdk2_testenv.set('GST_PLUGIN_PATH', path_gst_plugin)
filter_mvncsdk2_testenv.set('NNSTREAMER_CONF', path_nns_conf)
filter_mvncsdk2_testenv.set('NNSTREAMER_FILTERS', path_nns_plugin_filters)
filter_mvncsdk2_testenv.set('NNSTREAMER_DECODERS', path_nns_plugin_decoders)
filter_mvncsdk2_testenv.set('NNSTREAMER_CONVERTERS', path_nns_plugin_converters)
filter_mvncsdk2_testenv.set('NNSTREAMER_SOURCE_ROOT_PATH', meson.source_root())
filter_mvncsdk2_testenv.set('LD_LIBRARY_PATH', meson.current_build_dir())

test('unittest_filter_mvncsdk2', unittest_mvncsdk, env: filter_mvncsdk2_testenv)
