runtime_sources = ['explore_me.cpp', 'explore_me.h']

explore_me_static_lib = static_library('runtime', runtime_sources, install: true)
explore_me_shared_lib = shared_library('runtime', runtime_sources, install: true, override_options: ['b_lundef=false'])

# conflict between shared_library() or shared shared_module()
# only one can be used
# explore_me_shared_module = shared_module('runtime', runtime_sources, install: true)