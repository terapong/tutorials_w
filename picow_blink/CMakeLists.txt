add_executable(picow_blink
        picow_blink.c
        )

target_link_libraries(
        picow_blink              # for core functionality
        pico_cyw43_arch_lwip_threadsafe_background
        pico_stdlib     # we need Wifi to access the GPIO, but we don't need anything else
        )

# create map/bin/hex file etc.
pico_add_extra_outputs(picow_blink)