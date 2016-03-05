
#Proj
	#src
	#inc
	#out
		#obj
	#makefile


SRC_PATH = ./src
INC_PATH = ./inc
OUT_PATH = ./out
OBJ_PATH = $(OUT_PATH)/obj



SRC_FILES = $(wildcard $(SRC_PATH)/*.c)
OBJ_FILES = $(subst $(SRC_PATH),$(OBJ_PATH),$(SRC_PATH:.c=.o))
DEP_FILES = $(subst $(SRC_PATH),$(OBJ_PATH),$(SRC_PATH:.c=.d))
OBJS=$()
EXE = programa



vpath %.o $(OBJ_PATH)
vpath %.c $(SRC_PATH)




-include $(DEP_FILES)

#regla: para generar "ejecutable" uso "main.c", lo que está debajo es el comando (siempre con un tab)
#regla patron

%.o: %.c
	@echo "Compilando main.c"
	gcc -I(INC_PATH) -c $< -o $@
	@echo "Generamos las dependencias"
	gcc -I(INC_PATH) -MM $< > $(OBJ_PATH)/$(@:.o=.d)





#regla clean, no tiene dependencias, borra el ejecutable
clean: 
	rm $(EXE)
	rm $(OBJ_FILES)
	rm $(DEP_FILES)

$(EXE): $(OBJS)
	@echo "linkeando $(EXE).."
	gcc $(OBJ_FILES) -o $(EXE)



run: $(EXE)
	./$(EXE)


info: 
	@echo SRC_FILES: $(SRC_FILES)
	@echo OBJ_FILES: $(OBJ_FILES)
	@echo DEP_FILES: $(DEP_FILES)



