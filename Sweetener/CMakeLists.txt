cmake_minimum_required(VERSION 3.20)
project(micro_detuner_called_sweetener VERSION 0.1.0)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(JUCE)

juce_add_plugin(Sweetener
    COMPANY_NAME "JoshuaWere"
    IS_SYNTH FALSE
    NEEDS_MIDI_INPUT FALSE
    NEEDS_MIDI_OUTPUT FALSE
    IS_MIDI_EFFECT FALSE
    EDITOR_WANTS_KEYBOARD_FOCUS FALSE

    PLUGIN_MANUFACTURER_CODE JWer
    PLUGIN_CODE Swet

    FORMATS VST3 Standalone  # add AU on mac: VST3 AU Standalone
    PRODUCT_NAME "Sweetener"
)

target_sources(Sweetener PRIVATE
    Source/PluginProcessor.cpp
    Source/PluginProcessor.h
    Source/PluginEditor.cpp
    Source/PluginEditor.h
    Source/DSP/MicroTuner.cpp
    Source/DSP/MicroTuner.h
)

target_include_directories(Sweetener PRIVATE
    Source
    Source/DSP
)

target_compile_definitions(Sweetener PRIVATE
    JUCE_WEB_BROWSER=0
    JUCE_USE_CURL=0
)

target_link_libraries(Sweetener
    PRIVATE
        juce::juce_audio_utils
        juce::juce_dsp
    PUBLIC
        juce::juce_recommended_config_flags
        juce::juce_recommended_lto_flags
        juce::juce_recommended_warning_flags
)
