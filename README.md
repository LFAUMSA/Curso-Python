# Curso-Python
Autor: M.Sc. Decker Guzmán Zabalaga

Laboratorio de Física de la Atmósfera (LFA)
## 1. Introducción 
Este curso tiene como objetivo enseñar Python para el publico orientado en Ciencias Atmosféricas y Ciencia de Datos. 

Se realizará analisis a partir de datos de principales centros meterologicos que nos brindan sugerencias de manipulación de estos datos, asi como su visualización. Los codigos seran comentados para facilitar el aprendizaje.

Los datos utilizados serán:

* Programa Queimadas: https://queimadas.dgi.inpe.br/queimadas/portal

* Produto MERGE: http://ftp.cptec.inpe.br/modelos/tempo/MERGE/GPM/DAILY

* ERA5/ECMWF (European Centre for Medium-Range Weather Forecasts)
ERA5/ECMWF: https://cds.climate.copernicus.eu/cdsapp#!/search?type=dataset

* NCEP (National Centers for Environmental Prediction)
https://psl.noaa.gov/data/gridded

* NASA (National Aeronautics and Space Administration)
GRACE: https://nasagrace.unl.edu

## 2. Instalación de miniconda o anaconda
## 2.1 Anaconda
¿Por qué Anaconda o miniconda?

Se recomienda trabajar con Anaconda ya que en el mismo se pueden crear ambientes de trabajo específicos para cada tarea e instalar solamente los paquetes necesarios para la misma sin afectar al resto de los programas instalados en el PC.
Para la instalación se puede seguir la siguiente guia:

* https://docs.conda.io/projects/conda/en/latest/user-guide/install/index.html

Es preferible instalar las bibliotecas necesarias via Anaconda. Para instalar Anaconda,basta colocar los siguientes comandos en la terminal:
## 2.2 Miniconda 
* curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

* bash Miniconda3-latest-Linux-x86_64.sh

Debe reiniciar la maquina para que los cambios sean hechos:

### 2.2.1 Actualizar el conda

* conda update -n base -c defaults conda
### 2.2.2 Crear un nuevo ambiente virtual
* conda create --name <nombre_ambiente>
* Ejemplo: creacion del ambiente llamado lfa

conda create --name lfa

### 2.2.3 ver lista de programas instalados

* conda list
### 2.2.4 desactivar un ambiente virtual

* conda deactivate

Al realizar lo ultimo, el usuario de ambiente virtual cambiara al ambiente normal (base)

### 2.2.5 activar un ambiente

* conda activate <nombre_ambiente>

Ejemplo:

* conda activate lfa

Antes o ambiente era o (base).

* (base) decker@DESKTOP-LD7TCRV:~$

despues del comando, quedará asi:

* (lfa) decker@DESKTOP-LD7TCRV:~$

### 2.2.6 Borrar un ambiente 

* conda env remove --name <nombre_ambiente>

Exemplo:

* conda env remove --name lfa

### 2.2.7 Instalación de programas

* conda install -c conda-forge ncl
* conda install -c conda-forge gdal
* conda install -c conda-forge cdo
* conda install -c conda-forge imagemagick
* conda install -c conda-forge ncview
* conda install -c conda-forge htop
* conda install -c conda-forge parallel
* conda install -c conda-forge nco
* conda install -c conda-forge wgrib2

### 2.2.8 Instalación de una versión especifica de um programa

* conda install <nombre_programa>=<version_programa>
Ejemplo: Instalar la versión de cdo 1.9.9.

* conda install cdo=1.9.9
### 2.2.9 Actualizar una libreria 

* conda update <nombre_libreria>

### 2.2.10 desinstalar una libreria 

* conda remove --force <nombre_libreria>

## 3. Lista de bibliotecas que serán instalados

Los codigos son ejecutables correctamente con las bibiotecas listadas abajo, basta digitar estos comandos en la terminal:

* pip install matplotlib==3.4.3
* pip install pandas==1.4.2
* pip install SkillMetrics==1.1.8
* pip install proplot==0.9.4
* pip install xarray==2022.3.0
* pip install netcdf4==1.5.8
* pip install esmtools==1.1.3
* pip install cartopy==0.20.2
* pip install yellowbrick==1.4
* pip install seaborn==0.11.2
* pip install windrose==1.6.8
* pip install climate-indices==1.0.10
* pip install salem==0.3.7
* pip install geopandas==0.10.2
* pip install rasterio==1.2.10
* pip install siphon==0.9
* pip install metpy==1.3.0

Existen varias maneras de llamar las librerias, se puede crear un archivo con extension .yml y colocar las librerias y su versión 

el formato del archivo .ylm debe ser:

name: lfa

channels:
  - conda-forge
  - ncar
dependencies:
  - python=3.8.10
  - python-dateutil=2.8.1
  - python_abi=3.8
  - cartopy=0.19.0.post1
  - geographiclib=1.50
  - make=4.3
  - matplotlib=3.3.0
  - metpy=1.0.1
  - netcdf4=1.5.6 
  - numpy=1.20.3
  - pip=21.1.2 
  - wrf-python=1.3.2.5
  - xarray= 0.18.2   
  - ipython=7.24.1
  - ipython_genutils=0.2.0
  - make=4.3
  - matplotlib-inline=0.1.2
  
  Una vez que se tenga un archivo .yml se puede crear el ambiente siguiendo los siguientes pasos por terminal:
    
        cd <carpeta donde esta el programa .py>
  
	* conda activate base
  
	* conda env create -f archivo.yml
  
	* conda activate lfa
	
  RESULTA MUY UTIL PARA PERSONAS QUE NO QUIEREN INSTALAR NADA EN SUS PC'S O NO ESTAN FAMILIARIZADOS CON EL SISTEMA OPERATIVO LINUX USAR :
	
	* JUPYTER NOTEBOOKS
	* GOOGLE COLABORATORY (COLAB)
	
  # 4. Clase 1
  
  En esta clase veremos los comandos basicos de python:
  
  * Operaciones aritmeticas simples
  
  * Crear funciones
  
  * Condicionales if/else/elif
  
  * Lista
  
  * Matrizes con NUMPY 

    # 4.1 Librerias
	* Numpy es una libreria dundamental para computación en Python, contiene un poderoso manejo de matrices en N dimensiones, herramientas para integrar con C/C++ y Fortran como capacidad para realizar calculos en algebra lineal, transformada de Fourier, etc.
	
	Vamos a comenzar viendo comandos basicos de Pthon convirtiendo datos de temeratura en escala Celsius, Farenheit e Kelvin.
	
```python
# valor de la temperatura en celsius
tc = 35.1
# para convertir a kelvin
tk = tc + 273.15
print(tk)
```
308.25
```python
# para convertir a farenheit
tf = (tc * 9. / 5.) + 32.

print(tf)
```
95.18
	
Importante: Una cosa importante al escribir el código es tratar de no repetir demasiado y valorar la legibilidad del código. Entonces, para no repetir el mismo comando varias veces, construyamos una función. Para definir la función, usamos el comando *def* y luego el nombre de la función, seguido de los parámetros que toma.
```python
def convert_celsius_to_kelvin(value):
  return value + 273.15 # transforma celsius en kelvin

def convert_celsius_to_farenheit(value):
  return (value * 9. / 5.) + 32. # transforma celsius en farenheit
```

Sugerencia: hay un acrónimo en el mundo de la programación DRY (Don't Repeat yourself) que quizás recuerde cuando esté escribiendo un código más complejo y se pregunte ¿es bueno?".

Podemos simplificarlo para usar solo una función que haga todas las conversiones si verificamos las condiciones de la unidad de entrada y salida usando condicionales en python:

```python
if cond == value1:
  (haga alguna cosa)
elif cond == value2:
  (haga una cosa mas)
else:
  (haga otra cosa)
```
	
```python
def convert_temp(value, input_unit, output_unit):

  # se la unidad de input celsius y output kelvin
  if input_unit == 'celsius' and output_unit == 'kelvin':
    output = value + 273.15
  # o puede ser unidad de input celsius y output farenheit  
  elif input_unit == 'celsius' and output_unit == 'farenheit':
      output = (value * 9. / 5.) + 32.
  elif input_unit == 'kelvin' and output_unit == 'celsius':
      output = value - 273.15
  elif input_unit == 'kelvin' and output_unit == 'farenheit':
      output = ((value - 273.15) * 9. / 5.) + 32.
  elif input_unit == 'farenheit' and output_unit == 'celsius':
      output = (value - 32) * 5. / 9.
  elif input_unit == 'farenheit' and output_unit == 'kelvin':
      output = (value - 32) * 5. / 9. + 273.15
  # se la opción fuera invalida imprima un mensaje y atribuya el valor None
  else:
      output = None
       # Aquí utilizo el concepto de f-strings, que es una forma sencilla de
       # pasar variables para que se representen dentro de una cadena
      print(f'No conversion found from {input_unit} to {output_unit}.')

  return output
```
Vamos a revisar ahora. Primeramente una conversión de 'celsius' a 'kelvin'

```python
tk = convert_temp(tc, 'celsius', 'kelvin')

print(tk)
```

308.25

Ahora de  'kelvin' a 'farenheit'

```python
tf = convert_temp(tk, 'kelvin', 'farenheit')

print(tf)
```
95.18000000000004

Ahora veremos que nos dice la función `else` 

```python
tk = convert_temp(tc, 'celsius', 'keuvin')
```

No conversion found from celsius to keuvin.

¿Qué pasa si queremos convertir más de un valor? Podemos usar una lista para definir los valores y un `for para aplicar la función a cada uno de ellos


```python
# valores en celsius
tc = [35, 22, 17, 14.5]

# valores en kelvin comienza cpon una lista vacia
tk = []

for value in tc:
    # valor es convertido de celsius a kelvin
    output_value = convert_temp(value, 'celsius', 'kelvin')

    # valor convertido y adicionado a la lista
    tk.append(output_value)

print(tk)
```

[308.15, 295.15, 290.15, 287.65]


También podemos usar la biblioteca `numpy` que nos permite hacer cálculos de forma vectorizada. Para importar un paquete hacemos

```PYTHON
import numpy as np

```

El `as np` significa que para cada función o clase que llamo numpy, en lugar de escribir numpy., puedo hacer np., lo que hace que escribir código sea más rápido. Luego convertimos la lista tc en un objeto de tipo numpy.ndarray

```python
tc_arr = np.array(tc)

# aplicamos la conversión de una vez
tk_arr = convert_temp(tc_arr, 'celsius', 'kelvin')

print(tk_arr)
```

[308.15 295.15 290.15 287.65]

Y al final, ¿qué es un objeto? Un objeto se compone de atributos, que son básicamente características del objeto, así como de métodos, que son cosas que le pedimos que haga al objeto. En el ejemplo de la figura a continuación, vemos algunos atributos del objeto Perrito, como el nombre, la raza y el tamaño, así como algunos métodos como 'buscar' (=buscar) y 'hacerse el muerto' (=hacerse el muerto). La estructura básica de un objeto se da a continuación.

![tormenta](https://user-images.githubusercontent.com/101900012/223220348-08070b23-1eb5-4985-be36-f0669edff947.png)


