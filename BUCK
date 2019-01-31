load('//:subdir_glob.bzl', 'subdir_glob')

cxx_library(
  name = 'draco',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('src', 'draco/**/*.h'),
  ]),
  srcs = glob([
    'src/**/*.cc'  
  ], exclude = glob([
    'src/**/*_test.cc',
    'src/**/*_test_*.cc',
    'src/**/*_tests.cc',
    'src/**/*_plugin.cc',
    'src/**/tools/*.cc',
    'src/draco/javascript/**/*.cc',
  ])),
  compiler_flags = [
    '-std=c++14',
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_binary(
  name = 'draco-decoder',
  srcs = ['src/draco/tools/draco_decoder.cc'],
  deps = [':draco'],
  visibility = ['PUBLIC'],
)

cxx_binary(
  name = 'draco-encoder',
  srcs = ['src/draco/tools/draco_encoder.cc'],
  deps = [':draco'],
  visibility = ['PUBLIC'],
)
