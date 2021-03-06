cmake_minimum_required ( VERSION 2.8 )
project ( libpeconv )

set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} /MT")

include_directories (
  include
)

set (srcs
	src/pe_hdrs_helper.cpp
	src/pe_mode_detector.cpp
	src/pe_raw_to_virtual.cpp
	src/pe_virtual_to_raw.cpp
	src/relocate.cpp
	src/buffer_util.cpp
	src/remote_pe_reader.cpp
	src/imports_loader.cpp
	src/delayed_imports_loader.cpp
	src/fix_imports.cpp
	src/pe_loader.cpp
	src/pe_dumper.cpp
	src/exports_lookup.cpp
	src/function_resolver.cpp
	src/hooks.cpp
	src/exported_func.cpp
	src/exports_mapper.cpp
	src/resource_parser.cpp
	src/file_util.cpp
	src/resource_util.cpp
	src/imports_uneraser.cpp
	src/caves.cpp
	src/util.cpp
)

set (hdrs
	include/peconv.h
	include/peconv/pe_hdrs_helper.h
	include/peconv/pe_mode_detector.h
	include/peconv/pe_raw_to_virtual.h
	include/peconv/pe_virtual_to_raw.h
	include/peconv/relocate.h
	include/peconv/util.h
	include/peconv/buffer_util.h
	include/peconv/remote_pe_reader.h
	include/peconv/imports_loader.h
	include/peconv/delayed_imports_loader.h
	include/peconv/fix_imports.h
	include/peconv/pe_loader.h
	include/peconv/pe_dumper.h
	include/peconv/exports_lookup.h
	include/peconv/function_resolver.h
	include/peconv/hooks.h
	include/peconv/exported_func.h
	include/peconv/exports_mapper.h
	include/peconv/resource_parser.h
	include/peconv/file_util.h
	include/peconv/resource_util.h
	include/peconv/imports_uneraser.h
	include/peconv/caves.h
)

add_library ( ${PROJECT_NAME} STATIC ${hdrs} ${srcs} )
