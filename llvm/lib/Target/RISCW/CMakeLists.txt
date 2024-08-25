add_llvm_component_group(RISCW)

set(LLVM_TARGET_DEFINITIONS RISCW.td)
#add_subdirectory(MCTargetDesc)
#add_subdirectory(TargetInfo)

tablegen(LLVM RISCWGenRegisterInfo.inc -gen-register-info)
#tablegen(LLVM RISCWGenInstrInfo.inc -gen-instr-info)
#tablegen(LLVM RISCWGenCodeEmitter.inc -gen-emitter)
#tablegen(LLVM RISCWGenMCCodeEmitter.inc -gen-emitter)
#tablegen(LLVM RISCWGenAsmWriter.inc -gen-asm-writer)
#tablegen(LLVM RISCWGenDAGISel.inc -gen-dag-isel)
#tablegen(LLVM RISCWGenCallingConv.inc -gen-callingconv)
tablegen(LLVM RISCWGenSubtargetInfo.inc -gen-subtarget)
#tablegen(LLVM RISCWGenMCPseudoLowering.inc -gen-pseudo-lowering)

# General table gen
add_public_tablegen_target(RISCWCommonTableGen)

add_llvm_target(RISCWCodeGen
    RISCWTargetObjectFile.cpp
    )

