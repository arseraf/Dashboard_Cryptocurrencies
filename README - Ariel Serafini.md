

### ANÁLISIS DE MERCADO DE CRIPTOMONEDAS ###
##### Por Ariel Serafini #####

#
Con el fin de realizar un análisis del mercado de las criptomonedas, se debía contar con datos fiables y en tiempo real que indiquen tanto los valores actuales como históricos de las criptomonedas elegidas. Se decidió realizar el trabajo en PowerBI, software que permitió recompilar los datos, trabajarlos y exponerlos. 
 
Como criterio de elección, se seleccionaron las 10 criptomonedas con mayor capitalización de mercado haciendo par con la única Stable Coin de esa selección (USDT).

Criptomonedas elegidas: 
- Bitcoin (BTC)
- Ethereum (ETH)
- Tether (USDT)
- BNB (BNB)
- XRP (XRP)
- Solana (SOL)
- Dogecoin (DOGE)
- Polkadot (DOT)
- Polygon (MATIC)
- Shiba Inu (SHIB)



### Reporte de obtención y calidad de datos: 


### API ###
Para la obtención de datos se utilizó la API provista por el Exchange de criptomonedas FTX.

El acceso a la API se realizó mediante la siguiente URL:

https://ftx.com/api

Para obtener datos en tiempo real de una criptomoneda en particular, se debía agregar lo siguiente:

https://ftx.com/api/markets/{market_name}

con {market_name}: el par deseado (por ejemplo BTC/USDT).
Esta consulta devuelve un archivo JSON con un conjunto de datos de los cuales se utilizaron los siguientes:
- "name" (Nombre del par)
- "price" (Precio actual)
- "change1h" (Cambio del precio respecto a una hora)
- "change24h" (Cambio del precio respecto al día anterior)
- "volumeUsd24h" (Volumen en las últimas 24 horas)


Si, en cambio, se querían obtener los datos históricos se debía consultar mediante la siguiente URL:

https://ftx.com/api/markets/{market_name}/candles?resolution={resolution}

con {resolution}: resolución de las velas en segundos. 

Dado que la API devuelve un máximo de 1500 valores, para cada criptomoneda fueron solicitadas dos resoluciones distintas: un relevamiento cada 5 minutos (resolution = 300) y uno por cada dia (resolution = 86400).


Estas URL fueron cargadas en PowerBI, donde automáticamente se creaban tablas de cada criptomoneda. Dado que la calidad de dato provista por la API era muy buena, el único procedimiento que se le realizó a los datos fue el de darle formato a las columnas utilizadas. Por ejemplo, a la columna "change1h" se le dio carácter de procentaje, a la columna "price" de dinero, etc.


### DASHBOARD ##

Realizado en PowerBI, en primer lugar nos encontramos con un relevamiento de la selección de criptomonedas en dos páginas, cada una con sus datos en tiempo real más interesantes. El fin de este index es poder identificar rápidamente el comportamiento de una criptomoneda. 
Para acceder a una vista detallada, se debe hacer click en la criptomoneda deseada. 

Allí se accede a sus datos más interesantes, seguidos de un gráfico con el historial completo de su precio y el volumen de transacciones más abajo.
Es posible observar sobre el gráfico distintas medias móviles que pueden ser activadas apretando sobre el debido botón. 

El dashboard también cuenta con una calculadora que se accede desde la página prinicpal apretando su icono situado sobre el márgen izquierdo. Su función es permitir una rápida conversión entre criptomonedas. 


















