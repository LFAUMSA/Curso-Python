# Curso-Python
Autor: M.Sc. Decker Guzmán Zabalaga

Laboratorio de Fiśica de la Atmósfera (LFA)
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
## 2.2 MIniconda 
* curl -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh

* bash Miniconda3-latest-Linux-x86_64.sh

Debe reiniciar la maquina para que los cambios sean hechos:

### 2.1 Actualizar el conda

* conda update -n base -c defaults conda
### 2.2 Crear un nuevo ambiente virtual
* conda create --name <nombre_ambiente>
* Ejemplo: creacion del ambiente llamado lfa

conda create --name lfa

### 2.3 ver lista de programas instalados

* conda list
### 2.4 desactivar un ambiente virtual

* conda deactivate

Al realizar lo ultimo, el usuario de ambiente virtual cambiara al ambiente normal (base)

### 2.5 activar un ambiente

* conda activate <nombre_ambiente>

Ejemplo:

* conda activate lfa

Antes o ambiente era o (base).

* (base) decker@DESKTOP-LD7TCRV:~$

despues del comando, quedará asi:

* (lfa) decker@DESKTOP-LD7TCRV:~$

### 2.6 Borrar un ambiente 

* conda env remove --name <nombre_ambiente>

Exemplo:

* conda env remove --name lfa

### 2.7 Instalación de programas

* conda install -c conda-forge ncl
* conda install -c conda-forge gdal
* conda install -c conda-forge cdo
* conda install -c conda-forge imagemagick
* conda install -c conda-forge ncview
* conda install -c conda-forge htop
* conda install -c conda-forge parallel
* conda install -c conda-forge nco
* conda install -c conda-forge wgrib2

### 2.8 Instalación de una versión especifica de um programa

* conda install <nonbre_programa>=<version_programa>
Ejemplo: Instalar la versión de cdo 1.9.9.

* conda install cdo=1.9.9
### 2.9 Actualizar una libreria 

* conda update <nombre_libreria>

### 2.10 desinstalar una libreria 

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
 
