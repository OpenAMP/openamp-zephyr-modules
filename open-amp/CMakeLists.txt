#
# Copyright (c) 2018 Linaro Limited
#
# SPDX-License-Identifier: Apache-2.0
#

if(CONFIG_OPENAMP)
set(WITH_ZEPHYR 1)
set(WITH_ZEPHYR_LIB 1)
if (CONFIG_OPENAMP_MASTER)
  set(WITH_VIRTIO_DRIVER 1)
else()
  set(WITH_VIRTIO_DRIVER OFF CACHE BOOL "" FORCE)
endif()
if (CONFIG_OPENAMP_SLAVE)
  set(WITH_VIRTIO_DEVICE 1)
else()
  set(WITH_VIRTIO_DEVICE OFF CACHE BOOL "" FORCE)
endif()
if (CONFIG_OPENAMP_WITH_DCACHE)
  set(WITH_DCACHE 1)
endif()
set(WITH_LIBMETAL_FIND OFF CACHE BOOL "" FORCE)
set(WITH_PROXY OFF CACHE BOOL "" FORCE)

add_subdirectory(${ZEPHYR_BASE}/../open-amp open-amp)

endif()
