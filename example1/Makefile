#regla: para generar "ejecutable" uso "main.c", lo que está debajo es el comando (siempre con un tab)
main.o: main.c
	@echo "Compilando main.c"
	gcc -c main.c -o main.o

#regla clean, no tiene dependencias, borra el ejecutable
clean: 
	rm programa
	rm main.o

programa: main.o
	@echo "linkeando programa.."
	gcc main.o -o programa


run: programa
	./programa








#Proceso desede el programa al binario
	#Programa
		#Compliacion (genera los .o objetos)
		#Enlace (linkeo)
	#Binario

#Dependencias
	#Regla: [dependencias] las dependencias son opcionales
	#-TAB- comando  (si cumple hace el comando)