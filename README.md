# Seminario web para Desafíos AgTech 2020

![](https://github.com/yabellini/curso_rgee/blob/main/flyer_seminario_2020.jpg)

## Requisitos previos

### Google Earth Engine
Necesitamos que te registres en la herramienta para poder utilizarla durante el curso, para ello debes entrar en este link:

https://signup.earthengine.google.com/

### R y RStudio

Asumimos que tenes instalado R y RStudio, si no es así [seguí estas intrucciones](https://paocorrales.github.io/deExcelaR/instalacion.html) que Paola Corrales y Elio Campitelli escribieron de forma tan clara.

### Paquetes de R para trabajar con datos espaciales

Vas a tener que instalar una serie de paquetes que te permiten trabajar con datos espaciales, algunos los usaremos durante el seminario web.

#### Paquetes para trabajo con datos
`install.packages("tidyverse")`

#### Paquetes para trabajo con datos espaciales: r-spatial

```{r}
install.packages("sf") # para trabajar con datos vectoriales y rgee depende de sf
install.packages("raster") # para trabajar con datos raster.
install.packages("mapedit") #para trabajar con mapas interactivos.
install.packages("tmap") # para generar mapas temáticos.
```

#### Paquetes para trabajo con GEE

Para instalar **rgee** desde GitHub ejecutar este código de R:

`remotes::install_github("r-spatial/rgee")`

Si el código anterior te da error puede ser que necesites instalar la librería **remotes**

`install.packages('remotes')`

y luego puedas ejecutar `remotes::install_github('r-spatial/rgee')` sin problemas.

Es necesario instalar miniconda para que **rgee** funcione. La función `ee_intall()` se encarga de esta tarea.  Se ejecuta solamente una vez.

```{r}
library(rgee)  # cargamos el paquete rgee
ee_install() # pedimos que instale miniconda

# Inicializar Earth Engine! (vamos a necesitar tener nuestro usuario habilitado)
ee_Initialize()
```

Adicionalmente, si tuviste algún problema durante la instalación estas funciones pueden ser útiles para comprobar el estado de las dependencias de rgee y eliminar las credenciales. 

```{r}
ee_check() # Verifica las dependencias que no son de R
ee_clean_credentials() # Eliminar credenciales de un usuario específico
ee_clean_pyenv() # Eliminar variables del sistema
```

## Fuentes

* 250 ejemplos de uso de **rgee**: https://csaybar.github.io/rgee-examples/
* Teledetección y bandas mutiespectrales: https://mappinggis.com/2019/05/combinaciones-de-bandas-en-imagenes-de-satelite-landsat-y-sentinel/
* Manual de agricultura de precisión utilizando imágenes satelitales: http://www.rederural.gov.pt/centro-de-recursos/send/10-inovacao/1860-agricultura-de-precisao-com-imagens-de-satelite-manual-de-boas-praticas-agricolas

