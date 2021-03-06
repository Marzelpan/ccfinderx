AUTOMAKE_OPTIONS = subdir-objects
ACLOCAL_AMFLAGS = -I m4 ${ACLOCAL_FLAGS}

bin_PROGRAMS = \
	ccfx/ccfx \
	picosel/picosel

pyexec_LTLIBRARIES = torq/pyeasytorq/easytorq.la

lib_LTLIBRARIES = ccfx/CCFinderXLib/lib_CCFinderXLib.la

common_CPPFLAGS = \
	-DOS_UBUNTU \
	-DLITTLE_ENDIAN \
	-DCXLM_NO_ENC \
	-DCODE_CONVERSION_SUPPORT \
	-DWSTRING_CONVERSION_SUPPORT \
	-DREQUIRE_RNR \
	-DCONFDIR=\"$(pkgdatadir)\"

common_LIBADD = $(ICU_LIBS) -lboost_thread-mt -lboost_system

picosel_picosel_CPPFLAGS = $(common_CPPFLAGS) -O2 -fpermissive

picosel_picosel_SOURCES = \
	picosel/picosel.cpp \
	common/unportable.cpp

ccfx_ccfx_SOURCES = \
	common/allocaarray.h \
	common/argvbuilder.h \
	common/base64encoder.h \
	common/bitcounttable.h \
	common/bitvector.h \
	common/datastructureonfile.h \
	common/ffuncrenamer.h \
	common/filestructwrapper.h \
	common/hash_map_includer.h \
	common/hash_set_includer.h \
	common/unportable.h \
	common/utf8support.h \
	common/win32util.h \
	common/base64encoder.cpp \
	common/bitvector.cpp \
	common/unportable.cpp \
	common/utf8support.cpp \
	ccfx/ccfxcommon.h \
	ccfx/ccfxconstants.h \
	ccfx/clonedataassembler.h \
	ccfx/filteringmain.h \
	ccfx/findfilemain.h \
	ccfx/metricmain.h \
	ccfx/preprocessorinvoker.h \
	ccfx/prettyprintmain.h \
	ccfx/rawclonepairdata.h \
	ccfx/shapedfragmentcalculator.h \
	ccfx/transformermain.h \
	ccfx/ccfx.cpp \
	ccfx/ccfxcommon.cpp \
	ccfx/prettyprintermain.cpp \
	ccfx/rawclonepairdata.cpp \
	ccfx/ccfxconstants.cpp

ccfx_ccfx_CPPFLAGS = $(common_CPPFLAGS) -O2 -fpermissive
ccfx_ccfx_LDFLAGS = $(common_LIBADD)

# Remove -Wstrict-prototypes as this is only for ObjC and C, but we
# compiling with C++. Thiss only works with GNU Make.
CXX_PYTHON_INCLUDES := $(filter-out -Wstrict-prototypes,$(PYTHON_INCLUDES))
torq_pyeasytorq_easytorq_la_CPPFLAGS = $(common_CPPFLAGS) \
	-O2 -fpermissive $(CXX_PYTHON_INCLUDES)

torq_pyeasytorq_easytorq_la_SOURCES = \
	torq/interpreter.h \
	torq/specialchars.h \
	torq/texttoken.h \
	torq/torqcommon.h \
	torq/torqparser.h \
	torq/torqtokenizer.h \
	torq/interpreter.cpp \
	torq/texttoken.cpp \
	torq/easytorq/easytorq.h \
	torq/easytorq/easytorq.cpp \
	torq/pyeasytorq/pyeasytorq.cpp \
	torq/torqcommon.cpp \
	common/unportable.cpp \
	common/utf8support.cpp

torq_pyeasytorq_easytorq_la_LIBADD = $(common_LIBADD)
torq_pyeasytorq_easytorq_la_LDFLAGS = -avoid-version -module

ccfx_CCFinderXLib_lib_CCFinderXLib_la_CPPFLAGS = $(common_CPPFLAGS) \
	-O2 -fpermissive

ccfx_CCFinderXLib_lib_CCFinderXLib_la_SOURCES = \
	GemX/ccfinderx_CCFinderX.h \
	ccfx/CCFinderXLib/CCFinderXLib.cpp \
	common/unportable.cpp \
	common/base64encoder.cpp \
	common/utf8support.cpp \
	ccfx/ccfxcommon.cpp \
	ccfx/ccfxconstants.cpp

ccfx_CCFinderXLib_lib_CCFinderXLib_la_LDFLAGS = \
	-version-info $(CCFINDER_LIB_VER) \
	-release $(PACKAGE_VERSION)

ccfx_CCFinderXLib_lib_CCFinderXLib_la_LIBADD = $(common_LIBADD)

scriptsdir = $(pkgdatadir)/scripts
scripts_ppdir = $(scriptsdir)/pp

pkgdata_DATA = \
	macOS/ccfx_prep_scripts.ini \
	macOS/colors.json \
	macOS/gemx.properties \
	macOS/gemx.sh \
	macOS/icu4j-4_0_1.jar \
	macOS/icu4j-charsets-4_0_1.jar \
	macOS/icu4j-localespi-4_0_1.jar

scripts_DATA = \
	macOS/scripts/ccfxconfig.py \
	macOS/scripts/easytorq_helper.py \
	macOS/scripts/moduleloadutility.py \
	macOS/scripts/post-prettyprint.pl \
	macOS/scripts/preprocess.py \
	macOS/scripts/prescreening.py \
	macOS/scripts/pythonversionchecker.py \
	macOS/scripts/testthreadingutil.py \
	macOS/scripts/threadingutil.py \
	macOS/scripts/utility.py \
	macOS/scripts/win32getshortname.py

scripts_pp_DATA = \
	macOS/scripts/pp/__init__.py \
	macOS/scripts/pp/cobol.py \
	macOS/scripts/pp/cpp.py \
	macOS/scripts/pp/csharp.py \
	macOS/scripts/pp/java.py \
	macOS/scripts/pp/plaintext.py \
	macOS/scripts/pp/preprocessor.py \
	macOS/scripts/pp/visualbasic.py
