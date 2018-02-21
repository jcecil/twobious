TWOBIOUS := twobious 

CC := g++
CFLAGS := -w -std=c++11 -DNDEBUG=1
LFLAGS := -L./lib
INCLUDE := include
SOURCE := src
BUILD := build

CPPFILES := $(foreach dir, $(SOURCE)/, $(notdir $(wildcard $(SOURCE)/*.cpp)))
OBJFILES := $(addprefix $(BUILD)/, $(CPPFILES:.cpp=.o))
DEPFILES := $(addprefix $(INCLUDE)/, $(CPPFILES:.cpp=.hpp))

all: $(TWOBIOUS)
	echo "Hope this worked"

$(TWOBIOUS): $(OBJFILES)
	$(CC) $(CFLAGS) $^ -o $(TWOBIOUS) $(LFLAGS) 

$(BUILD)/%.o: $(SOURCE)/%.cpp
	$(CC) $(CFLAGS) -I$(INCLUDE) -c $< -o $@ 

test: $(TWOBIOUS)
	LD_LIBRARY_PATH=./twobious
			
clean:
	mkdir -p $(BUILD)
	rm -f $(BUILD)/*.o
	rm -f $(TWOBIOUS)

.PHONY: clean
