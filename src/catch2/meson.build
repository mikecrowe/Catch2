# TODO:
# - support choosing C++17 and turning on appropriate catch_user_config options


conf_data = configuration_data()
conf_data.set('CATCH_CONFIG_DEFAULT_REPORTER', 'console')
conf_data.set('CATCH_CONFIG_CONSOLE_WIDTH', '80')
conf_data.set('miketest', 'wibble')

configure_file(input: 'catch_user_config.hpp.in',
               output: 'catch_user_config.hpp',
               format: 'cmake@',
#               install: true,
               configuration: conf_data)

sources = [
  'catch_approx.cpp',
  'internal/catch_assertion_handler.cpp',
  'catch_assertion_result.cpp',
  'internal/catch_clara.cpp',
  'internal/catch_commandline.cpp',
  'internal/catch_source_line_info.cpp',
  'catch_config.cpp',
  'internal/catch_case_insensitive_comparisons.cpp',
  'internal/catch_console_colour.cpp',
  'internal/catch_context.cpp',
  'internal/catch_debug_console.cpp',
  'internal/catch_debugger.cpp',
  'internal/catch_enforce.cpp',
  'internal/catch_enum_values_registry.cpp',
  'internal/catch_exception_translator_registry.cpp',
  'internal/catch_fatal_condition_handler.cpp',
  'internal/catch_floating_point_helpers.cpp',
  'internal/catch_istream.cpp',
  'interfaces/catch_interfaces_generatortracker.cpp',
  'interfaces/catch_interfaces_reporter.cpp',
  'internal/catch_list.cpp',
  'matchers/catch_matchers_floating_point.cpp',
  'matchers/catch_matchers_quantifiers.cpp',
  'matchers/catch_matchers_string.cpp',
  'matchers/catch_matchers_templated.cpp',
  'catch_message.cpp',
  'internal/catch_output_redirect.cpp',
  'catch_registry_hub.cpp',
  'internal/catch_random_number_generator.cpp',
  'internal/catch_random_seed_generation.cpp',
  'internal/catch_reporter_registry.cpp',
  'internal/catch_reporter_spec_parser.cpp',
  'internal/catch_result_type.cpp',
  'internal/catch_run_context.cpp',
  'internal/catch_section.cpp',
  'internal/catch_stdstreams.cpp',
  'catch_session.cpp',
  'internal/catch_singletons.cpp',
  'internal/catch_reusable_string_stream.cpp',
  'internal/catch_stringref.cpp',
  'internal/catch_string_manip.cpp',
  'internal/catch_tag_alias_registry.cpp',
  'catch_test_case_info.cpp',
  'internal/catch_test_case_registry_impl.cpp',
  'internal/catch_test_case_tracker.cpp',
  'internal/catch_test_registry.cpp',
  'internal/catch_textflow.cpp',
  'catch_test_spec.cpp',
  'internal/catch_test_spec_parser.cpp',
  'catch_timer.cpp',
  'catch_tostring.cpp',
  'catch_totals.cpp',
  'catch_version.cpp',
  'internal/catch_wildcard_pattern.cpp',
  'internal/catch_xmlwriter.cpp',
  'internal/catch_test_case_info_hasher.cpp',
  'generators/catch_generators_random.cpp',
  'generators/catch_generator_exception.cpp',
  'generators/catch_generators.cpp',
  'matchers/catch_matchers.cpp',
  'matchers/catch_matchers_container_properties.cpp',
  'matchers/catch_matchers_exception.cpp',
  'matchers/catch_matchers_predicate.cpp',
  'matchers/internal/catch_matchers_impl.cpp',
  'catch_tag_alias_autoregistrar.cpp',
  'internal/catch_decomposer.cpp',
  'internal/catch_errno_guard.cpp',
  'internal/catch_lazy_expr.cpp',
  'internal/catch_leak_detector.cpp',
  'internal/catch_message_info.cpp',
  'internal/catch_polyfills.cpp',
  'internal/catch_startup_exception_registry.cpp',
  'internal/catch_uncaught_exceptions.cpp',
  'interfaces/catch_interfaces_capture.cpp',
  'interfaces/catch_interfaces_config.cpp',
  'interfaces/catch_interfaces_exception.cpp',
  'interfaces/catch_interfaces_registry_hub.cpp',
  'interfaces/catch_interfaces_reporter_factory.cpp',
  'interfaces/catch_interfaces_reporter_registry.cpp',
  'interfaces/catch_interfaces_testcase.cpp'
]

install_headers([])

catch2 = static_library(
  'Catch2',
  sources,
  include_directories : '..',
  dependencies : [],
  install : true)
catch2_with_main = static_library(
  'Catch2Main',
  [ 'internal/catch_main.cpp' ],
  include_directories : '..',
  dependencies : [],
  install : true)

catch2_pkg = pkg.generate(
  filebase: 'catch2',
  name : 'Catch2',
  libraries : catch2,
  version : meson.project_version(),
  description : 'A modern, C++-native, test framework for C++14 and above',
  url: 'https://github.com/catchorg/Catch2',
)

pkg.generate(
  filebase : 'catch2-with-main',
  name : 'Catch2-With-Main',
  libraries : catch2_with_main,
  version : meson.project_version(),
  description : 'A modern, C++-native, test framework for C++14 and above (links in default main)',
  requires : 'catch2'
)



