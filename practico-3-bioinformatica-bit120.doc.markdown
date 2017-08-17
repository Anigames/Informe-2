#<strong>Trabajo Práctico Nº3: Ensamblaje de genomas y predicción de genes</strong>

#BIT120

__Laboratorio de Bioinformática__

__Profesores:__
-

                                                                                             -Nombre: 
                                                                                             -Carrera: Ingeniería en Biotecnología
                                                                                             -Fecha de entrega: 


---

####<strong>Parte 1: El artículo genoma</strong>

####<strong>Responde:
####1. ¿Cuántos genomas han sido depositados en GOLD? ¿Son los mismos de GENBANK?
#####R.-  Al realizar una búsqueda en la base de datos de GOLD sobre el organismo <em>Neurospora crassa</em>, se encontraron 836 genomas depositados, mientras que al realizar la búsqueda del genoma del mismo organismo eucarionte en la base de datos de GENBANK, se encontraron sólo 2 entradas para <em> Neurospora crassa </em>. 
####2. ¿Cuál es la distribución de procariontes y eucariontes secuenciados?
#####R.- En GOLD, para establecer una razón de los organismos secuenciados entre eucariontes y procariontes, se encuentra un total hasta la fecha de 74176; donde las entradas respecto a eucariontes es de 12412, y si para procariontes se incluyen las entradas para bacterias, con un número de 55908 entradas, y archeas con 1231 (ausentando las entradas referentes a virus), se puede establecer una distribución en la razon:

#####(bacterias + archeas)/eucariontes = (55908+1231)/12412 = 57139/12412 = 4,60 ~ 5 ; aproximadamente una razon de 5:1.

####<strong>-Evaluando un ensamblaje de genomas.

####<strong>Responde:
####1. ¿Qué es el N50, L50, NG50?
#####R.- En primer lugar, el N50 es una medida estadística que define la calidad un montaje de secuencias, que dado un conjunto de contigs con longitudes definidas, el N50 es la longitud más corta de la secuencia al 50% del genoma, es decir, que el número de bases de todos los contigs más cortos que el N50 serán más cercanas al número de bases de todos los contigs más largos al N50. El L50 por su parte, que dado un set de contigs y cada uno con su propio largo, esta medida corresponde al menor número de contigs cuya sumatoria de los largos produce el N50. El NG50, es una medida estadística similar al N50, excepto que corresponde al 50% del tamaño del genoma conocido o estimado, que debe de ser la longitud del NG50 o más largo. 
####2. ¿Cuál es el propósito de calcular estas estadísticas?
#####R.- El propósito del cálculo de estas estadísticas, es que al utilizarse en un conjunto de longitudes contigs o scaffolds, el N50 es como la media o mediana de las longitudes, pero tiene una mayor importancia por sobre los contigs más largos, utilizándose mayoritariamente para montaje de genomas, especialmente para referenciar longitudes contigs dentro de un montaje preliminar. El L50 se utiliza al corresponder al número de contigs cuya suma de longitudes resulta en el N50. Y sobre el NG50, permite comparaciones significativas entre distintos montajes al referirse más hacia el tamaño del genoma que el tamaño del montaje como lo hace N50, donde la comparación entre valores N50 derivados de montajes con longitudes bastante diferentes, usualmente no es informativo, por lo que se recurre en este contexto al NG50.
####3. ¿Cuál es el genoma que escogiste? Adjunta la referencia.
#####R.- <em> Neurospora crassa </em> OR74A. Por un asunto de falta de información, no se escogieron las otras entradas al no encontrarse una publicación de referencia para su genoma, por lo que el genoma OR74A fue el seleccionado al contener una referencia completa (segunda publicación listada).

![Texto Alternativo](http://i.imgur.com/LFXp7vY.png)

####Referencia:

#####Maccallum I1, Przybylski D, Gnerre S, Burton J, Shlyakhter I, Gnirke A, Malek J, McKernan K, Ranade S, Shea TP, Williams L, Young S, Nusbaum C, Jaffe DB. (2009). <em>ALLPATHS 2: small genomes assembled accurately and with high continuity from short paired reads.</em> Genome Biol. 2009; 10(10): R103. 

####4. ¿Cuál es el N50 del genoma que escogiste? ¿Y el NG50?
#####R.- De acuerdo a la Tabla 1 del artículo (data de referencia), el N50 para <em> N. crassa </em> es de 665 kb. El NG50 no se encuentra listado.

![Texto Alternativo](http://i.imgur.com/PtiHhxI.png)

####5. ¿Qué tipo de tecnología se uso para secuenciar el genoma que escogiste?
#####R.- En la investigación citada, se utilizaron reads de 36 bases (fragmentos) y 26 bases (jumping) de 5 genomas microbianos con composición GC variable con tamaños hasta 40 Mb. Para secuenciar el genoma de <em>N. crassa</em>, se utilizó la tecnologia ALLPATHS2, el cual es un montador (assembler) de genomas completos el cual puede generar montajes de genomas de alta calidad utilizando reads cortos; y comparando estos resultados al utilizar los algoritmos Velvet (para montajes de genomas <em> de novo </em> y secuencias de alineamiento de reads cortos, utilizado para construir secuencias continuas de forma rápida) y EULER-SR (programa para montaje de reads <em> de novo </em> que contiene programas para la correción de errores en reads cortos). Se demostró que ALLPATHS2, generó montajes con contigs y scaffolds largos y precisos, siendo los programas EULER-SR y Velvet menos precisos.

####6. ¿Qué organismo escogiste, cuántos cromosomas tiene tu organismo y cuál es su tamaño?
#####R.- El organismo <em> Neurospora crassa </em>, con un tamaño de genoma de 39226 kb, teniendo 7 cromosomas. 

####<strong>Parte 2: Predicción de genes
####<strong>Responde:
####1.	¿Cuántos ORF o genes encontró ORFfinder?
#####R.- ORFfinder encontró 4 ORFs o genes.

![Texto Alternativo](http://i.imgur.com/rdcC6Bu.png)

####2.	¿Cuántos ORF o genes encontró Glimmer?
#####R.- GLIMMER encontró 3 ORFs o genes.

![Texto Alternativo](http://i.imgur.com/D6dsL9U.png)

####3.	¿Alguno de los genes predichos por estas herramientas coinciden?
#####R.- Para establecer coincidencias entre ambos programas, deben de poseer un mismo inicio/final y marco de lectura (frame), por lo que coinciden en el primer ORF/gen que ambos encontraron, empezando en 1 y terminando en 909, con +1 en el marco de lectura. Otra coincidencia, es en la cual en ORFfinder se muestra de 1391 a 1795, mientras que en GLIMMER, comienza en 1795 y termina en 1391, ambos con un marco de lectura de -2. Esta aparente diferencia en el inicio/final del ORF/gen, puede deberse a que en GLIMMER, si el transcrito se ubica en la hebra complementaria, la lectura será negativa al estar en la hebra negativa, por lo que la lectura se muestra en dirección reversa; de la misma manera en ORFfinder, si se selecciona el ORF/gen con un frame negativo, la secuencia mostrada en la parte inferior también da a conocer un marco de lectura inverso, por lo que sí coinciden en ese ORF/gen. Por otra parte, el ORF/gen que comienza en 1388 y termina en 948, coinciden en ambos programas en el largo y dirección, pero el marco de lectura es -2 en ORFfinder y en GLIMMER -3.
####4.	¿En qué hebra están codificados?
#####R.- En ORFfinder, el primero se ubica en la hebra directa, al ir de 1-->909, mientras que las otras 3, se ubican en la hebra complementaria al tener un marco de lectura reverso. En GLIMMER, coincide en que el orf00001 se encuentra en la hebra directa, y los siguientes dos, orf00002 y orf00003, se ubican en la complementaria al ir de 1388-->948 y 1795-->1391, respectivamente.
####5. ¿Qué tipo de programa es GLIMMER? ¿Ab initio o por homología?
#####R.- En primer lugar, <em> ab initio </em> que se refiere a "desde el principio", en Bioinformática, se refiere a buscadores de genes que usan modelos estadísticos para predecir genes desde solamente la secuencia genómica. Por su parte, GLIMMER corresponde a un programa <em> Ab initio </em> al ser un sistema para la búsqueda de genes en DNA microbial, utilizando la medida estadística de modelos de Markov interpolados para identificar regiones codificantes, a partir de una secuencia genómica.

####<strong>-Búsqueda en BLAST</strong>

####1.	Describe los resultados encontrados con respecto a los genes que encontraste con GLIMMER y ORFfinder
#####R.- Al realizar una búsqueda en BLAST, los genes encontrados provienen del organismo <em>Haemophilus influenzae</em>, donde el primer gen encontrado en ORFfinder (de 1 a 909), corresponde al gen FdhE, el cual codifica a la enzima formato deshidrogensasa; el siguiente (de 948 a 1388), es el gen Riml, que codifica a la proteína ribosomal-alanina N-acetiltransferasa; el tercer listado (de 1391 a 1795), corresponde al gen holD, el cual codifica la subunidad III de la DNA polimerasa; y el último listado en ORFfinder (de 455 a 598), no muestra resultados en BLAST ("No significant similarity found"), en donde al dirigirse al FAQ de BLAST, este error puede deberse a que alineamientos cortos pueden estar sobre el valor umbral default del valor Expect (parámetro que describe el número de "hits" que uno puede esperar para ver por chance cuando se realiza una búsqueda en la base de datos) y por lo tanto, no se entregan resultados respecto a esa secuencia.
