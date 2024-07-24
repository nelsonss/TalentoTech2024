# **Proyecto : Eco-energy analysis of power plants**
Realizado por: Nelson Sánchez Sánchez
Bootcamp Análisis y Visualización de Datos AVDV2-45

<img src="https://lh3.googleusercontent.com/pw/AP1GczMWciNA8OuBQJLwyUDJPme-QgFozGX99R6ZqE716hapSILA47Y0h_z42QIxC5rIk7CVH-LvXHBs4yC4DhIBReYGus5JH4V3ADWc8iVQhbgl7ca4NtjieGPnwpsOjlO0W_9YNGQyOJyCFmtWRd6672HP=w2555-h820-s-no-gm?authuser=0" alt="Eco-energy analysis of power plants">


<img src="https://lh3.googleusercontent.com/pw/AP1GczO4TGUlLkudPTscZbFf9PMpyNvtpfyAns5MugRfUFiu4vewpwWA8eQln8VhguThYtH1-fqYgbbGww6S83onR0HySty8eB2_DPcKPETM07ZCf9M1_Na8ieEZHydiLH9KLp6OnSNFfNhJYFYVGnU_mXt-=w2772-h369-s-no-gm?authuser=0" alt="Descripción de la imagen">

### Selección del Proyecto
**Bases de Datos Utilizadas:**
[Global Power Plant Database](https://datasets.wri.org/dataset/globalpowerplantdatabase)

---

La "Global Power Plant Database" es una herramienta integral y fuente de información abierta para el análisis energético global. Esta base de datos contiene más de 30,000 plantas de energía de 164 países, con una amplia gama de tipos de plantas, desde térmicas (como carbón, gas, petróleo, nuclear, biomasa, desechos y geotérmica) hasta renovables (como hidroeléctrica, eólica y solar). Cada planta en la base de datos está geolocalizada, con detalles específicos sobre su capacidad de generación, propiedad, tipo de combustible y datos operacionales.

Debido a la amplitud y profundidad de los datos que proporciona esta base de datos es posible realizar diversos tipos de análisis:
- **Análisis de Capacidad y Producción**: Permite evaluar la capacidad de generación de energía por país, región o globalmente, analizar tendencias de producción a lo largo del tiempo y evaluar el crecimiento o declive de los distintos tipos de combustibles.
- **Análisis de Tipo de Combustible**: Facilita la investigación sobre la distribución de los tipos de combustibles y la comparación de la eficiencia de las plantas según su combustible principal.
- **Análisis Geoespacial**: Ofrece la capacidad de mapear plantas para visualizar la distribución geográfica y densidad, lo que es esencial para estudiar dependencias regionales y identificar áreas posiblemente desatendidas por la infraestructura actual.
- **Impacto Ambiental**: Es crucial para estimar emisiones de plantas térmicas y analizar el impacto ambiental potencial, integrando datos de plantas con datos ecológicos o demográficos.
- **Eficiencia Operacional y Estructura de Mercado**: Ayuda a analizar la eficiencia de las plantas, la concentración de la propiedad y el impacto de la propiedad privada versus estatal.
- **Pronósticos y Análisis Predictivos**: Utiliza datos históricos de generación para predecir necesidades futuras de generación de energía y modelar escenarios bajo diferentes condiciones económicas o políticas.
- **Análisis de Impacto de Políticas y Regulaciones**: Permite evaluar el impacto de políticas en el desarrollo de recursos energéticos renovables y estudiar el efecto de acuerdos internacionales en estrategias energéticas nacionales.

---

**Estructura de la Base de Datos:**


1. **Información Geográfica e Identificación:**
   - **country** (cadena): Código ISO del país donde está ubicada la planta de energía.
   - **country_long** (cadena): Nombre completo del país.
   - **name** (cadena): Nombre de la planta de energía.
   - **gppd_idnr** (cadena): Identificador único para cada planta de energía en la base de datos global.
   - **latitude** (flotante): Latitud geográfica de la planta de energía.
   - **longitude** (flotante): Longitud geográfica de la planta de energía.

2. **Especificaciones Técnicas:**
   - **capacity_mw** (flotante): Capacidad total de generación eléctrica de la planta en megavatios.
   - **primary_fuel** (cadena): Fuente principal de combustible utilizada (por ejemplo, Carbón, Gas, Hidroeléctrica, Nuclear, Solar, Eólica).
   - **other_fuel1**, **other_fuel2**, **other_fuel3** (cadena, opcional): Fuentes secundarias o terciarias de combustible, si las hay.

3. **Detalles Operativos:**
   - **commissioning_year** (flotante, opcional): Año en que la planta comenzó operaciones, importante para entender la antigüedad y tecnología de la planta.
   - **owner** (cadena, opcional): Nombre de la entidad que posee la planta de energía.

4. **Fuentes de Datos y Verificación:**
   - **source** (cadena): Nombre de la organización que proporcionó los datos.
   - **url** (cadena): Enlace a la página web de donde se obtuvieron los datos.
   - **geolocation_source** (cadena): Fuente de las coordenadas geográficas (por ejemplo, GPS, SIG, registros gubernamentales).

5. **Datos de Generación Anual:**
   - **generation_gwh_2013** a **generation_gwh_2019** (flotante, opcional): Generación eléctrica anual en gigavatios-hora para los años respectivos.
   - **generation_data_source** (cadena, opcional): Fuente de donde se obtuvieron los datos de generación.

6. **Estimaciones y Proyecciones:**
   - **estimated_generation_gwh** (varios años, flotante, opcional): Cifras estimadas de generación para varios años, utilizadas cuando no hay datos reales disponibles.

### Fuentes de Datos:

La información en la Base de Datos Global de Plantas de Energía se recolecta de múltiples fuentes para asegurar precisión y exhaustividad:

1. **Agencias Internacionales de Energía**: Como la Agencia Internacional de Energía (AIE), que proporcionan datos estandarizados sobre generación de energía y tipos de combustibles.
2. **Informes y Bases de Datos Gubernamentales**: Bases de datos nacionales y regionales que rastrean la producción de energía y la infraestructura.
3. **Compañías de Servicios Públicos**: Datos directamente de las compañías que operan las plantas de energía, que a menudo son los más precisos para detalles operativos como capacidad y generación.
4. **Imágenes Satelitales y Datos Geográficos**: Para verificar ubicaciones y capacidades de las plantas, especialmente en regiones menos accesibles.
5. **Instituciones Académicas y de Investigación**: Estudios y encuestas realizados por universidades y organizaciones de investigación también pueden contribuir con datos, particularmente para estimaciones e impactos ambientales.
6. **Datos de Fuente Abierta y Proyectos Colaborativos**: Conjuntos de datos de acceso público y agregado que recopilan información global sobre plantas de energía.

<img src="https://lh3.googleusercontent.com/pw/AP1GczOetl_6K0xFFI1Eps2gk_t8sBcGbLguXH-O12EGXtc32OmVgr1SpjEcX34CvrqvkU0tomEpuHgFibbGNxxmD9aY0uON9t0tjRUbhWD7SpKqZHFBBjM7npW2Z8u6lydNy0WFa6rN5w0BRhhs4YB_xuOU=w2772-h347-s-no-gm?authuser=0" alt="Descripción de la imagen">

   - Exploración de variables
   - Visualización de datos
   - Análisis descriptivo


<img src="https://lh3.googleusercontent.com/pw/AP1GczMhP-E_cge2AzZDw-_qJzYUaxoADgFRM-hbnWvPLi-TMKT6YCeRisGFU-uU_OvDDkIEnl_scgMyAxYdg4pBfcL-9TFdeRXp_YjxcjQBuHA7odvt-P5qcaxIzKiwfMrGYemaDaIF4xCBpp6B9v634_RC=w2772-h376-s-no-gm?authuser=0" alt="Descripción de la imagen" >

   - Selección de modelo
   - Entrenamiento y validación del modelo
   - Selección del mejor modelo
   - Interpretación del modelo

<img src="https://lh3.googleusercontent.com/pw/AP1GczMZ0ZYdiDxe6a-jCWcXRNbU8S38dJNhPFZ6-AFiW3SL9InE23Cz6UYs2pOdcP6NrVkIeH7R9CvI8K2GLZKAhSpeoV0q2SW_X0PLhLjInLZjasbXYDFMOq5DFmvDaiCWd8AvbGDvwE5PN7Yc8dtRxK9C=w2772-h437-s-no-gm?authuser=0" alt="Análisis EcoEnergéticos">
<img src="https://www.repsol.com/content/dam/repsol-corporate/es/energia-e-innovacion/subestacion%20electrica.jpg.transform/rp-rendition-md/image.jpg" alt="Análisis EcoEnergéticos">

   - Creación de visualizaciones
   - Métricas clave
   - Interactividad


