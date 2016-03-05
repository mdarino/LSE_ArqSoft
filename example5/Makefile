
#Proj
	#src
	#inc
	#out
		#obj
	#makefile



SRC_FILES = $(wildcard *.c)
OBJ_FILES = $(SRC_FILES:.c=.o)
DEP_FILES = $(SRC_FILES:.c=.d)
EXE = programa





-include $(DEP_FILES)

#regla: para generar "ejecutable" uso "main.c", lo que está debajo es el comando (siempre con un tab)
#regla patron
%.o: %.c
	@echo "Compilando main.c"
	gcc -c $< -o $@
	#$< regla
	#$@ dependencia


#falta generar las dependencias
#creamos un archivo .d (dependencias)
%.d: %.c
	@echo "Generamos las dependencias"
	gcc -MM $< > $(subst .o,.d,$@)





#regla clean, no tiene dependencias, borra el ejecutable
clean: 
	rm $(EXE)
	rm $(OBJ_FILES)
	rm $(DEP_FILES)

$(EXE): $(OBJ_FILES)
	@echo "linkeando $(EXE).."
	gcc $(OBJ_FILES) -o $(EXE)



run: $(EXE)
	./$(EXE)


info: 
	@echo SRC_FILES: $(SRC_FILES)
	@echo OBJ_FILES: $(OBJ_FILES)
	@echo DEP_FILES: $(DEP_FILES)



