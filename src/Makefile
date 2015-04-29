# ------------------------------------------------------------------------
# Altere somente as 4 variáveis abaixo
# ------------------------------------------------------------------------
SRCS      = ExampleApp.o Multiply.o Addition.o
PROGRAM   = app
# ------------------------------------------------------------------------
CXX       = g++
CXXFLAGS  = -Wall -I. -Winline -O3
LDFLAGS   = 
OBJS      = $(SRCS:.cpp=.o)
TEST_DIR  = ./test

.SUFFIXES: .cpp .o

.cpp.o: 
	$(CXX) -c $(CXXFLAGS) $< -o $@

all: $(PROGRAM) 

run: all
	./$(PROGRAM)

check:
	make -C $(TEST_DIR) run

$(PROGRAM): $(OBJS)
	$(CXX) -o $(PROGRAM) $(SRCS) $(CXXFLAGS) $(LDFLAGS)

clean:
	@/bin/rm -f $(OBJS) $(PROGRAM) *~
	make -C $(TEST_DIR) clean
