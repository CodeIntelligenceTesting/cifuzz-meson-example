project('tutorial', 'cpp')

# make ENV variables set by cifuzz accessible as meson variables
cmd = run_command('sh', '-c', 'echo $FUZZ_TEST_CFLAGS')
FUZZ_TEST_CFLAGS = cmd.stdout().strip().strip('\'')
cmd = run_command('sh', '-c', 'echo $FUZZ_TEST_LDFLAGS')
FUZZ_TEST_LDFLAGS = cmd.stdout().strip().strip('\'')
cmd = run_command('sh', '-c', 'echo $CFLAGS')
CFLAGS = cmd.stdout().strip().strip('\'').split(' ')
cmd = run_command('sh', '-c', 'echo $LDFLAGS')
LDFLAGS = cmd.stdout().strip().strip('\'').split(' ')

add_global_arguments(CFLAGS, language: 'cpp')
add_global_link_arguments(LDFLAGS, language: 'cpp')

subdir('src')

executable('demo', 'main.cpp', link_with: explore_me_shared_lib)

executable('my_fuzz_test', 'my_fuzz_test.cpp', 
link_with: [explore_me_shared_lib], 
cpp_args: [FUZZ_TEST_CFLAGS],
link_args: FUZZ_TEST_LDFLAGS
)