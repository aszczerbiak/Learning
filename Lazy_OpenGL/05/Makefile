CXX=g++
MKDIR_P=mkdir -p
RM=rm -f
RM_R=rm -rf
CXXFLAGS= -g -c -Wall -Wextra -D_REENTRANT --std=c++1z
LDLIBS= -lGL -lGLU -lglut

.PHONY: all \
        clean \
        run

SRCDIR=src
BINDIR=bin
OBJDIR=${BINDIR}/obj

PROGRAM_NAME=Lazy_OpenGL05
PROGRAM_LOCATION=${BINDIR}/${PROGRAM_NAME}

SOURCES=$(shell find ${SRCDIR} -name "*.cpp")
OBJECTS=$(patsubst ${SRCDIR}/%.cpp, ${OBJDIR}/%.o, ${SOURCES})


all: ${PROGRAM_LOCATION}

clean:
	${RM_R} ${BINDIR}
	${RM} ${PROGRAM_NAME}

run:
	@./${PROGRAM_LOCATION}

###############################################################################

${PROGRAM_LOCATION}: ${OBJECTS}
	${CXX} ${LDFLAGS} -o ${PROGRAM_LOCATION} ${OBJECTS} ${LDLIBS}
	@echo "Build successful."

${OBJECTS}: ${OBJDIR}/%.o: ${SRCDIR}/%.cpp
	@mkdir -p $(@D)
	${CXX} ${CXXFLAGS} $< -o $@

print-%:
	@echo $* = ${$*}
