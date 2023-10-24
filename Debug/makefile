################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include MCAL/DIO/Source/subdir.mk
-include HAL/SevSeg/Source/subdir.mk
-include HAL/LCD/Source/subdir.mk
-include HAL/Keypad/Source/subdir.mk
-include App/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
CalculatorWithPrioriry.lss \

FLASH_IMAGE += \
CalculatorWithPrioriry.hex \

EEPROM_IMAGE += \
CalculatorWithPrioriry.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: CalculatorWithPrioriry.elf secondary-outputs

# Tool invocations
CalculatorWithPrioriry.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,CalculatorWithPrioriry.map -mmcu=atmega32 -o "CalculatorWithPrioriry.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

CalculatorWithPrioriry.lss: CalculatorWithPrioriry.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S CalculatorWithPrioriry.elf  >"CalculatorWithPrioriry.lss"
	@echo 'Finished building: $@'
	@echo ' '

CalculatorWithPrioriry.hex: CalculatorWithPrioriry.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex CalculatorWithPrioriry.elf  "CalculatorWithPrioriry.hex"
	@echo 'Finished building: $@'
	@echo ' '

CalculatorWithPrioriry.eep: CalculatorWithPrioriry.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex CalculatorWithPrioriry.elf  "CalculatorWithPrioriry.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: CalculatorWithPrioriry.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=avr --mcu=atmega32 CalculatorWithPrioriry.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(EEPROM_IMAGE)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) CalculatorWithPrioriry.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
