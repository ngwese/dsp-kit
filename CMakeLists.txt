cmake_minimum_required(VERSION 3.7)
project(dsp_kit)

set(CMAKE_CXX_STANDARD 14)

include_directories(.)

add_subdirectory(lib/cnpy)

add_executable(test-fifo
        test/test-fifo.cpp
        Fifo.hpp)

#add_executable(test-smoothing
#        test/test-smoothing.cpp)

add_executable(test-envelope
        test/test-envelope.cpp
        Envelope.cpp
        Envelope.hpp)
target_link_libraries(test-envelope cnpy)

add_executable(test-svf
        test/test-svf.cpp
        Svf.cpp
        Svf.hpp)
target_link_libraries(test-svf sndfile)

add_executable(test-ladder-lpf
        test/test-ladder-lpf.cpp
        LadderLpf.hpp)
target_link_libraries(test-ladder-lpf sndfile)

add_executable(test-dc-blocker
        test/test-dc-blocker.cpp
        DcBlocker.hpp)
target_link_libraries(test-dc-blocker sndfile)

add_executable(test-taper
        test/test-taper.cpp
        Taper.hpp
        Taper.cpp)

add_executable(test-audio-bus
        test/test-audio-bus.cpp
        AudioBus.hpp)

add_subdirectory(noise)
