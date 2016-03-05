SRC_FILES = main.c suma.c
OBJ_FILES = main.o suma.o
DEP_FILES = main.d suma.d
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






