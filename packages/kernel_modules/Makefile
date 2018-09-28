in_ext = .c
module_ext = .ko
basenames = $(notdir $(basename $(filter-out %.mod.c, $(wildcard $(M)/*$(in_ext)))))
obj-m += $(addsuffix .o, $(basenames))
ccflags-y := -DDEBUG -g -std=gnu99 -Werror -Wno-declaration-after-statement -Wframe-larger-than=1000000000

.PHONY: all clean

all:
	$(MAKE) -C '$(LINUX_DIR)' M='$(M)' $(MAKE_EXTRA)

clean:
	$(MAKE) -C '$(LINUX_DIR)' M='$(M)' clean
