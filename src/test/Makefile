# ------------------------------------------------------------------------
# Altere somente as 4 variáveis abaixo
# ------------------------------------------------------------------------
GTEST_DIR = /opt/gtest
TEST_SRCS = Main_TestAll.o Multiply_Test.o Addition_Test.o
APP_SRCS  = ../Addition.o ../Multiply.o
PROGRAM   = test
# ------------------------------------------------------------------------

CXX       = g++

CXXFLAGS  = -Wall -I. -Winline -I../ -I$(GTEST_DIR)/include 
LDFLAGS   = -lpthread
TEST_OBJS = $(TEST_SRCS:.cpp=.o) 
APP_OBJS  = $(APP_SRCS:.cpp=.o) 
GTEST_OBJS= $(GTEST_DIR)/src/gtest-all.o 

.SUFFIXES: .cpp .o

.cpp.o: 
	$(CXX) -c $(CXXFLAGS) $< -o $@

all: $(PROGRAM) 

run: all
	./$(PROGRAM)

$(PROGRAM): $(TEST_OBJS) $(APP_OBJS)
	$(CXX) -o $(PROGRAM) $(TEST_SRCS) $(APP_OBJS) $(GTEST_OBJS) $(CXXFLAGS) $(LDFLAGS)

clean:
	@/bin/rm -f $(TEST_OBJS) $(PROGRAM) *~
