#path
DIR_INC = ./include
DIR_SRC = ./src
DIR_LIB = ./lib
DIR_BIN = ./bin
DIR_OBJ = ./obj

CC = gcc
CFLAGS = -Wall -O0 -g 
BIN_NAME = app
PATH_SRC = $(wildcard $(DIR_SRC)/*.c) 	#将src目录下的.c以及路径名赋值给PATH_SRC
SRC = $(notdir $(PATH_SRC))				#除去路径名后剩下的文件以及扩展名
OBJS = $(patsubst %.c, $(DIR_OBJ)/%.o, $(SRC))	
INC = $(patsubst %.c, $(DIR_INC)/%.d, $(SRC))	
#OBJS = $(SRC:.c=.o)					#此方法可将.c换成.o，但是无法加上路径
BIN = $(DIR_BIN)/$(BIN_NAME)		

.PHONY:clean

include $(.d)

$(BIN):$(OBJS)
	$(CC) $(CFLAGS) -o $@ $^

$(DIR_OBJ)/%.o:$(DIR_SRC)/%.c #$(DIR_INC)/%.h
	$(CC) -c $(CFLAGS)  $< -o $@ 

clean:
	$(RM) $(BIN) $(OBJS) .*.sw? 


