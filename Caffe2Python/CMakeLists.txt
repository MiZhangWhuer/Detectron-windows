
#PROJECT(caffe)
#CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3)

#STRING(TOUPPER ${PROJECT_NAME} PROJECT_NAME_CAPITALIZED)

ADD_DEFINITIONS(-DUNICODE)

# FILE(GLOB_RECURSE HDRS_FILES *.h *.hpp)
# FILE(GLOB_RECURSE SRCS_FILES *.cpp *.c *.cc *.cxx)
#INCLUDE_DIRECTORIES(${glog_INCLUDE_DIR})
#INCLUDE_DIRECTORIES(${openblas_INCLUDE_DIR})

#STRING(TOUPPER ${PROJECT_NAME} PROJECT_NAME_CAPITALIZED)

#ADD_DEFINITIONS(-DUNICODE)
#ADD_DEFINITIONS(-DGOOGLE_GLOG_DLL_DECL=)

ADD_SUBDIRECTORY(caffe2)
#ADD_SUBDIRECTORY(python)

  # caffe_source_group("Include"        GLOB "${root}/include/caffe/*.h*")
  # caffe_source_group("Include\\Util"  GLOB "${root}/include/caffe/util/*.h*")
  # caffe_source_group("Include"        GLOB "${PROJECT_BINARY_DIR}/caffe_config.h*")
  # caffe_source_group("Source"         GLOB "${root}/src/caffe/*.cpp")
  # caffe_source_group("Source\\Util"   GLOB "${root}/src/caffe/util/*.cpp")
  # caffe_source_group("Source\\Layers" GLOB "${root}/src/caffe/layers/*.cpp")
  # caffe_source_group("Source\\Cuda"   GLOB "${root}/src/caffe/layers/*.cu")
  # caffe_source_group("Source\\Cuda"   GLOB "${root}/src/caffe/util/*.cu")
  # caffe_source_group("Source\\Proto"  GLOB "${root}/src/caffe/proto/*.proto")

  # # source groups for test target
  # caffe_source_group("Include"      GLOB "${root}/include/caffe/test/test_*.h*")
  # caffe_source_group("Source"       GLOB "${root}/src/caffe/test/test_*.cpp")
  # caffe_source_group("Source\\Cuda" GLOB "${root}/src/caffe/test/test_*.cu")

  # header files
  # file(GLOB LAYERS_HEDS   ${CMAKE_CURRENT_SOURCE_DIR}/include/layers/*.h*)
  # file(GLOB UTIL_HEDS     ${CMAKE_CURRENT_SOURCE_DIR}/include/utils/*.h*)
  # file(GLOB PROTO_HEDS    ${CMAKE_CURRENT_SOURCE_DIR}/include/protos/*.h*)
  # file(GLOB SOLVER_HEDS    ${CMAKE_CURRENT_SOURCE_DIR}/include/solvers/*.h*)
  #file(GLOB LAYERS_HEDS   ${CMAKE_CURRENT_SOURCE_DIR}/include/layers/*.h*)
  # file(GLOB UTIL_HEDS     ${CMAKE_CURRENT_SOURCE_DIR}/include/caffe/util/*.h*)
  # file(GLOB PROTO_HEDS    ${CMAKE_CURRENT_SOURCE_DIR}/include/caffe/proto/*.h*)
  # #file(GLOB SOLVER_HEDS    ${CMAKE_CURRENT_SOURCE_DIR}/include/solvers/*.h*)
  # #source_group(include\\layer FILES ${LAYERS_HEDS})
  # source_group(include\\util FILES ${UTIL_HEDS})
  # source_group(include\\proto FILES ${PROTO_HEDS})
  # #source_group(include\\solver FILES ${SOLVER_HEDS})
  
  # #source files
  # file(GLOB LAYERS_SRCS   ${CMAKE_CURRENT_SOURCE_DIR}/src/caffe/layers/*.cpp)
  # file(GLOB UTIL_SRCS     ${CMAKE_CURRENT_SOURCE_DIR}/src/caffe/util/*.cpp)
  # file(GLOB PROTO_SRCS    ${CMAKE_CURRENT_SOURCE_DIR}/src/caffe/proto/*.cc)
  # source_group(src\\layers FILES ${LAYERS_SRCS})
  # source_group(src\\util FILES ${UTIL_SRCS})
  # source_group(src\\proto FILES ${PROTO_SRCS})
  
  #file(GLOB SOLVER_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/solvers/*.cpp)
  #source_group(src\\solvers FILES ${SOLVER_SRCS})
  
  #cuda files
  # file(GLOB_RECURSE CU_LAYER_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/caffe/layers/*.cu)
  # file(GLOB CU_UTIL_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/caffe/util/*.cu)
  # #file(GLOB CU_SOLVER_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/solvers/*.cu)
  # source_group(cu\\layers FILES ${CU_LAYER_FILES} )
  # source_group(cu\\util FILES ${CU_UTIL_FILES})
  #source_group(cu\\solvers FILES ${CU_SOLVER_FILES})
  
  
  # group for common layer, data layer, loss layer, neuron layer, recurrent layer and vision layer respectively
  # file(GLOB COMMON_LAYER_HEDS ${CMAKE_CURRENT_SOURCE_DIR}/include/layers/common/*.h* )
  # file(GLOB DATA_LAYER_HEDS ${CMAKE_CURRENT_SOURCE_DIR}/include/layers/data/*.h* )
  # file(GLOB LOSS_LAYER_HEDS ${CMAKE_CURRENT_SOURCE_DIR}/include/layers/loss/*.h* )
  # file(GLOB NEURON_LAYER_HEDS ${CMAKE_CURRENT_SOURCE_DIR}/include/layers/neuron/*.h* )
  # file(GLOB RECURRENT_LAYER_HEDS ${CMAKE_CURRENT_SOURCE_DIR}/include/layers/recurrent/*.h* )
  # file(GLOB VISION_LAYER_HEDS ${CMAKE_CURRENT_SOURCE_DIR}/include/layers/vision/*.h* )
  
  
  # source_group(include\\layer\\common FILES ${COMMON_LAYER_HEDS})
  # source_group(include\\layer\\data FILES ${DATA_LAYER_HEDS})
  # source_group(include\\layer\\loss FILES ${LOSS_LAYER_HEDS})
  # source_group(include\\layer\\neuron FILES ${NEURO_LAYER_HEDS})
  # source_group(include\\layer\\recurrent FILES ${RECURRENT_LAYER_HEDS})
  # source_group(include\\layer\\vision FILES ${VISION_LAYER_HEDS})
  
  
  # file(GLOB COMMON_LAYER_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/layers/common/*.c* )
  # file(GLOB DATA_LAYER_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/layers/data/*.c* )
  # file(GLOB LOSS_LAYER_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/layers/loss/*.c* )
  # file(GLOB NEURON_LAYER_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/layers/neuron/*.c* )
  # file(GLOB RECURRENT_LAYER_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/layers/recurrent/*.c* )
  # file(GLOB VISION_LAYER_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/layers/vision/*.c* )
  
  
  # source_group(src\\layer\\common FILES ${COMMON_LAYER_SRCS})
  # source_group(src\\layer\\data FILES ${DATA_LAYER_SRCS})
  # source_group(src\\layer\\loss FILES ${LOSS_LAYER_SRCS})
  # source_group(src\\layer\\neuron FILES ${NEURON_LAYER_SRCS})
  # source_group(src\\layer\\recurrent FILES ${RECURRENT_LAYER_SRCS})
  # source_group(src\\layer\\vision FILES ${VISION_LAYER_SRCS})
  
  # file(GLOB_RECURSE NETWORK_SRCS      RELATIVE ${CMAKE_CURRENT_SOURCE_DIR}/network *.cpp *.h)
  # file(GLOB_RECURSE THREADING_SRCS    RELATIVE ${CMAKE_CURRENT_SOURCE_DIR}/threading *.cpp *.h)
  # file(GLOB_RECURSE UTILS_SRCS        RELATIVE ${CMAKE_CURRENT_SOURCE_DIR}/utils *.cpp *.h)

  
  # source_group(network    FILES ${NETWORK_SRCS})
  # source_group(threading  FILES ${THREADING_SRCS})
  # source_group(utils      FILES ${UTILS_SRCS})
  


# SET(VarMethod_FILES 
    # ${CMAKE_CURRENT_SOURCE_DIR}/varitionalmethod/ChanVeseSegmentation.h
	# ${CMAKE_CURRENT_SOURCE_DIR}/varitionalmethod/ChanVeseSegmentation.cpp
	# ${CMAKE_CURRENT_SOURCE_DIR}/varitionalmethod/Image.h
	# ${CMAKE_CURRENT_SOURCE_DIR}/varitionalmethod/Image.cpp
	# ${CMAKE_CURRENT_SOURCE_DIR}/varitionalmethod/ReadWritePBM.h
	# ${CMAKE_CURRENT_SOURCE_DIR}/varitionalmethod/ReadWritePBM.cpp
	# ${CMAKE_CURRENT_SOURCE_DIR}/varitionalmethod/ZeroCrossings.h
	# ${CMAKE_CURRENT_SOURCE_DIR}/varitionalmethod/ZeroCrossings.cpp
	# )

  #file(GLOB test_hdrs    ${CMAKE_CURRENT_SOURCE_DIR}/include/caffe/test/test_*.h*)
  #file(GLOB test_srcs    ${CMAKE_CURRENT_SOURCE_DIR}/src/caffe/test/test_*.cpp)
  # file(GLOB GENERAL_HED_FILES ${CMAKE_CURRENT_SOURCE_DIR}/include/caffe/*.h*)
  # file(GLOB GENERAL_SRC_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/caffe/*.cpp)
  # source_group(include FILES ${GENERAL_HED_FILES})
  # source_group(src FILES ${GENERAL_SRC_FILES})
  #list(REMOVE_ITEM  hdrs ${test_hdrs})
  #list(REMOVE_ITEM  srcs ${test_srcs})

  # adding headers to make the visible in some IDEs (Qt, VS, Xcode)
  #list(APPEND srcs ${hdrs} ${PROJECT_BINARY_DIR}/caffe_config.h)
  #list(APPEND test_srcs ${test_hdrs})

  # collect cuda files
  #file(GLOB    test_cuda ${root}/src/caffe/test/test_*.cu)
  #file(GLOB CUDA_FILES ${CMAKE_CURRENT_SOURCE_DIR}/src/caffe/*.cu)	
	
# INCLUDE_DIRECTORIES(.)
# INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})

# SET(FILE_LISTS ${UTIL_HEDS} ${PROTO_HEDS} 
               # ${LAYERS_SRCS} ${UTIL_SRCS} ${PROTO_SRCS} 
			   # ${CU_LAYER_FILES} ${CU_UTIL_FILES} 
			   # ${GENERAL_HED_FILES} ${GENERAL_SRC_FILES}
			   
			   # )
#executable files for caffe tools
# SET(TOOL_TARGETS
    # ${CMAKE_CURRENT_SOURCE_DIR}/tools/caffe
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/compute_image_mean
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/convert_imageset
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/device_query
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/extract_features
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/finetune_net
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/net_speed_benchmark
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/test_net
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/train_net
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/upgrade_net_proto_binary
	# ${CMAKE_CURRENT_SOURCE_DIR}/tools/upgrade_net_proto_text
# )

# INCLUDE_DIRECTORIES(.)
# INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})


# FOREACH(TOOLTARGET_NAME ${TOOL_TARGETS})
	# CUDA_ADD_EXECUTABLE( ${TOOLTARGET_NAME} ${FILE_LISTS} ${TOOLTARGET_NAME}.cpp)
	# ADD_DEPENDENCIES(${TOOLTARGET_NAME}  CmdLine glog gflags leveldb lmdb gtest gtest_main protobuf )
	# TARGET_LINK_LIBRARIES(${TOOLTARGET_NAME} 
	  
	   # debug CmdLined
	   # debug glogd
	   # optimized CmdLine
	   # optimized glog
	   # gflags
	   # debug leveldbd
	   # optimized leveldb
	   # debug leveldb-testharnessd
	   # optimized leveldb-testharness
	   # debug lmdbd
	   # optimized lmdb
	   # debug gtestd
	   # optimized gtest
	   # debug gtest_maind
	   # optimized gtest_main
	   # debug protobufd
	   # optimized protobuf
	   # #debug DeepLearningLibd
	   # #optimized DeepLearningLib
	   # #debug DeepLearningSyncedMemTestLibd
	   # #optimized DeepLearningSyncedMemTestLib
	   # debug openblasd
	   # optimized openblas
	   # debug libmpid
	   # optimized libmpi
	   # debug libmpi_cxxd
	   # optimized libmpi_cxx
	   # debug libopen-pald
	   # optimized libopen-pal
	   # debug libopen-rted
	   # optimized libopen-rte
	   # ${OpenCV_LIBS} ${Boost_LIBRARIES} ${Boost_THREADAPI} ${CUDA_LIBRARIES} ${CUDA_CUBLAS_LIBRARIES} ${CUDA_curand_LIBRARY})
	# #SET_TARGET_PROPERTIES(${TARGET_NAME} PROPERTIES DEFINE_SYMBOL ${PROJECT_NAME_CAPITALIZED}_LIB)#
	# SET_TARGET_PROPERTIES(${TOOLTARGET_NAME} PROPERTIES FOLDER examples/DeepLearning/Tools)
# ENDFOREACH(TOOLTARGET_NAME)			   
			   
			   
#CUDA_ADD_EXECUTABLE(${PROJECT_NAME}  ${FILE_LISTS})
#ADD_LIBRARY(${PROJECT_NAME}  ${FILE_LISTS})
# ADD_DEPENDENCIES(${TARGET_NAME} ChangeDetection CmdLine glog gflags leveldb lmdb gtest gtest_main protobuf)
# TARGET_LINK_LIBRARIES(${PROJECT_NAME} 
	   # debug ChangeDetectiond 
	   # debug CmdLined
	   # debug glogd
	   # optimized ChangeDetection 
	   # optimized CmdLine
	   # optimized glog
	   # gflags
	   # debug leveldbd
	   # optimized leveldb
	   # debug leveldb-testharnessd
	   # optimized leveldb-testharness
	   # debug lmdbd
	   # optimized lmdb
	   # debug gtestd
	   # optimized gtest
	   # debug gtest_maind
	   # optimized gtest_main
	   # debug protobufd
	   # optimized protobuf
	   # #debug DeepLearningLMDBTestLibd
	   # #optimized DeepLearningLMDBTestLib
	   # #debug DeepLearningSyncedMemTestLibd
	   # #optimized DeepLearningSyncedMemTestLib
	   # debug openblasd
	   # optimized openblas
	   # debug libmpid
	   # optimized libmpi
	   # debug libmpi_cxxd
	   # optimized libmpi_cxx
	   # debug libopen-pald
	   # optimized libopen-pal
	   # debug libopen-rted
	   # optimized libopen-rte
	   # ${OpenCV_LIBS} ${Boost_LIBRARIES} ${Boost_THREADAPI} ${CUDA_LIBRARIES} ${CUDA_CUBLAS_LIBRARIES} ${CUDA_curand_LIBRARY})

 #SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES DEFINE_SYMBOL ${PROJECT_NAME_CAPITALIZED}_LIB)
 #SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES FOLDER examples/DeepLearning)



