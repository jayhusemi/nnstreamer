if get_option('enable-edgetpu')
  unittest_edgetpu_deps = [
    nnstreamer_unittest_deps,
    gst_base_dep,
  ]
  unittest_edgetpu = executable('unittest_edgetpu',
    ['unittest_edgetpu.cc'],
    dependencies: unittest_edgetpu_deps,
    install: get_option('install-test'),
    install_dir: unittest_install_dir
  )

  test('unittest_edgetpu', unittest_edgetpu, env: testenv)
endif
