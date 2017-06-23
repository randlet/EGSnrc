#*****************************************************************************
#
#  $Id: Makefile,v 1.1 2005/04/29 20:50:20 iwan Exp $
#
#*****************************************************************************

include $(EGS_CONFIG)
include $(SPEC_DIR)egspp.spec
include $(SPEC_DIR)egspp_$(my_machine).conf

DEFS = $(DEF1) -Wall

library = egs_rz
lib_files = egs_rz
link2_libs = egspp egs_planes egs_cylinders egs_ndgeometry

all: ndgeom planes cyls $(DSO2)$(libpre)$(library)$(libext)

include $(SPEC_DIR)egspp_libs.spec

ndgeom: planes
	cd ..$(DSEP)egs_nd_geometry$(DSEP) && make

planes:
	cd ..$(DSEP)egs_planes$(DSEP) && make

cyls:
	cd ..$(DSEP)egs_cylinders$(DSEP) && make

$(make_depend)

clean:
	rm -f $(ABS_DSO)$(libpre)egs_rz$(libext)
	rm -f $(DSO2)egs_rz.$(obje)

.PHONY: all clean
.DEFAULT: all
