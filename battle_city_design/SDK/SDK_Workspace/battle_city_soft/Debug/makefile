################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include src/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
ELFSIZE += \
battle_city_soft.elf.size \

ELFCHECK += \
battle_city_soft.elf.elfcheck \


# All Target
all: battle_city_soft.elf secondary-outputs

# Tool invocations
battle_city_soft.elf: $(OBJS) ../src/lscript.ld $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: MicroBlaze gcc linker'
	mb-gcc -Wl,-T -Wl,../src/lscript.ld -L../../standalone_bsp_0/microblaze_0/lib -mlittle-endian -mxl-barrel-shift -mxl-pattern-compare -mcpu=v8.50.b -mno-xl-soft-mul -Wl,--no-relax -Wl,--gc-sections -o "battle_city_soft.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

battle_city_soft.elf.size: battle_city_soft.elf
	@echo 'Invoking: MicroBlaze Print Size'
	mb-size battle_city_soft.elf  |tee "battle_city_soft.elf.size"
	@echo 'Finished building: $@'
	@echo ' '

battle_city_soft.elf.elfcheck: battle_city_soft.elf
	@echo 'Invoking: Xilinx ELF Check'
	elfcheck battle_city_soft.elf -hw ../../battle_city_design_hw_platform/system.xml -pe microblaze_0  |tee "battle_city_soft.elf.elfcheck"
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(OBJS)$(C_DEPS)$(EXECUTABLES)$(ELFSIZE)$(ELFCHECK)$(S_UPPER_DEPS) battle_city_soft.elf
	-@echo ' '

secondary-outputs: $(ELFSIZE) $(ELFCHECK)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
