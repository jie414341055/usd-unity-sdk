﻿set(USD_CS_SWIG_SHIM ${CMAKE_CURRENT_LIST_DIR}/usdCs.i)
if (${CMAKE_SYSTEM_NAME} STREQUAL "Linux")
    set_source_files_properties(
        ${USD_CS_SWIG_SHIM}
        PROPERTIES
        CPLUSPLUS ON
        SWIG_FLAGS "-namespace;pxr;-w401;-w516;-w503;-DSWIGWORDSIZE64"
        )
else ()
    set_source_files_properties(
        ${USD_CS_SWIG_SHIM}
        PROPERTIES
        CPLUSPLUS ON
        SWIG_FLAGS "-namespace;pxr;-w401;-w516;-w503;-dllimport;UsdCs"
        )
endif ()
