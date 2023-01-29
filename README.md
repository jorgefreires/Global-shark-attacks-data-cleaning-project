# Global shark attacks data cleaning project

En este proyecto se intenta limpiar la base de datos [global-shark-attacks](https://www.kaggle.com/datasets/teajay/global-shark-attacks), obtenido en Kaggle, sin eliminar ninguna de sus columnas. A continuación se enumeran las 23 columnas del csv y se indica lo que se ha hecho en cada una de ellas:

* **Case number:** Indice de los casos. Dado que lo importante es que sea unico, se han cambiado sus valores por un índice de valores únicos.

* **Date:** Fecha en la que se produjo el incidente. Se copiaron los valores de Case Number.1 (que indicaban la fecha) y se convirtieron al formato aaaa.mm.dd. Sin embargo, existían datos inexcatos que se sustituyeron por la palabra unknown.

* **Year:** Año en el que se produjo el incidente. Se elimino el .0 que venia al final de muchos años (aaaa.0) y se cambiaron los años desconocidos por la palabra unknwon.

* **Type:** Razón del incidente, que puede ser Boating, Unprovoked, Provoked, Questionable o Sea Disaster. Los valores nulos o desconocidos se cambiaron por la palabra unknown y Boat, Boating y Boatomg se unificaron como Boating.

* **Country:** País en el que se ha producido el incidente. Se edito valor a valor corrigiendo aquellos valores mal indicados y, en el caso de ser territorio internacional, como un oceano, se indico la región. Los datos desconocidos se indicaron con la palabra unknown.

* **Area:** Región en la que se produjo el incidente. Se cambiaron los valores nulos por la plaabra unknown, pero no se verificaron los valores uno por uno debido a la gran cantidad de valores únicos. Una vez limpia esta columna, se comprobo si se podían rellenar datos desconocidos de Country con los datos de esta columna.

* **Location:** Lugar concreto del incidente. Se cambiaron los valores nulos por la plaabra unknown, pero no se verificaron los valores uno por uno debido a la gran cantidad de valores únicos. Una vez limpia esta columna, se comprobo si se podían rellenar datos desconocidos de Country o Area con los datos de esta columna.

* **Activity:** Actividad que se estaba realizando cuando ocurrio el incidente. Se cambiaron los valores nulos por la plaabra unknown, pero no se verificaron los valores uno por uno debido a la gran cantidad de valores únicos.

* **Name:** Nombre de la persona o personas envueltas en el incidente. Se cambiaron los valores nulos y desconocidos por la palabra unknown, pero no se verificaron los valores uno por uno debido a la gran cantidad de valores únicos.

* **Sex:** Indica el sexo de la persona envuelta en el incidente siendo F: Female y M: Male. Hubo que corregir algunos valores mal puestos y cambiar los nulos y los desconocidos por la palabra unknown, excepto aquellos que se podían deducir por la columna Name.

* **Age:** Indica la edad de la persona envuelta en el incidente. Hubo que corregir muchos de sus valores y en los casos en los que hubo varios afectados se indica la media de las edades.

* **Injury:** Descripción de los daños causados. Se cambiaron los valores nulos por la palabra unknwon.

* **Fatal (Y/N):** Indica Y si el incidente fue mortal y N si no. Hubo que corregir algunos valores mal puestos y cambiar los nulos y los desconocidos por la palabra unknown.

* **Time:** Indica la hora y minuto a la que se produjo el incidente. Se arreglaron los valores para que estuvieran en formato hh:mm. Además se cambiaron los nulos y los desconocidos por la palabra unknown.

* **Species:** Indica la especie del tiburón envuelto en el incidente. Se cambiaron los valores nulos por la plaabra unknown, pero no se verificaron los valores uno por uno debido a la gran cantidad de valores únicos.

* **Investigator or Source:** Persona, entidad o ambas responsable de la investigación del ataque. Se cambiaron los valores nulos por la plaabra unknown, pero no se verificaron los valores uno por uno debido a la gran cantidad de valores únicos.

* **pdf:** Nombre del pdf asociado al incidente. No hubo que cambiar nada.

* **href formula y href:** Dos columnas iguales que contienen los liks a los pdf de los incidentes. Hubo que rellenar un valor manualmente.

* **Case number.1 y Case Number.2:** De nuevo aparecía el número de cada caso repetido en dos columnas. Se igualaron a la columna Case Number ya limpiada.

* **original order:** Orden original de los casos. No hubo que realizar ningún cambio.

* **'Unnamed: 22' y 'Unnamed: 23':** Columnas desconocidas con tan solo 1 y 2 valores cada una. Se convirtieron dichos valores y el resto de nulos a la palabra unknown.



## BONUS: Pequeño análisis explotatorio ⚙️


### Hipótesis

Una vez la base de datos está limpia, se cruzan las columnas Time y Fatal (Y/N) para probar la hipótesis de que los ataques de tiburón que se producen durante la noche tienen un mayor índice de letalidad. El resultado de este análisis exploratorio demostro que, en horario nocturno, la letalidad de los tiburones es del 33.59%, mientras que por el día este porcentaje baja hasta el 18.49%. Es por ello que, finalmente, la hipótesis de la mayor letalidad nocturna de los tiburones queda confirmada.