cmake_minimum_required(VERSION 2.8.3)

project(tasker_msgs)

# Get the information about this package's buildtime dependencies
  find_package(catkin REQUIRED
    COMPONENTS message_generation std_msgs geometry_msgs rospy)

  # Declare the message files to be built
  add_message_files(FILES
    TaskState.msg
    ScheduleParams.msg
    Status.msg
    RobotResource.msg
    ShdlData.msg
    ShdlDataStamped.msg
    CMD.msg
  #  MyMessage2.msg
  )


  # Declare the service files to be built
  add_service_files(FILES
    TaskRequest.srv
    LaunchConditions.srv
    StartTask.srv
    HoldConditions.srv
    SchedulingConditions.srv
    SuspendConditions.srv
    CostConditions.srv
  )



  # Actually generate the language-specific message and service files
  generate_messages(DEPENDENCIES std_msgs geometry_msgs)

# Catkin package  
  catkin_package(
   INCLUDE_DIRS 
   CATKIN_DEPENDS rospy
   DEPENDS )



  # define executable using MyMessage1 etc.
  #add_executable(message_program src/main.cpp)
  #add_dependencies(message_program ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

  # define executable not using any messages/services provided by this package
  #add_executable(does_not_use_local_messages_program src/main.cpp)
  #add_dependencies(does_not_use_local_messages_program ${catkin_EXPORTED_TARGETS})

