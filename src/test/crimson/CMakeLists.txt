add_executable(unittest_seastar_buffer
  test_buffer.cc)
add_ceph_test(unittest_seastar_buffer
  unittest_seastar_buffer --memory 256M --smp 1)
target_link_libraries(unittest_seastar_buffer crimson)

add_executable(unittest_seastar_denc
  test_denc.cc)
add_ceph_unittest(unittest_seastar_denc)
target_link_libraries(unittest_seastar_denc crimson GTest::Main)

add_executable(unittest_seastar_socket test_socket.cc)
add_ceph_test(unittest_seastar_socket
  unittest_seastar_socket --memory 256M --smp 2)
target_link_libraries(unittest_seastar_socket crimson)

add_executable(unittest_seastar_messenger test_messenger.cc)
add_ceph_test(unittest_seastar_messenger
  unittest_seastar_messenger --memory 256M --smp 1)
target_link_libraries(unittest_seastar_messenger crimson)

add_executable(test_seastar_messenger_peer test_messenger_peer.cc)
target_link_libraries(test_seastar_messenger_peer ceph-common global ${ALLOC_LIBS})

add_executable(perf_crimson_msgr perf_crimson_msgr.cc)
target_link_libraries(perf_crimson_msgr crimson)

add_executable(perf_async_msgr perf_async_msgr.cc)
target_link_libraries(perf_async_msgr ceph-common global ${ALLOC_LIBS})

add_executable(unittest_seastar_echo
  test_alien_echo.cc)
target_link_libraries(unittest_seastar_echo crimson)

add_executable(unittest_async_echo
  test_async_echo.cc)
target_link_libraries(unittest_async_echo ceph-common global)

add_executable(unittest_seastar_thread_pool
  test_thread_pool.cc)
add_ceph_test(unittest_seastar_thread_pool
  unittest_seastar_thread_pool --memory 256M --smp 1)
target_link_libraries(unittest_seastar_thread_pool crimson)

add_executable(unittest_seastar_config
  test_config.cc)
target_link_libraries(unittest_seastar_config crimson)

add_executable(unittest_seastar_monc
  test_monc.cc)
target_link_libraries(unittest_seastar_monc crimson)

add_executable(unittest_seastar_perfcounters
  test_perfcounters.cc)
add_ceph_test(unittest_seastar_perfcounters
  unittest_seastar_perfcounters --memory 256M --smp 1)
target_link_libraries(unittest_seastar_perfcounters crimson)

add_executable(unittest_seastar_lru
  test_lru.cc)
add_ceph_unittest(unittest_seastar_lru --memory 256M --smp 1)
target_link_libraries(unittest_seastar_lru crimson GTest::Main)

