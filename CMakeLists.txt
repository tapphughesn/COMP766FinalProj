cmake_minimum_required(VERSION 3.10)

# set the project name
project(Tsdproj)

find_package(VTK REQUIRED)
# find_package(ITK 5 REQUIRED)
find_package(ITK 5 REQUIRED
			COMPONENTS
			ThinShellDemons
			ITKVtkGlue
			ITKOptimizers
			ITKOptimizersv4
			ITKStatistics
			ITKTransform
			ITKSpatialObjects
			ITKPath
			ITKSmoothing
			ITKImageFeature
			ITKOptimizers
			ITKRegistrationMethodsv4
			ITKVtkGlue
			ITKMetaIO
			ITKVTK
)

include(${ITK_USE_FILE})

# add the executable
add_executable(Tsdproj Tsdproj.cxx)

target_link_libraries(Tsdproj ${VTK_LIBRARIES})
target_link_libraries(Tsdproj ${ITK_LIBRARIES})
