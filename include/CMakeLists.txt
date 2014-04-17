# Copyright 2011, Nicolas Mansard, LAAS-CNRS
#
# This file is part of sot-dyninv.
# sot-dyninv is free software: you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public License
# as published by the Free Software Foundation, either version 3 of
# the License, or (at your option) any later version.
#
# sot-dyninv is distributed in the hope that it will be useful, but
# WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# General Lesser Public License for more details.  You should have
# received a copy of the GNU Lesser General Public License along with
# sot-dyninv. If not, see <http://www.gnu.org/licenses/>.

SET(${PROJECT_NAME}_HEADERS
	commands-helper.h
	entity-helper.h
	signal-helper.h

	mal-to-eigen.h
	stack-template.h
	stack-template.t.cpp

	controller-pd.h
	task-dyn-pd.h
	dynamic-integrator.h
	solver-op-space.h
	zmp-estimator.h
	pseudo-robot-dynamic.h
        
        task-joint-limits.h
)

# Recreate correct path for the headers
#--------------------------------------

FOREACH(lHeader ${${PROJECT_NAME}_HEADERS})
  file(COPY ../src/${lHeader} DESTINATION ${CATKIN_DEVEL_PREFIX}/include/${PROJECT_NAME}/)

ENDFOREACH(lHeader)

INSTALL(DIRECTORY ${CATKIN_DEVEL_PREFIX}/include/${PROJECT_NAME}/
	DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}/
)

#----------------------------------------------------
# Install procedure for the header files
#----------------------------------------------------
