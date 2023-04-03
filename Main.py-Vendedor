import csv

# Función para validar la entrada del usuario
def validar_entrada(mensaje, tipo):
    while True:
        entrada = input(mensaje)
        try:
            # Intenta convertir la entrada del usuario al tipo especificado
            entrada_validada = tipo(entrada)
            return entrada_validada
        except:
            # Si hay un error al convertir la entrada, muestra un mensaje de error y vuelve a solicitar la entrada al usuario.
            print("Error: entrada no válida.")

# Solicitar la información del vendedor
nombre = validar_entrada("Nombre del vendedor: ", str)
print("Por favor, ingrese la siguiente información del vendedor:")

num_productos = validar_entrada("¿Cuántos productos desea agregar?: ", int)

productos = []
for i in range(num_productos):
    producto = {}
    producto["tipo_producto"] = validar_entrada(f"Tipo de producto {i+1}: ", str)
    producto["descripcion"] = validar_entrada(f"Descripción de producto {i+1}: ", str)
    producto["precio"] = validar_entrada(f"Precio de producto {i+1}: ", float)
    producto["cantidad"] = validar_entrada(f"Inventario de producto {i+1}: ", int)
    productos.append(producto)

# Mostrar la información del vendedor
print("\nInformación del vendedor:")
print("Nombre del vendedor:", nombre)
for i, producto in enumerate(productos):
    print(f"\nInformación del producto {i+1}:")
    print("Tipo de producto:", producto["tipo_producto"])
    print("Descripción:", producto["descripcion"])
    print("Precio:", producto["precio"])
    print("Cantidad de productos:", producto["cantidad"])

# Almacenar la información del vendedor en un archivo CSV
try:
    with open("vendedores.csv", mode="a", newline="") as archivo:
        escritor_csv = csv.writer(archivo, delimiter=":")
        # Escribe el nombre del vendedor en una fila separada
        escritor_csv.writerow(["El vendedor se llama " + nombre])
        # Escribe la información de cada producto en una fila separada
        for i, producto in enumerate(productos):
            escritor_csv.writerow([f"Producto {i+1}", producto["tipo_producto"], producto["descripcion"], "Precio", producto["precio"], "Cantidad", producto["cantidad"]])
    # Muestra un mensaje de éxito si la información se ha almacenado con éxito
    print("\nLa información del vendedor se ha almacenado exitosamente en el archivo vendedores.csv.")
except:
    # Muestra un mensaje de error si hubo algún problema al intentar almacenar la información en el archivo CSV.
    print("\nError al intentar almacenar la información del vendedor en el archivo vendedores.csv.")
