set(LOCAL_PATH ${KERNEL_ROOT}/fs)

set(SOURCE_FILES "")

add_c_source(SOURCE_FILES ${LOCAL_PATH} open)
add_c_source(SOURCE_FILES ${LOCAL_PATH} read_write)
add_c_source(SOURCE_FILES ${LOCAL_PATH} file_table)
add_c_source(SOURCE_FILES ${LOCAL_PATH} super)
add_c_source(SOURCE_FILES ${LOCAL_PATH} char_dev)
add_c_source(SOURCE_FILES ${LOCAL_PATH} stat)
add_c_source(SOURCE_FILES ${LOCAL_PATH} exec)
add_c_source(SOURCE_FILES ${LOCAL_PATH} pipe)
add_c_source(SOURCE_FILES ${LOCAL_PATH} namei)
add_c_source(SOURCE_FILES ${LOCAL_PATH} fcntl)
add_c_source(SOURCE_FILES ${LOCAL_PATH} ioctl)
add_c_source(SOURCE_FILES ${LOCAL_PATH} readdir)
add_c_source(SOURCE_FILES ${LOCAL_PATH} select)
add_c_source(SOURCE_FILES ${LOCAL_PATH} dcache)
add_c_source(SOURCE_FILES ${LOCAL_PATH} inode)
add_c_source(SOURCE_FILES ${LOCAL_PATH} attr)
add_c_source(SOURCE_FILES ${LOCAL_PATH} bad_inode)
add_c_source(SOURCE_FILES ${LOCAL_PATH} file)
add_c_source(SOURCE_FILES ${LOCAL_PATH} filesystems)
add_c_source(SOURCE_FILES ${LOCAL_PATH} namespace)
add_c_source(SOURCE_FILES ${LOCAL_PATH} seq_file)
add_c_source(SOURCE_FILES ${LOCAL_PATH} xattr)
add_c_source(SOURCE_FILES ${LOCAL_PATH} libfs)
add_c_source(SOURCE_FILES ${LOCAL_PATH} fs-writeback)
add_c_source(SOURCE_FILES ${LOCAL_PATH} pnode)
add_c_source(SOURCE_FILES ${LOCAL_PATH} splice)
add_c_source(SOURCE_FILES ${LOCAL_PATH} sync)
add_c_source(SOURCE_FILES ${LOCAL_PATH} utimes)
add_c_source(SOURCE_FILES ${LOCAL_PATH} stack)
add_c_source(SOURCE_FILES ${LOCAL_PATH} fs_struct)
add_c_source(SOURCE_FILES ${LOCAL_PATH} statfs)


add_library(fs STATIC ${SOURCE_FILES})

if (${CONFIG_DEBUG_FS})
    add_subdirectory(debugfs)
    target_link_libraries(fs
            fs-debugfs
            )
endif ()