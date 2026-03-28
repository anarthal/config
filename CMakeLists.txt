# Copyright 2018 Mike Dev
# Copyright 2019 Peter Dimov
# Distributed under the Boost Software License, Version 1.0.
# See accompanying file LICENSE_1_0.txt or copy at http://www.boost.org/LICENSE_1_0.txt

# We support CMake 3.5, but prefer 4.3 policies and behavior
cmake_minimum_required(VERSION 3.5...4.3)

project(boost_config VERSION "${BOOST_SUPERPROJECT_VERSION}" LANGUAGES CXX)

add_library(boost_config INTERFACE)
add_library(Boost::config ALIAS boost_config)

# -----------------------------------------------------------------------------
# Include headers
# -----------------------------------------------------------------------------
if(NOT BOOST_USE_MODULES)
  target_include_directories(boost_config INTERFACE include)
endif()

# Note: usable starting with cmake v3.23
if(NOT CMAKE_VERSION VERSION_LESS 3.23)
  target_sources(
    boost_config
    PUBLIC
      FILE_SET headers_public
        TYPE HEADERS
        BASE_DIRS include
        FILES
          include/boost/config.hpp
          include/boost/config/abi/borland_prefix.hpp
          include/boost/config/abi/borland_suffix.hpp
          include/boost/config/abi/msvc_prefix.hpp
          include/boost/config/abi/msvc_suffix.hpp
          include/boost/config/abi_prefix.hpp
          include/boost/config/abi_suffix.hpp
          include/boost/config/assert_cxx03.hpp
          include/boost/config/assert_cxx11.hpp
          include/boost/config/assert_cxx14.hpp
          include/boost/config/assert_cxx17.hpp
          include/boost/config/assert_cxx20.hpp
          include/boost/config/assert_cxx23.hpp
          include/boost/config/assert_cxx98.hpp
          include/boost/config/auto_link.hpp
          include/boost/config/compiler/borland.hpp
          include/boost/config/compiler/clang.hpp
          include/boost/config/compiler/clang_version.hpp
          include/boost/config/compiler/codegear.hpp
          include/boost/config/compiler/comeau.hpp
          include/boost/config/compiler/common_edg.hpp
          include/boost/config/compiler/compaq_cxx.hpp
          include/boost/config/compiler/cray.hpp
          include/boost/config/compiler/diab.hpp
          include/boost/config/compiler/digitalmars.hpp
          include/boost/config/compiler/gcc.hpp
          include/boost/config/compiler/gcc_xml.hpp
          include/boost/config/compiler/greenhills.hpp
          include/boost/config/compiler/hp_acc.hpp
          include/boost/config/compiler/intel.hpp
          include/boost/config/compiler/kai.hpp
          include/boost/config/compiler/metrowerks.hpp
          include/boost/config/compiler/mpw.hpp
          include/boost/config/compiler/nvcc.hpp
          include/boost/config/compiler/pathscale.hpp
          include/boost/config/compiler/pgi.hpp
          include/boost/config/compiler/sgi_mipspro.hpp
          include/boost/config/compiler/sunpro_cc.hpp
          include/boost/config/compiler/vacpp.hpp
          include/boost/config/compiler/visualc.hpp
          include/boost/config/compiler/xlcpp.hpp
          include/boost/config/compiler/xlcpp_zos.hpp
          include/boost/config/detail/cxx_composite.hpp
          include/boost/config/detail/posix_features.hpp
          include/boost/config/detail/select_compiler_config.hpp
          include/boost/config/detail/select_platform_config.hpp
          include/boost/config/detail/select_stdlib_config.hpp
          include/boost/config/detail/suffix.hpp
          include/boost/config/disable_module_warnings.hpp
          include/boost/config/header_deprecated.hpp
          include/boost/config/helper_macros.hpp
          include/boost/config/no_tr1/cmath.hpp
          include/boost/config/no_tr1/complex.hpp
          include/boost/config/no_tr1/functional.hpp
          include/boost/config/no_tr1/memory.hpp
          include/boost/config/no_tr1/utility.hpp
          include/boost/config/platform/aix.hpp
          include/boost/config/platform/amigaos.hpp
          include/boost/config/platform/beos.hpp
          include/boost/config/platform/bsd.hpp
          include/boost/config/platform/cloudabi.hpp
          include/boost/config/platform/cray.hpp
          include/boost/config/platform/cygwin.hpp
          include/boost/config/platform/haiku.hpp
          include/boost/config/platform/hpux.hpp
          include/boost/config/platform/irix.hpp
          include/boost/config/platform/linux.hpp
          include/boost/config/platform/macos.hpp
          include/boost/config/platform/qnxnto.hpp
          include/boost/config/platform/solaris.hpp
          include/boost/config/platform/symbian.hpp
          include/boost/config/platform/vms.hpp
          include/boost/config/platform/vxworks.hpp
          include/boost/config/platform/wasm.hpp
          include/boost/config/platform/win32.hpp
          include/boost/config/platform/zos.hpp
          include/boost/config/pragma_message.hpp
          include/boost/config/requires_threads.hpp
          include/boost/config/std/algorithm.hpp
          include/boost/config/std/any.hpp
          include/boost/config/std/array.hpp
          include/boost/config/std/atomic.hpp
          include/boost/config/std/barrier.hpp
          include/boost/config/std/bit.hpp
          include/boost/config/std/bitset.hpp
          include/boost/config/std/cassert.hpp
          include/boost/config/std/cctype.hpp
          include/boost/config/std/cerrno.hpp
          include/boost/config/std/cfenv.hpp
          include/boost/config/std/cfloat.hpp
          include/boost/config/std/charconv.hpp
          include/boost/config/std/chrono.hpp
          include/boost/config/std/cinttypes.hpp
          include/boost/config/std/climits.hpp
          include/boost/config/std/clocale.hpp
          include/boost/config/std/cmath.hpp
          include/boost/config/std/codecvt.hpp
          include/boost/config/std/compare.hpp
          include/boost/config/std/complex.hpp
          include/boost/config/std/concepts.hpp
          include/boost/config/std/condition_variable.hpp
          include/boost/config/std/coroutine.hpp
          include/boost/config/std/csetjmp.hpp
          include/boost/config/std/csignal.hpp
          include/boost/config/std/cstdarg.hpp
          include/boost/config/std/cstddef.hpp
          include/boost/config/std/cstdint.hpp
          include/boost/config/std/cstdio.hpp
          include/boost/config/std/cstdlib.hpp
          include/boost/config/std/cstring.hpp
          include/boost/config/std/ctime.hpp
          include/boost/config/std/cuchar.hpp
          include/boost/config/std/cwchar.hpp
          include/boost/config/std/cwctype.hpp
          include/boost/config/std/debugging.hpp
          include/boost/config/std/deque.hpp
          include/boost/config/std/exception.hpp
          include/boost/config/std/execution.hpp
          include/boost/config/std/expected.hpp
          include/boost/config/std/filesystem.hpp
          include/boost/config/std/flat_map.hpp
          include/boost/config/std/flat_set.hpp
          include/boost/config/std/format.hpp
          include/boost/config/std/forward_list.hpp
          include/boost/config/std/fstream.hpp
          include/boost/config/std/functional.hpp
          include/boost/config/std/future.hpp
          include/boost/config/std/generator.hpp
          include/boost/config/std/hazard_pointer.hpp
          include/boost/config/std/initializer_list.hpp
          include/boost/config/std/inplace_vector.hpp
          include/boost/config/std/iomanip.hpp
          include/boost/config/std/ios.hpp
          include/boost/config/std/iosfwd.hpp
          include/boost/config/std/iostream.hpp
          include/boost/config/std/istream.hpp
          include/boost/config/std/iterator.hpp
          include/boost/config/std/latch.hpp
          include/boost/config/std/limits.hpp
          include/boost/config/std/linalg.hpp
          include/boost/config/std/list.hpp
          include/boost/config/std/locale.hpp
          include/boost/config/std/map.hpp
          include/boost/config/std/mdspan.hpp
          include/boost/config/std/memory.hpp
          include/boost/config/std/memory_resource.hpp
          include/boost/config/std/mutex.hpp
          include/boost/config/std/new.hpp
          include/boost/config/std/numbers.hpp
          include/boost/config/std/numeric.hpp
          include/boost/config/std/optional.hpp
          include/boost/config/std/ostream.hpp
          include/boost/config/std/print.hpp
          include/boost/config/std/queue.hpp
          include/boost/config/std/random.hpp
          include/boost/config/std/ranges.hpp
          include/boost/config/std/ratio.hpp
          include/boost/config/std/rcu.hpp
          include/boost/config/std/regex.hpp
          include/boost/config/std/scoped_allocator.hpp
          include/boost/config/std/semaphore.hpp
          include/boost/config/std/set.hpp
          include/boost/config/std/shared_mutex.hpp
          include/boost/config/std/simd.hpp
          include/boost/config/std/source_location.hpp
          include/boost/config/std/span.hpp
          include/boost/config/std/spanstream.hpp
          include/boost/config/std/sstream.hpp
          include/boost/config/std/stack.hpp
          include/boost/config/std/stacktrace.hpp
          include/boost/config/std/stdexcept.hpp
          include/boost/config/std/stdfloat.hpp
          include/boost/config/std/stop_token.hpp
          include/boost/config/std/streambuf.hpp
          include/boost/config/std/string.hpp
          include/boost/config/std/string_view.hpp
          include/boost/config/std/strstream.hpp
          include/boost/config/std/syncstream.hpp
          include/boost/config/std/system_error.hpp
          include/boost/config/std/text_encoding.hpp
          include/boost/config/std/thread.hpp
          include/boost/config/std/tuple.hpp
          include/boost/config/std/type_traits.hpp
          include/boost/config/std/typeindex.hpp
          include/boost/config/std/typeinfo.hpp
          include/boost/config/std/unordered_map.hpp
          include/boost/config/std/unordered_set.hpp
          include/boost/config/std/utility.hpp
          include/boost/config/std/valarray.hpp
          include/boost/config/std/variant.hpp
          include/boost/config/std/vector.hpp
          include/boost/config/std/version.hpp
          include/boost/config/stdlib/dinkumware.hpp
          include/boost/config/stdlib/libcomo.hpp
          include/boost/config/stdlib/libcpp.hpp
          include/boost/config/stdlib/libstdcpp3.hpp
          include/boost/config/stdlib/modena.hpp
          include/boost/config/stdlib/msl.hpp
          include/boost/config/stdlib/roguewave.hpp
          include/boost/config/stdlib/sgi.hpp
          include/boost/config/stdlib/stlport.hpp
          include/boost/config/stdlib/vacpp.hpp
          include/boost/config/stdlib/xlcpp_zos.hpp
          include/boost/config/user.hpp
          include/boost/config/warning_disable.hpp
          include/boost/config/workaround.hpp
          include/boost/cstdint.hpp
          include/boost/cxx11_char_types.hpp
          include/boost/detail/workaround.hpp
          include/boost/limits.hpp
          include/boost/static_assert.hpp
          include/boost/version.hpp
  )
endif()
