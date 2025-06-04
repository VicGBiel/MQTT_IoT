cmake_minimum_required(VERSION 3.13)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
set(PICO_BOARD pico_w CACHE STRING "Board type")
include(pico_sdk_import.cmake)


project(MQTT_IoT C CXX ASM)
pico_sdk_init()

add_executable(${PROJECT_NAME} 
            MQTT_IoT.c 
            )

target_link_libraries(${PROJECT_NAME} 
        pico_stdlib
        pico_cyw43_arch_lwip_threadsafe_background
        pico_lwip_mqtt
        pico_mbedtls
        pico_lwip_mbedtls
        hardware_gpio
        hardware_pio
        hardware_adc
        hardware_pwm
        )

target_include_directories(${PROJECT_NAME} PRIVATE
    ${CMAKE_CURRENT_LIST_DIR}
)

target_sources(${PROJECT_NAME} PRIVATE
)

pico_enable_stdio_usb(${PROJECT_NAME}  1)
pico_enable_stdio_uart(${PROJECT_NAME}  0)

pico_add_extra_outputs(${PROJECT_NAME} )
