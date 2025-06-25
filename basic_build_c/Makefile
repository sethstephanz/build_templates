# Compiler and flags
CC = gcc
CFLAGS = -Wall -Wextra -std=c11
LDFLAGS = 

# Directories
SRC_DIR = src
TEST_DIR = test
BUILD_DIR = build

# Files
SRC_FILES = $(SRC_DIR)/main.c
TEST_FILES = $(TEST_DIR)/test.c
OBJ_FILES = $(BUILD_DIR)/main.o $(BUILD_DIR)/test.o
EXEC = $(BUILD_DIR)/test

# Build target
all: $(EXEC)

# Link the final executable
$(EXEC): $(OBJ_FILES)
	@mkdir -p $(BUILD_DIR)
	$(CC) $(LDFLAGS) -o $@ $^

# Compile object files
$(BUILD_DIR)/%.o: $(SRC_DIR)/%.c $(SRC_DIR)/%.h
	@mkdir -p $(BUILD_DIR)
	$(CC) $(CFLAGS) -c $< -o $@

$(BUILD_DIR)/test.o: $(TEST_DIR)/test.c $(SRC_DIR)/main.h
	@mkdir -p $(BUILD_DIR)
	$(CC) $(CFLAGS) -c $< -o $@

# Clean up build files
clean:
	rm -rf $(BUILD_DIR)

# Phony targets
.PHONY: all clean

