all: fvcom

make.inc:
	# Rewrite make.inc from it's constituent parts
	./setup -w

libs: make.inc
	cd ../FVCOM_source/libs && $(MAKE) clobber && time $(MAKE) -j 6

gotm: make.inc
	cd ../GOTM_source && $(MAKE) clobber && time $(MAKE)

fvcom: make.inc
	cd ../FVCOM_source && \rm -f fvcom && time $(MAKE) -j

clean: make.inc
	cd ../FVCOM_source && $(MAKE) clean

clobber: make.inc
	cd ../FVCOM_source/libs && $(MAKE) clobber
	cd ../GOTM_source && $(MAKE) clobber
	cd ../FVCOM_source && $(MAKE) clobber

