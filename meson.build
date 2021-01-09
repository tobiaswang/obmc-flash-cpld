project(
    'obmc-flash-cpld', 
    'cpp',
    default_options: [
          'cpp_std=c++17'
        ],
    version: '0.1',
)

boost_args = [
        '-DBOOST_ASIO_DISABLE_THREADS',
        '-DBOOST_ALL_NO_LIB',
        '-DBOOST_SYSTEM_NO_DEPRECATED',
        '-DBOOST_ERROR_CODE_HEADER_ONLY',
        '-DBOOST_COROUTINES_NO_DEPRECATION_WARNING'
]

cpp = meson.get_compiler('cpp')

boost_asio_dep = dependency('boost', modules : ['system', 'coroutine', 'date_time', 'thread'])
sdbusplus_dep = dependency('sdbusplus')
systemd_dep = dependency('libsystemd')
deps = [
        boost_asio_dep,
        sdbusplus_dep,
        systemd_dep
]

executable(
    'obmc-flash-cpld', 
    'flash-cpld.cpp',  
    cpp_args: boost_args,
    dependencies: deps,
    install:true,
    install_dir: get_option('bindir')
)