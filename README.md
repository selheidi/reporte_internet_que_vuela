# Análisis del estado de internet en Argentina con foco en accesos aéreos. 
![Gaucho_argentino](wifi_gaucho.jpg)

Internet es un elemento fundamental de nuestro día a día, porque, en la actualidad, estar desconectado es sinónimo de estar excluido de oportunidades para acceder a información básica, aprender y trabajar entre otros.

# Empresa
![Aero_internet](aero.jfif)

AERO es una empresa mendocina, dedicada a prestar servicios de internet y telefonía en distintas áreas de Mendoza, y actualmente otras provincias como San Juan. AERO no tiene cables, siempre llegam más lejos, a esos lugares que las grandes empresas han olvidado. También prentende "volar cada vez más rápido", mejoramndo día a día las prestaciones de servicio, y para invierte permanentemente en tecnología. Buscan fidelizar sus clientes sin tener que recurrir a contratos de permanencia difíciles de resindir, consideran que los clientes deben ser plenamente libres en sus elecciones.  

Los servicios prestados por Aero ofrecen planes desde 6 Mbps hasta 50 Mbps y se subdividen a sus clientes en dos categorías y ademas un modelo de franquicia :

* Hogares 
* Servicios corporativos: Estos últimos pensados para profesionales y empresas con múltiples necesidades de conectividad.Los servicios corporativos se caracterizan por asegurar un ancho de banda permanente, sin pérdida de rendimiento durante todo el día. Además, son servicios simétricos donde las velocidades máximas de subida y de bajada son iguales. Ante necesidades especiales, Aero dispone de anchos de banda ilimitados "DEDICADOS" con conexiones punto a punto.

* Socio local o Franquicido: Aero internet es un modelo de negocio replicable en cualquier parte del país e inclusive en el exterior. La infraestructura de red y sistema de administración remota,  permite operar en localidades lejanas a la provincia de Mendoza. Teniendo un socio local o "franquiciado", que atiende la zona adjudicada, se proyecta un crecimiento sostenido del cual se benefician ambas partes. El programa de franquicias Aero es una gran oportunidad comercial, ideal para emprendedores dispuestos a competir en un mercado de crecimiento constante.

# Objetivo 

Colaborar en el entendimiento del Mercado de Internet Fijo en Argentina, sus tendencias, tecnologías y necesidades y así poder brindar herramientas para la toma de decisiones de la empresa Aero, basada en internet sin cables. 

#Análisis 

Se realizó un exaustivo análisis de los datos provistos por ENACOM, Ente Nacional de Comunicaciones de Argentina. Este estudio se subdividió en tres partes: accesos por hogares, tecnologías y velocidades disponibles en las distintas provincias y localidades de Argentina.

Los datos fueron descargados desde la página de ENACOM en formato Excel en los casos posibles o en formato CSV. La interacción con la API no fue exitosa, solo se pudo descargar un archivo de esta manera que se detalla en el archivo del este repositorio como ETL. Los archivos fueron descargados del siguiente link: https://datosabiertos.enacom.gob.ar/dashboards/20000/acceso-a-internet/.

En el archivo EDA, se trabajó con las siguientes librerías: 
* pandas
* matplotlib.pyplot 
* seaborn 
* numpy 

Los archivos descargados en formato Excel estaban en mejor condición de formato y eran prácticamente útiles de inmediato. En algunos como en tecnología, para el archivo CSV era necesario hacer transformaciones ya que al entrar en este formato habían problemas de comas y puntos y los datos. Para conocer que valores eran correctos y cuales incorrectos sirvió hacer algunas lecturas de información adicional como el siguiente gráfico:

![accesos_tecnologia](Cantidad_accesos_doc_oficial.png)

#### Para poder explorar los Datasets se procedió de forma general de la siguiente manera: 

* Abrir el DataFrame.
* Ver las primeras filas.
* Hacer info, ver nulos, cantidad de columnas y tipo de datos de cada columna.
* Hacer conversion de tipo de formato de variables, por ejemplo object a category o int (entero) o float (flotante/decimal) según el caso.
* Reemplazar según sea el caso caracteres, por ejemplo puntos por comas. 
* Revisar unidades y corregir en caso de ser necesario. Por ejemplo millones vs miles. 
* Elimnar columnas vacías.
* Borrar duplicados.
* Cambiar nombres de columnas usando replace().
* Revisar los cambios.
* Observar datos de variables categóricas con funciones como unique() y value_counts().
* Observar datos de variables númericas con funciones como describe().
* Analizar con gráficos los outlayers y tomar decisiones si conservarlos. 
* Hacerle preguntas a los Datos contestando con tablas y gráficos
* En algunos casos, se cruza información para responder estas preguntas. 
* Se escriben observaciones en general y en particular de los gráficos. 

#### El orden de los DataFrames es el siguiente:

1) Penetración de Internet fijo por Provincia 
2) Acceso a Internet fijo por Tecnología y Provincia
3) Accesos Internet fijo por Tecnología en todo el País
4) Accesos a Internet fijo por Tecnología y Localidad
5) Acceso a Internet fijo por rangos de Velocidad de bajada y provincia
6) Listado de Localidades con Conectividad a Internet
7) Accesos a Internet fijo por Velocidad de bajada y Localidad
8) DataFrame 8  Histórico Velocidad Internet por Provincias
