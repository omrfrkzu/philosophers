NAME            = philo
CC              = cc
CFLAGS          = -Wall -Wextra -Werror
MKDIR           = mkdir -p
RM              = rm -rf
LINKER          = -lpthread

INCLUDES_DIR    = includes
INCLUDES_FLAG   = -I$(INCLUDES_DIR)
INCLUDES     	= $(wildcard $(INCLUDES_DIR)/*.h)

SRCS_DIR        = srcs/
SRC_FILES       = main.c \
				  init.c \
				  utils.c \
				  str_utils.c \
				  simulation.c

OBJS_DIR        = objs/
OBJ_FILES       = $(SRC_FILES:.c=.o)
OBJS            = $(addprefix $(OBJS_DIR), $(OBJ_FILES))

all: $(OBJS_DIR) $(NAME)

$(OBJS_DIR):
	$(MKDIR) $(OBJS_DIR)

$(NAME): $(OBJS) Makefile
	$(CC) $(CFLAGS) $(OBJS) $(LINKER) -o $(NAME)

$(OBJS_DIR)%.o: $(SRCS_DIR)%.c $(INCLUDES)
	$(CC) $(CFLAGS) $(INCLUDES_FLAG) -c $< -o $@

clean:
	$(RM) $(OBJS_DIR)

fclean: clean
	$(RM) $(NAME)

re: fclean all

.PHONY: all clean fclean re
