SOURCES := Data_Model.dia

# The Technical Style Guide requires us to make PNG versions available too
all:	$(SOURCES:%.dia=%.svg) $(SOURCES:%.dia=%.png)

%.svg:	%.dia
	dia -t svg -e $@ $^

# Direct conversion to PNG by dia results in much lower resolution images,
# and (unlike inscape which has a -p option), this cannot be overridden.
%.png:	%.svg
	inkscape -e $@ $^
