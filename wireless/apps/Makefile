
include $(BUILD_ROOT)/tools/config.mk
include $(BUILD_ROOT)/tools/tools.mk

LIBS = libosl libxwifi
APPS = xwifiapp

SUB_BUILD = $(LIBS) $(APPS) 
.PHONY : $(SUB_BUILD) $(BIN_DIR) 

all : $(OBJ_DEST)	$(SUB_BUILD)	$(BIN_DIR)

$(SUB_BUILD) : 
	$(call DISPLAY_RED , $(subst ,,* $@ ) )
	@ $(MAKE) -C $(APPS_DIR)/$@

clean : $(patsubst %, %_clean, $(SUB_BUILD))
	$(call DISPLAY_RED ,##  $@  COMPLETE !!!  )
	
$(patsubst %,%_clean,$(SUB_BUILD)) :
	$(Q_)$(MAKE) -C $(APPS_DIR)/$(subst _clean,,$@) clean
	
install : $(patsubst %, %_install, $(SUB_BUILD))
	$(call DISPLAY_RED ,##  $@  COMPLETE !!!  )

$(patsubst %,%_install,$(SUB_BUILD)) :
	$(Q_)$(MAKE) -C $(APPS_DIR)/$(subst _install,,$@) install
	
	
$(BIN_DIR) :
	$(Q_)$(MKDIR) $(BIN_DIR)


include $(BUILD_ROOT)/tools/print.mk

	
