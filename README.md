# Curso-Python
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

## 2. Instalación de miniconda
Es preferible instalar las bibliotecas necesarias via Anaconda. Para instalar Anaconda,basta colocar los siguientes comendas en la terminal:

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
despues deñ comanda, quedará asi:

* (lfa) decker@DESKTOP-LD7TCRV:~$

