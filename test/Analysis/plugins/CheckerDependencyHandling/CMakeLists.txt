set(LLVM_EXPORTED_SYMBOL_FILE ${CMAKE_CURRENT_SOURCE_DIR}/CheckerDependencyHandlingAnalyzerPlugin.exports)
add_llvm_library(CheckerDependencyHandlingAnalyzerPlugin MODULE CheckerDependencyHandling.cpp PLUGIN_TOOL clang)

if(LLVM_ENABLE_PLUGINS)
  target_link_libraries(CheckerDependencyHandlingAnalyzerPlugin PRIVATE
    clangAnalysis
    clangAST
    clangStaticAnalyzerCore
    clangStaticAnalyzerFrontend
    LLVMSupport
    )
endif()
