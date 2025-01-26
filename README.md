# -Implementaci-n-de-Constructores-y-Destructores
 Implementación de Archivo
# Implementación de Constructores y Destructores
# Ejemplo Archivo
class Archivo:
    def __init__(self, nombre_archivo):
        # Constructor: inicializa el atributo nombre_archivo y abre el archivo en modo escritura
        self.nombre_archivo = nombre_archivo
        self.archivo = open(nombre_archivo, 'w')
        print(f"Archivo {nombre_archivo} abierto")

    def escribir(self, texto):
        # Escribe texto en el archivo
        self.archivo.write(texto)

    def __del__(self):
        # Destructor: cierra el archivo cuando el objeto es eliminado
        self.archivo.close()
        print(f"Archivo {self.nombre_archivo} cerrado")

#Clase que representa un recurso
class Recurso:
    def __init__(self, nombre_recurso):
        # Constructor: inicializa el atributo nombre_recurso e imprime un mensaje
        self.nombre_recurso = nombre_recurso
        print(f"Recurso {nombre_recurso} inicializado")

    def utilizar(self):
        # Simula el uso del recurso
        print(f"Utilizando recurso {self.nombre_recurso}")

    def __del__(self):
        # Destructor: imprime un mensaje cuando el objeto es eliminado
        print(f"Recurso {self.nombre_recurso} liberado")

#Crea objetos y utiliza sus métodos
archivo = Archivo('example.txt')
archivo.escribir('Hola, mundo!')

recurso = Recurso('Recurso 1')
recurso.utilizar()
