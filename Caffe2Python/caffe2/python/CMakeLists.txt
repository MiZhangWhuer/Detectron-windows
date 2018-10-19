PROJECT(CaffeReImp)
CMAKE_MINIMUM_REQUIRED(VERSION 2.8.3)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIC}/lib)
INCLUDE_DIRECTORIES(${glog_INCLUDE_DIR})
INCLUDE_DIRECTORIES(${openblas_INCLUDE_DIR})

STRING(TOUPPER ${PROJECT_NAME} PROJECT_NAME_CAPITALIZED)

ADD_DEFINITIONS(-DBOOST_PYTHON_STATIC_LIB)
ADD_DEFINITIONS(-DUNICODE)
ADD_DEFINITIONS(-DGOOGLE_GLOG_DLL_DECL=)
ADD_DEFINITIONS(-DNEED_SEGMENTOR=1)
#SET(NEED_SEGMENTOR TRUE)

file(GLOB LAYERS_HEDS     ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/layers/*.h*)
file(GLOB UTIL_HEDS     ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/util/*.h*)
file(GLOB PROTO_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/proto/*.h*)
file(GLOB IMGCUT_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/util/ImageCutProcess/*.h*)
file(GLOB MSCNN_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/util/MSCNN/*.h*)
file(GLOB FRCNN_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/util/FRCNN/*.h*)
file(GLOB FRCNN_UTIL_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/util/FRCNN/util/*.h*)
file(GLOB FRCNN_API_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/api/*.h*)
file(GLOB FRCNN_API_UTIL_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/api/FRCNN/*.h*)
file(GLOB RTPOSE_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/rtpose/*.h*)
file(GLOB RTPOSE_CPM_LAYERS_HEDS  ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/cpm/layers/*.h*)
file(GLOB RTPOSE_CPM_UTIL_HEDS  ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/cpm/util/*.h*)
file(GLOB RTPOSE_CPM_HEDS  ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/cpm/*.h*)
file(GLOB SYMMETRY_HEDS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/util/SymmetryDetection/*.h*)

file(GLOB CAFFE_CORE_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/core/*.h*) #added by mi.zhang 9/26/2018
file(GLOB CAFFE_PROC_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/proto/*.h*) #added by mi.zhang 9/26/2018
file(GLOB CAFFE_GTEST_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/gtest/*.h*) #added by mi.zhang 9/26/2018
file(GLOB CAFFE_UTILS_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/utils/*.h*) #added by mi.zhang 9/26/2018
file(GLOB CAFFE_UTILS_THREADPOOL_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/utils/threadpool/*.h*) #added by mi.zhang 9/27/2018
file(GLOB CAFFE_UTILS_UTIL_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/util/*.h*) #added by mi.zhang 10/09/2018
file(GLOB CAFFE_UTILS_CVPLOT_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/cvplot/*.h*) #added by mi.zhang 10/09/2018
file(GLOB CAFFE_OPERATORS_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/operators/*.h*) #added by mi.zhang 9/28/2018
file(GLOB CAFFE_OPERATORS_RNN_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/operators/rnn/*.h*) #added by mi.zhang 9/28/2018
file(GLOB CAFFE_SGD_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/sgd/*.h*) #added by mi.zhang 10/09/2018
file(GLOB CAFFE_DB_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/db/*.h*) #added by mi.zhang 10/09/2018
file(GLOB CAFFE_MPI_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/mpi/*.h*) #added by mi.zhang 10/14/2018
file(GLOB CAFFE_OBSERVERS_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/observers/*.h*) #added by mi.zhang 10/14/2018
file(GLOB CAFFE_CONTRIB_SCRIPT_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/contrib/script/*.h*) #added by mi.zhang 10/14/2018
file(GLOB CAFFE_MODULES_DETECTRON_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/modules/detectron/*.h*) #added by mi.zhang 10/15/2018
file(GLOB CAFFE_QUEUE_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/queue/*.h*) #added by mi.zhang 10/16/2018
#for python utilities
file(GLOB CAFFE_PYTHON_HEDS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/python/*.h*) #added by mi.zhang 10/13/2018

SET(FRCNN_HED_LIST ${FRCNN_HEDS} ${FRCNN_UTIL_HEDS})
SET(FRCNN_API_HED_LIST ${FRCNN_API_HEDS} ${FRCNN_API_UTIL_HEDS})
SET(RTPOSENET_HEDS_LIST ${RTPOSE_HEDS} ${RTPOSE_CPM_LAYERS_HEDS} ${RTPOSE_CPM_UTIL_HEDS} ${RTPOSE_CPM_HEDS})

# source_group(include\\rtpose FILES ${RTPOSE_HEDS})
# source_group(include\\rtpose\\cpm FILES ${RTPOSE_CPM_HEDS})
# source_group(include\\rtpose\\cpm\\layers FILES ${RTPOSE_CPM_LAYERS_HEDS})
# source_group(include\\rtpose\\cpm\\util FILES ${RTPOSE_CPM_UTIL_HEDS})
# source_group(include\\api FILES ${FRCNN_API_HED_LIST})
# source_group(include\\layers FILES ${LAYERS_HEDS})
# source_group(include\\util FILES ${UTIL_HEDS})
# source_group(include\\proto FILES ${PROTO_HEDS})
# source_group(include\\util\\ImageCut FILES ${IMGCUT_HEDS})
# source_group(include\\util\\MSCNN FILES ${MSCNN_HEDS})
# source_group(include\\util\\FRCNN FILES ${FRCNN_HED_LIST})
# source_group(include\\util\\SymmetryDetection FILES ${SYMMETRY_HEDS})

source_group(include\\caffe2\\core FILES ${CAFFE_CORE_HEDS})
source_group(include\\caffe2\\proto FILES ${CAFFE_PROC_HEDS})
source_group(include\\caffe2\\utils FILES ${CAFFE_PROC_HEDS})
source_group(include\\caffe2\\utils\\threadpool FILES ${CAFFE_UTILS_THREADPOOL_HEDS})
source_group(include\\caffe2\\utils\\util FILES ${CAFFE_UTILS_UTIL_HEDS})
source_group(include\\caffe2\\utils\\cvplot FILES ${CAFFE_UTILS_CVPLOT_HEDS})
source_group(include\\caffe2\\operators FILES ${CAFFE_OPERATORS_HEDS})
source_group(include\\caffe2\\operators\\rnn FILES ${CAFFE_OPERATORS_RNN_HEDS})
source_group(include\\caffe2\\sgd FILES ${CAFFE_SGD_HEDS})
source_group(include\\caffe2\\db FILES ${CAFFE_DB_HEDS})
source_group(include\\caffe2\\python FILES ${CAFFE_PYTHON_HEDS})
source_group(include\\caffe2\\mpi FILES ${CAFFE_MPI_HEDS})
source_group(include\\caffe2\\observers FILES ${CAFFE_OBSERVERS_HEDS})
source_group(include\\caffe2\\contrib\\script FILES ${CAFFE_CONTRIB_SCRIPT_HEDS})
source_group(include\\caffe2\\modules\\detectron FILES ${CAFFE_MODULES_DETECTRON_HEDS})
source_group(include\\caffe2\\queue FILES ${CAFFE_QUEUE_HEDS})

file(GLOB LAYERS_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/layers/*.cpp)
file(GLOB UTIL_SRCS     ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/*.cpp)
file(GLOB SOLVER_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/solvers/*.cpp)
file(GLOB PROTO_SRCS    ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/proto/*.cc)
file(GLOB IMGCUT_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/ImageCutProcess/*.cpp)
file(GLOB FRCNN_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/FRCNN/*.cpp)
file(GLOB FRCNN_UTIL_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/FRCNN/util/*.cpp)
file(GLOB FRCNN_API_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/api/FRCNN/*.cpp)
file(GLOB FRCNN_API_UTIL_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/api/FRCNN/*.cpp)
file(GLOB RTPOSE_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/rtpose/*.cpp)
file(GLOB RTPOSE_CPM_LAYERS_SRCS  ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/cpm/layers/*.cpp)
file(GLOB RTPOSE_CPM_UTIL_SRCS  ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/cpm/util/*.cpp)
file(GLOB SYMMETRY_SRCS   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/SymmetryDetection/*.cpp)

file(GLOB CAFFE_CORE_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/core/*.c*) #added by mi.zhang 9/26/2018
file(GLOB CAFFE_PROC_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/proto/*.c*) #added by mi.zhang 9/26/2018
file(GLOB CAFFE_GTEST_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/gtest/*.cc) #added by mi.zhang 9/26/2018
file(GLOB CAFFE_UTILS_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/utils/*.c*) #added by mi.zhang 9/26/2018
file(GLOB CAFFE_UTILS_THREADPOOL_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/utils/threadpool/*.c*) #added by mi.zhang 9/27/2018
file(GLOB CAFFE_UTILS_UTIL_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/util/*.c*) #added by mi.zhang 10/09/2018
file(GLOB CAFFE_UTILS_CVPLOT_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/cvplot/*.c*) #added by mi.zhang 10/09/2018
file(GLOB CAFFE_OPERATORS_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/operators/*.c*) #added by mi.zhang 9/28/2018
file(GLOB CAFFE_OPERATORS_RNN_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/operators/rnn/*.c*) #added by mi.zhang 9/28/2018
file(GLOB CAFFE_SGD_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/sgd/*.c*) #added by mi.zhang 10/09/2018
file(GLOB CAFFE_DB_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/db/*.c*) #added by mi.zhang 10/09/2018
file(GLOB CAFFE_PYTHON_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/python/*.c*) #added by mi.zhang 10/13/2018
file(GLOB CAFFE_MPI_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/mpi/*.c*) #added by mi.zhang 10/14/2018
file(GLOB CAFFE_OBSERVERS_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/observers/*.c*) #added by mi.zhang 10/14/2018
file(GLOB CAFFE_CONTRIB_SCRIPT_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/contrib/script/*.c*) #added by mi.zhang 10/14/2018
file(GLOB CAFFE_MODULES_DETECTRON_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/modules/detectron/*.c*) #added by mi.zhang 10/15/2018
file(GLOB CAFFE_QUEUE_SRCS ${CMAKE_SOURCE_DIR}/src/DeepLearning/caffe2/queue/*.c*) #added by mi.zhang 10/16/2018


SET(FRCNN_SRC_LIST ${FRCNN_SRCS} ${FRCNN_UTIL_SRCS})
SET(FRCNN_API_SRC_LIST ${FRCNN_API_SRCS} ${FRCNN_API_UTIL_SRCS})
SET(RTPOSENET_SRCS_LIST ${RTPOSE_SRCS} ${RTPOSE_CPM_LAYERS_SRCS} ${RTPOSE_CPM_UTIL_SRCS})

# source_group(src\\rtpose FILES ${RTPOSE_SRCS})
# source_group(src\\rtpose\\cpm\\layers FILES ${RTPOSE_CPM_LAYERS_SRCS})
# source_group(src\\rtpose\\cpm\\util FILES ${RTPOSE_CPM_UTIL_SRCS})
# source_group(src\\api FILES ${FRCNN_API_SRC_LIST})
# source_group(src\\layers FILES ${LAYERS_SRCS})
# source_group(src\\util FILES ${UTIL_SRCS})
# source_group(src\\solvers FILES ${SOLVER_SRCS})
# source_group(src\\proto FILES ${PROTO_SRCS})
# source_group(src\\util\\ImageCut FILES ${IMGCUT_SRCS})
# source_group(src\\util\\FRCNN FILES ${FRCNN_SRC_LIST})
# source_group(src\\util\\SymmetryDetection FILES ${SYMMETRY_SRCS})
source_group(src\\caffe2\\core FILES ${CAFFE_CORE_SRCS})
source_group(src\\caffe2\\proto FILES ${CAFFE_PROC_SRCS})
source_group(src\\caffe2\\utils FILES ${CAFFE_UTILS_SRCS})
source_group(src\\caffe2\\utils\\thredpool FILES ${CAFFE_UTILS_THREADPOOL_SRCS})
source_group(src\\caffe2\\utils\\util FILES ${CAFFE_UTILS_UTIL_SRCS})
source_group(src\\caffe2\\utils\\cvplot FILES ${CAFFE_UTILS_CVPLOT_SRCS})
source_group(src\\caffe2\\operators FILES ${CAFFE_OPERATORS_SRCS})
source_group(src\\caffe2\\operators\\rnn FILES ${CAFFE_OPERATORS_RNN_SRCS})
source_group(src\\caffe2\\sgd FILES ${CAFFE_SGD_SRCS})
source_group(src\\caffe2\\db FILES ${CAFFE_DB_SRCS})
source_group(src\\caffe2\\python FILES ${CAFFE_PYTHON_SRCS})
source_group(src\\caffe2\\mpi FILES ${CAFFE_MPI_SRCS})
source_group(src\\caffe2\\observers FILES ${CAFFE_OBSERVERS_SRCS})
source_group(src\\caffe2\\contrib\\script FILES ${CAFFE_CONTRIB_SCRIPT_SRCS})
source_group(src\\caffe2\\modules\\detectron FILES ${CAFFE_MODULES_DETECTRON_SRCS})
source_group(src\\caffe2\\queue FILES ${CAFFE_QUEUE_SRCS})

file(GLOB_RECURSE CU_LAYER_FILES ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/layers/*.cu)
file(GLOB CU_UTIL_FILES ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/*.cu)
file(GLOB CU_MSCNN_FILES   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/MSCNN/*.cu)
file(GLOB CU_FRCNN_FILES   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/FRCNN/*.cu)
file(GLOB CU_FRCNN_UTIL_FILES   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/util/FRCNN/util/*.cu)
file(GLOB CU_RTPOSE_FILES   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/rtpose/*.cu)
file(GLOB CU_RTPOSE_CPM_LAYERS_FILES   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/cpm/layers/*.cu)
file(GLOB CU_RTPOSE_CPM_UTIL_FILES   ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/cpm/util/*.cu)
file(GLOB CU_SOLVER_FILES ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/solvers/*.cu)

SET(CU_FRCNN_LIST ${CU_FRCNN_FILES} ${CU_FRCNN_UTIL_FILES})
SET(CU_RTPOSENET_LIST ${CU_RTPOSE_FILES} ${CU_RTPOSE_CPM_LAYERS_FILES} ${CU_RTPOSE_CPM_UTIL_FILES})

# source_group(cu\\layers FILES ${CU_LAYER_FILES} )
# source_group(cu\\util FILES ${CU_UTIL_FILES})
# source_group(cu\\util\\MSCNN FILES ${MSCNN_CUSRCS})
# source_group(cu\\util\\FRCNN FILES ${CU_FRCNN_LIST})
# source_group(cu\\rtpose FILES ${CU_RTPOSE_FILES})
# source_group(cu\\rtpose\\cpm\\layers FILES ${CU_RTPOSE_CPM_LAYERS_FILES})
# source_group(cu\\rtpose\\cpm\\util FILES ${CU_RTPOSE_CPM_UTIL_FILES})
# source_group(cu\\solvers FILES ${CU_SOLVER_FILES})

 # file(GLOB GENERAL_HED_FILES ${CMAKE_SOURCE_DIR}/src/DeepLearning/include/caffe/*.h*)
 # file(GLOB GENERAL_SRC_FILES ${CMAKE_SOURCE_DIR}/src/DeepLearning/src/caffe/*.cpp)
 # source_group(include FILES ${GENERAL_HED_FILES})
 # source_group(src FILES ${GENERAL_SRC_FILES})


 
INCLUDE_DIRECTORIES(.)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})

SET(FILE_LISTS 
               # ${LAYERS_HEDS} ${UTIL_HEDS} ${PROTO_HEDS} ${IMGCUT_HEDS} ${MSCNN_HEDS} ${FRCNN_HED_LIST} ${FRCNN_API_HED_LIST} ${SYMMETRY_HEDS} ${RTPOSENET_HEDS_LIST}
               # ${LAYERS_SRCS} ${UTIL_SRCS} ${PROTO_SRCS} ${SOLVER_SRCS} ${IMGCUT_SRCS} ${FRCNN_SRC_LIST} ${FRCNN_API_SRC_LIST} ${SYMMETRY_SRCS} ${RTPOSENET_SRCS_LIST}
			   # ${CU_LAYER_FILES} ${CU_UTIL_FILES} ${CU_SOLVER_FILES} ${MSCNN_CUSRCS}  ${CU_FRCNN_LIST} ${CU_RTPOSENET_LIST}
			   # ${GENERAL_HED_FILES} ${GENERAL_SRC_FILES}
			   ${CAFFE_CORE_HEDS} ${CAFFE_CORE_SRCS}
			   ${CAFFE_PROC_HEDS} ${CAFFE_PROC_SRCS}
			   ${CAFFE_GTEST_HEDS} ${CAFFE_GTEST_SRCS}
			   ${CAFFE_UTILS_HEDS} ${CAFFE_UTILS_SRCS}
			   ${CAFFE_UTILS_THREADPOOL_HEDS} ${CAFFE_UTILS_THREADPOOL_SRCS}
			   ${CAFFE_OPERATORS_HEDS} ${CAFFE_OPERATORS_SRCS} 
			   ${CAFFE_OPERATORS_RNN_HEDS} ${CAFFE_OPERATORS_RNN_SRCS}
			   ${CAFFE_SGD_HEDS} ${CAFFE_SGD_SRCS}
			   ${CAFFE_DB_HEDS} ${CAFFE_DB_SRCS}
			   ${CAFFE_PYTHON_HEDS} ${CAFFE_PYTHON_SRCS}
			   ${CAFFE_UTILS_UTIL_HEDS} ${CAFFE_UTILS_UTIL_SRCS} ${CAFFE_UTILS_CVPLOT_HEDS} ${CAFFE_UTILS_CVPLOT_SRCS}
			   ${CAFFE_MPI_HEDS} ${CAFFE_MPI_SRCS} ${CAFFE_OBSERVERS_HEDS} ${CAFFE_OBSERVERS_SRCS}
			   ${CAFFE_CONTRIB_SCRIPT_HEDS} ${CAFFE_CONTRIB_SCRIPT_SRCS}
			   ${CAFFE_MODULES_DETECTRON_HEDS} ${CAFFE_MODULES_DETECTRON_SRCS}
			   ${CAFFE_QUEUE_HEDS} ${CAFFE_QUEUE_SRCS}
			   )

 # SET(TOOL_TARGETS
     #registry_test
	 #caffe2_pybind11_state_gpu
	 # caffe
	 # compute_image_mean
	 # convert_imageset
	 #device_query
	 # extract_features
	 #finetune_net
	 #net_speed_benchmark
	 #test_net
	 #train_net
	 # upgrade_net_proto_binary
	 # upgrade_net_proto_text
	 # semantic_segmentation #added by mi.zhang 2016.11.10 21:24
	 # semantic_segmentationSingleChannel #added by mi.zhang 2017.03.11 10:11
	 # mscnn
	 # demo_frcnn_api
	 # demo_frcnnCmp_api
	 # demo_frcnn_transModel
	 # test_frcnn
	 # convert_mnist_data
	 # rtpose
	 # convert_octree_data
	 # feature_pooling
	 # demo
	 # ssd_detect
 # )

INCLUDE_DIRECTORIES(.)
INCLUDE_DIRECTORIES(${CMAKE_CURRENT_SOURCE_DIR})

#python C/C++ mixed mode, code modified by mi.zhang 1/19/2018
# IF(USE_EMBED_PYTHON_mode)
   # SET(EMBED_PYTHON_EXTRA_CPP ${CMAKE_SOURCE_DIR}/src/DeepLearning/python/caffe/_caffe.cpp)
# ENDIF()

# FOREACH(TOOLTARGET_NAME ${TOOL_TARGETS})
	CUDA_ADD_LIBRARY(caffe2_pybind11_state_gpu  MODULE ${FILE_LISTS} )
	ADD_DEPENDENCIES(caffe2_pybind11_state_gpu  lmdb gtest protobuf libprotobuf libprotobuf-lite libprotoc libxml2)
	TARGET_LINK_LIBRARIES(caffe2_pybind11_state_gpu
	  
	   debug glogd
	   optimized glog
	   debug gflagsd
	   optimized gflags
	   debug gtestd
	   optimized gtest
	   #debug openblasd
	   openblas
	   debug leveldbd
	   optimized leveldb
	   debug lmdbd
	   optimized lmdb
	   #debug gtest_maind
	   #optimized gtest_main
	   debug protobufd
	   optimized protobuf
	   #debug DeepLearningLibd
	   #optimized DeepLearningLib
	   #debug DeepLearningSyncedMemTestLibd
	   #optimized DeepLearningSyncedMemTestLib
	   #debug openblasd
	   #optimized openblas
	   # debug libmpid
	   # optimized libmpi
	   # debug libmpi_cxxd
	   # optimized libmpi_cxx
	   # debug libopen-pald
	   # optimized libopen-pal
	   # debug libopen-rted
	   # optimized libopen-rte
	   optimized lmdb
	   debug matiod
	   optimized matio
	   debug pthreadsVC2d
	   optimized pthreadsVC2
	   # debug hdf5_D
	   # optimized hdf5
	   # debug hdf5_hl_D
	   # optimized hdf5_hl
	   # debug hdf5_cpp_D
	   # optimized hdf5_cpp
	   # debug hdf5_tools_D
	   # optimized hdf5_tools
	   # debug hdf5_hl_cpp_D
	   # optimized hdf5_hl_cpp
	   debug libhdf5_D
	   optimized libhdf5
	   debug libhdf5_cpp_D
	   optimized libhdf5_cpp
	   debug libhdf5_hl
	   optimized libhdf5_hl_D
	   debug libhdf5_hl_cpp_D
	   optimized libhdf5_hl_cpp
	   debug libhdf5_tools
	   optimized libhdf5_tools_D
	   debug ChangeDetectiond
	   optimized ChangeDetection
	   # debug libmpid
	   # optimized libmpi
	   # debug libmpi_cxxd
	   # optimized libmpi_cxx
	   # debug libopen-pald
	   # optimized libopen-pal
	   # debug libopen-rted
	   # optimized libopen-rte
	   msmpifmc
	   msmpifec
	   msmpi
	   debug libxml2d
	   optimized libxml2
	   debug cpuinfo
	   optimized cpuinfo
	   ${OpenCV_LIBS} ${GDAL_LIBRARY} ${PYTHON_LIBRARY} ${Boost_LIBRARIES} ${Boost_THREADAPI} 
	   ${CUDA_LIBRARIES} ${CUDA_CUBLAS_LIBRARIES} ${CUDA_cusparse_LIBRARY} ${CUDA_curand_LIBRARY} 
	   ${CUDA_TOOLKIT_ROOT_DIR}/lib/x64/cudnn.lib)
	#SET_TARGET_PROPERTIES(${TARGET_NAME} PROPERTIES DEFINE_SYMBOL ${PROJECT_NAME_CAPITALIZED}_LIB)#
	SET_TARGET_PROPERTIES(caffe2_pybind11_state_gpu PROPERTIES FOLDER examples/DeepLearning/Tools)
	SET_TARGET_PROPERTIES(caffe2_pybind11_state_gpu PROPERTIES SUFFIX ".pyd")
    set_target_properties(caffe2_pybind11_state_gpu PROPERTIES COMPILE_FLAGS "-fvisibility=hidden")
    set_target_properties(caffe2_pybind11_state_gpu PROPERTIES PREFIX "")
# ENDFOREACH(TOOLTARGET_NAME)



# #generate static and shared library
 # SET(LIB_TARGETS
    # AutoParsingAPI
 # )
# FOREACH(TOOLTARGET_NAME ${LIB_TARGETS})
    # #generate dynamic library
	# CUDA_ADD_LIBRARY(${TOOLTARGET_NAME} SHARED ${TOOLTARGET_NAME}.cpp ${FILE_LISTS} ${EMBED_PYTHON_EXTRA_CPP})
	# ADD_DEPENDENCIES(${TOOLTARGET_NAME}  leveldb lmdb gtest protobuf libxml2)
	# TARGET_LINK_LIBRARIES(${TOOLTARGET_NAME}
	  
	   # debug glogd
	   # optimized glog
	   # debug gflagsd
	   # optimized gflags
	   # debug gtestd
	   # optimized gtest
	   # #debug openblasd
	   # libopenblas
	   # debug leveldbd
	   # optimized leveldb
	   # debug lmdbd
	   # optimized lmdb
	   # #debug gtest_maind
	   # #optimized gtest_main
	   # debug protobufd
	   # optimized protobuf
	   # #debug DeepLearningLibd
	   # #optimized DeepLearningLib
	   # #debug DeepLearningSyncedMemTestLibd
	   # #optimized DeepLearningSyncedMemTestLib
	   # #debug openblasd
	   # #optimized openblas
	   # # debug libmpid
	   # # optimized libmpi
	   # # debug libmpi_cxxd
	   # # optimized libmpi_cxx
	   # # debug libopen-pald
	   # # optimized libopen-pal
	   # # debug libopen-rted
	   # # optimized libopen-rte
	   # optimized lmdb
	   # debug matiod
	   # optimized matio
	   # debug pthreadsVC2d
	   # optimized pthreadsVC2
	   # # debug hdf5_D
	   # # optimized hdf5
	   # # debug hdf5_hl_D
	   # # optimized hdf5_hl
	   # # debug hdf5_cpp_D
	   # # optimized hdf5_cpp
	   # # debug hdf5_tools_D
	   # # optimized hdf5_tools
	   # # debug hdf5_hl_cpp_D
	   # # optimized hdf5_hl_cpp
	   # debug libhdf5_D
	   # optimized libhdf5
	   # debug libhdf5_cpp_D
	   # optimized libhdf5_cpp
	   # debug libhdf5_hl
	   # optimized libhdf5_hl_D
	   # debug libhdf5_hl_cpp_D
	   # optimized libhdf5_hl_cpp
	   # debug libhdf5_tools
	   # optimized libhdf5_tools_D
	   # debug ChangeDetectiond
	   # optimized ChangeDetection
	   # # debug libmpid
	   # # optimized libmpi
	   # # debug libmpi_cxxd
	   # # optimized libmpi_cxx
	   # # debug libopen-pald
	   # # optimized libopen-pal
	   # # debug libopen-rted
	   # # optimized libopen-rte
	   # msmpifmc
	   # msmpifec
	   # msmpi
	   # debug libxml2d
	   # optimized libxml2
	   # ${OpenCV_LIBS} ${GDAL_LIBRARY} ${PYTHON_LIBRARY} ${Boost_LIBRARIES} ${Boost_THREADAPI} ${CUDA_LIBRARIES} ${CUDA_CUBLAS_LIBRARIES} ${CUDA_cusparse_LIBRARY} ${CUDA_curand_LIBRARY})
	
    # #generate static library
    # SET(STATIC_TARGET_NAME lib${TOOLTARGET_NAME})	
	# CUDA_ADD_LIBRARY(${STATIC_TARGET_NAME} STATIC ${TOOLTARGET_NAME}.cpp ${FILE_LISTS} ${EMBED_PYTHON_EXTRA_CPP})
	# ADD_DEPENDENCIES(${STATIC_TARGET_NAME}  leveldb lmdb gtest protobuf libxml2)
	# TARGET_LINK_LIBRARIES(${STATIC_TARGET_NAME}
	  
	   # debug glogd
	   # optimized glog
	   # debug gflagsd
	   # optimized gflags
	   # debug gtestd
	   # optimized gtest
	   # #debug openblasd
	   # libopenblas
	   # debug leveldbd
	   # optimized leveldb
	   # debug lmdbd
	   # optimized lmdb
	   # #debug gtest_maind
	   # #optimized gtest_main
	   # debug protobufd
	   # optimized protobuf
	   # #debug DeepLearningLibd
	   # #optimized DeepLearningLib
	   # #debug DeepLearningSyncedMemTestLibd
	   # #optimized DeepLearningSyncedMemTestLib
	   # #debug openblasd
	   # #optimized openblas
	   # # debug libmpid
	   # # optimized libmpi
	   # # debug libmpi_cxxd
	   # # optimized libmpi_cxx
	   # # debug libopen-pald
	   # # optimized libopen-pal
	   # # debug libopen-rted
	   # # optimized libopen-rte
	   # optimized lmdb
	   # debug matiod
	   # optimized matio
	   # debug pthreadsVC2d
	   # optimized pthreadsVC2
	   # # debug hdf5_D
	   # # optimized hdf5
	   # # debug hdf5_hl_D
	   # # optimized hdf5_hl
	   # # debug hdf5_cpp_D
	   # # optimized hdf5_cpp
	   # # debug hdf5_tools_D
	   # # optimized hdf5_tools
	   # # debug hdf5_hl_cpp_D
	   # # optimized hdf5_hl_cpp
	   # debug libhdf5_D
	   # optimized libhdf5
	   # debug libhdf5_cpp_D
	   # optimized libhdf5_cpp
	   # debug libhdf5_hl
	   # optimized libhdf5_hl_D
	   # debug libhdf5_hl_cpp_D
	   # optimized libhdf5_hl_cpp
	   # debug libhdf5_tools
	   # optimized libhdf5_tools_D
	   # debug ChangeDetectiond
	   # optimized ChangeDetection
	   # # debug libmpid
	   # # optimized libmpi
	   # # debug libmpi_cxxd
	   # # optimized libmpi_cxx
	   # # debug libopen-pald
	   # # optimized libopen-pal
	   # # debug libopen-rted
	   # # optimized libopen-rte
	   # msmpifmc
	   # msmpifec
	   # msmpi
	   # debug libxml2d
	   # optimized libxml2
	   # ${OpenCV_LIBS} ${GDAL_LIBRARY} ${PYTHON_LIBRARY} ${Boost_LIBRARIES} ${Boost_THREADAPI} ${CUDA_LIBRARIES} ${CUDA_CUBLAS_LIBRARIES} ${CUDA_cusparse_LIBRARY} ${CUDA_curand_LIBRARY})
	   
	# #SET_TARGET_PROPERTIES(${TARGET_NAME} PROPERTIES DEFINE_SYMBOL ${PROJECT_NAME_CAPITALIZED}_LIB)#
	# SET_TARGET_PROPERTIES(${TOOLTARGET_NAME} PROPERTIES FOLDER examples/DeepLearning/Tools)
# ENDFOREACH(TOOLTARGET_NAME)


#ADD_SUBDIRECTORY(ASIFT)