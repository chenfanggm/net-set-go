SET(EXE_NAME testNetCore)

SET(SOURCE_DIR ${CMAKE_SOURCE_DIR}/tests/NetCore)
SET(HEADER_DIR ${CMAKE_SOURCE_DIR}/tests/NetCore)

ADD_SOURCE_FILES(EXE_SOURCE_FILES ${SOURCE_DIR} "")
ADD_HEADER_FILES(EXE_HEADER_FILES ${HEADER_DIR} "")

ADD_EXECUTABLE(${EXE_NAME}
               ${EXE_SOURCE_FILES}
               ${EXE_HEADER_FILES}
)

INCLUDE_DIRECTORIES(${HEADER_PATH}
                    ${OPENTHREADS_INCLUDE_DIR}
                    # todo: add more
)

# libraries to link into the executable, both Release and Debug
TARGET_LINK_LIBRARIES(${EXE_NAME}
                      NetCore
                      optimized ${OPENTHREADS_LIBRARY} debug  ${OPENTHREADS_LIBRARY_DEBUG}
)
