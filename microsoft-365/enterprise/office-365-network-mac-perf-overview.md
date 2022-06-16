---
title: Conectividad de red en el Centro de Administración de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 06/15/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.reviewer: pandrew1
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
description: Introducción a la conectividad de red en el Centro de Administración de Microsoft 365
ms.openlocfilehash: 5c360820c39be6ec1c42ecdfa0a045a51716e408
ms.sourcegitcommit: 18bc521a88b7b521bccb0e69d02deac764218087
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2022
ms.locfileid: "66115663"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center"></a>Conectividad de red en el Centro de Administración de Microsoft 365

El Centro de Administración de Microsoft 365 ahora incluye métricas de conectividad de red agregadas recopiladas del inquilino de Microsoft 365 y disponibles para que solo los usuarios administrativos puedan verlas en el inquilino.

> [!div class="mx-imgBorder"]
> ![Herramienta de prueba de conectividad de red.](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**Las evaluaciones de red y la** **información de red** se muestran en el Centro de Administración de Microsoft 365, en **Health | Conectividad de red**.

> [!div class="mx-imgBorder"]
> ![Página Rendimiento de red.](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

> [!NOTE]
> La conectividad de red en el Centro de Administración admite inquilinos en WW Commercial y Alemania, pero no GCC Moderate, GCC High, DoD o China.

Cuando navegue por primera vez a la página de rendimiento de red, tendrá que configurar las ubicaciones para ver el mapa del rendimiento de la red global, una evaluación de red con ámbito para todo el inquilino, porcentaje de los usuarios que trabajan de forma remota e in situ y una lista de problemas actuales para tomar medidas o investigar más. En el panel de información general, puede explorar en profundidad para ver las métricas y problemas de rendimiento de red específicos por ubicación. Para obtener más información, consulte [Introducción al rendimiento de red en el Centro de Administración de Microsoft 365](#network-connectivity-overview-in-the-microsoft-365-admin-center).

Para acceder a la página de conectividad de la red, debe ser administrador de la organización en Microsoft 365. El rol administrativo de Lector de informes tendrá acceso de lectura a esta información. Para configurar ubicaciones y otros elementos de conectividad de red, un administrador debe tener el rol Administrador de soporte técnico de servicio.

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Requisitos previos para que aparezcan las evaluaciones de conectividad de red

Para empezar, active la opción de participación de ubicación para recopilar automáticamente datos de dispositivos mediante Windows Location Services, vaya a la lista Ubicaciones para agregar o cargar datos de ubicación o ejecute la prueba de conectividad de red Microsoft 365 desde las ubicaciones de office. Estas tres opciones para la información de ubicación de la oficina se detallan a continuación. Aunque la conectividad de red se puede evaluar en toda la organización, deberá realizarse cualquier mejora de diseño de red para ubicaciones de oficina específicas. Se proporciona información de conectividad de red para cada ubicación de office una vez que se pueden determinar esas ubicaciones. Hay tres opciones para obtener evaluaciones de red de las ubicaciones de su oficina:

### <a name="1-enable-windows-location-services"></a>1. Habilitar los servicios de ubicación de Windows

Para esta opción, debe tener al menos dos equipos que se ejecuten en cada ubicación de la oficina que admitan los requisitos previos. OneDrive para Windows versión debe estar actualizado e instalado en cada equipo. Las pruebas de red solo se ejecutan una vez al día de forma aleatoria. Las medidas de red están previstas para agregarse pronto a otras aplicaciones cliente de Office 365.

Windows servicio de ubicación debe dar su consentimiento en las máquinas. Para probar esto, ejecute la aplicación **de Mapas** y localícese. Se puede habilitar en una sola máquina con **Configuración | Privacidad | Ubicación** en la que se debe habilitar la opción _Permitir que las aplicaciones accedan a su ubicación_. Windows el consentimiento de Location Services se puede implementar en equipos con MDM o directiva de grupo con la configuración _LetAppsAccessLocation_.

No es necesario agregar ubicaciones en el Centro de Administración con este método, ya que se identifican automáticamente en la resolución de la ciudad. No se mostrarán varias ubicaciones de oficina dentro de la misma ciudad al usar Windows Location Services. La información de ubicación se redondea a los 300 metros más cercanos por 300 metros para que no se acceda a información de ubicación más precisa. El uso de Windows Location Services para las medidas de red está desactivado de forma predeterminada para los clientes. Debe habilitarlo en el control flotante Conectividad de red Configuración ubicación.

   > [!div class="mx-imgBorder"]
   > ![Habilitar ubicación](../media/m365-mac-perf/m365-mac-perf-location-enable.png)

Las máquinas deben tener redes Wi-Fi en lugar de un cable Ethernet. Las máquinas con un cable Ethernet no tienen información de ubicación precisa.

Las muestras de medida y las ubicaciones de oficina deben empezar a aparecer 24 horas después de que se cumplan estos requisitos previos. Office ubicaciones detectadas de Windows Location Services se agregan por ciudad y se conservan en la vista durante 90 días después de que ya no se reciban muestras. Si decide cambiar a las ubicaciones de oficina agregadas por el administrador con la información de subred de LAN, puede deshabilitar Windows Location Services y ocultar todas las ubicaciones detectadas. Se quitarán después del período de 90 días.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Agregar ubicaciones y proporcionar información de subred LAN

Para esta opción, no se requiere Windows Location Services ni Wi-Fi. La OneDrive para Windows versión debe estar actualizada e instalada en al menos un equipo en la ubicación y debe conocer la información de subred de LAN para cada una de las oficinas. Esta opción permite varias ubicaciones de oficina por ciudad y puede asignar un nombre a las ubicaciones de la oficina. También puede cargarlos desde otros orígenes.

Asegúrese de agregar también ubicaciones en la **página de ubicaciones** o importarlas desde un archivo CSV. Las ubicaciones agregadas deben incluir la información de subred de la LAN de office. En el cuadro de diálogo para agregar o editar una ubicación, puede especificar un número de subredes LAN y una serie de subredes IP de salida públicas. Las subredes LAN son necesarias y una de ellas debe coincidir con el atributo de subred LAN en una evaluación de red recibida para que aparezcan los resultados. No se admiten super nets, por lo que la subred LAN debe coincidir exactamente.

Normalmente, las subredes LAN son intervalos de direcciones IP privadas tal como se define en RFC1918, de modo que es probable que el uso de direcciones IP públicas como subredes LAN sea incorrecto. El cuadro de diálogo mostrará sugerencias de subredes LAN que se han visto en las pruebas de evaluación de red recientes de su organización para que pueda elegir.

Si agrega direcciones IP de salida públicas, se usan como diferenciador secundario y están pensadas para cuando tiene varios sitios que usan los mismos intervalos de direcciones IP de subred LAN. Para asegurarse de que los resultados de la prueba aparecen, debe empezar dejando los intervalos de direcciones IP de salida públicos en blanco. Si se incluyen, un resultado de prueba debe coincidir con uno de los intervalos de direcciones IP de la subred LAN y uno de los intervalos de direcciones IP de salida públicas.

Esta opción le permite tener varias oficinas definidas dentro de una ciudad.

Todas las medidas de prueba de las máquinas cliente incluyen la información de subred de LAN, que se correlaciona con los detalles de ubicación de office que ha especificado. Las muestras de medida y las ubicaciones de oficina deben empezar a aparecer 24 horas después de que se cumplan estos requisitos previos.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Recopilación manual de informes de prueba con la herramienta de prueba de conectividad de red Microsoft 365

Para esta opción, debe identificar a una persona en cada ubicación. Pídales que busquen [Microsoft 365 prueba de conectividad de red](https://connectivity.office.com) en una máquina Windows en la que tengan permisos administrativos. En el sitio web, deben iniciar sesión en su cuenta de Office 365 para la misma organización en la que desea ver los resultados. A continuación, deben hacer clic en **Ejecutar prueba**. Durante la prueba, hay una versión EXE de prueba de conectividad descargada. Deben abrirlo y ejecutarlo. Una vez completadas las pruebas, el resultado de la prueba se carga en el Centro de Administración.

Los informes de prueba se vinculan a una ubicación si se agregaron con información de subred LAN; de lo contrario, solo se muestran en la ubicación de ciudad detectada.

Los ejemplos de medida y las ubicaciones de oficina deben empezar a aparecer entre 2 y 3 minutos después de que se complete un informe de prueba. Para obtener más información, consulte [Microsoft 365 prueba de conectividad de red](office-365-network-mac-perf-onboarding-tool.md).

> [!NOTE]
> Actualmente, al agregar las ubicaciones de office a Microsoft 365 conectividad de red en el Centro de administración de Microsoft 365, solo puede proporcionar direcciones IPv4 para las subredes LAN. Egress direcciones IP deben usar IPv4.

## <a name="how-do-i-use-this-information"></a>Cómo usar esta información?

**Network Insights**, sus recomendaciones de rendimiento y evaluaciones de red relacionadas están diseñadas para ayudar a diseñar perímetros de red para las ubicaciones de su oficina. Cada información proporciona detalles sobre las características de rendimiento de un problema de red común específico para cada ubicación geográfica en la que los usuarios acceden a su inquilino. **Las recomendaciones de rendimiento** para cada información de red ofrecen cambios específicos en el diseño de la arquitectura de red que puede realizar para mejorar la experiencia del usuario relacionada con Microsoft 365 conectividad de red. La evaluación de red muestra cómo la conectividad de red afecta a la experiencia del usuario, lo que permite comparar las distintas conexiones de red de ubicación de usuario.

**Las evaluaciones de red** destilan un agregado de muchas métricas de rendimiento de red en una instantánea del estado de la red empresarial, representada por un valor de puntos de 0 a 100. Las evaluaciones de red se limitan tanto a todo el inquilino como a cada ubicación geográfica desde la que los usuarios se conectan a su inquilino, lo que proporciona a los administradores de Microsoft 365 una manera fácil de captar instantáneamente un resultado del estado de la red de la empresa y explorar en profundidad rápidamente un informe detallado de cualquier ubicación de oficina global.

Las empresas complejas con varias ubicaciones de oficina y arquitecturas perimetrales de red no triviales pueden beneficiarse de esta información durante su incorporación inicial a Microsoft 365 o para corregir los problemas de rendimiento de red detectados con el crecimiento del uso. Por lo general, esto no es necesario para las pequeñas empresas que usan Microsoft 365 o cualquier empresa que ya tenga conectividad de red sencilla y directa. Se espera que las empresas con más de 500 usuarios y varias ubicaciones de oficina se beneficien más.

## <a name="enterprise-network-connectivity-challenges"></a>Enterprise desafíos de conectividad de red

> [!div class="mx-imgBorder"]
> ![Red del cliente a la nube.](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Muchas empresas tienen configuraciones perimetrales de red, que han crecido con el tiempo y están diseñadas principalmente para dar cabida al acceso al sitio web de Internet de los empleados, donde la mayoría de los sitios web no se conocen de antemano y no son de confianza. El enfoque predominante y necesario es evitar ataques de malware y phishing de estos sitios web desconocidos. Esta estrategia de configuración de red, aunque resulta útil por motivos de seguridad, puede provocar la degradación de Microsoft 365 el rendimiento del usuario y la experiencia del usuario.

## <a name="how-we-can-solve-these-challenges"></a>Cómo podemos resolver estos desafíos

Las empresas pueden mejorar la experiencia general del usuario y proteger su entorno siguiendo [Office 365 principios de conectividad](./microsoft-365-network-connectivity-principles.md) y mediante la característica de conectividad de red Administración de Microsoft 365 Center. En la mayoría de los casos, seguir estos principios generales tendrá un impacto positivo significativo en la latencia del usuario final, la confiabilidad del servicio y el rendimiento general de Microsoft 365.

A veces se pide a Microsoft que investigue los problemas de rendimiento de red con Microsoft 365 para clientes empresariales de gran tamaño, y estos suelen tener una causa principal relacionada con la infraestructura perimetral de red del cliente. Cuando se encuentra una causa principal común de un problema perimetral de red del cliente, buscamos identificar medidas de prueba sencillas. Una prueba con un umbral de medida que identifica un problema específico es útil porque podemos probar la misma medida en cualquier ubicación, indicar si esta causa raíz está presente allí y compartirla como información de red con el administrador.

Algunas conclusiones de red simplemente indicarán un problema que necesita más investigación. Una información de red en la que tenemos suficientes pruebas para mostrar una acción de corrección específica para corregir la causa raíz se muestra como una **acción recomendada**. Estas recomendaciones, basadas en métricas dinámicas que revelan valores que están fuera de un umbral predeterminado, son mucho más valiosas que los consejos de procedimientos recomendados generales, ya que son específicas de su entorno y mostrarán la mejora real una vez realizados los cambios recomendados.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Introducción a la conectividad de red en el Centro de Administración de Microsoft 365

Microsoft tiene medidas de red existentes de varios clientes de escritorio y web de Office, que admiten el funcionamiento de Microsoft 365. Estas medidas se usan ahora para proporcionar información de diseño de arquitectura de red y una evaluación de red, que se muestran en la página **Conectividad** de red del Centro de Administración de Microsoft 365.

De forma predeterminada, la información de ubicación aproximada asociada a las medidas de red identifica la ciudad donde se encuentran los dispositivos cliente. La evaluación de red en cada ubicación se muestra con color y el número relativo de usuarios en cada ubicación se representa por el tamaño del círculo.

> [!div class="mx-imgBorder"]
> ![Mapa de información general de Network Insights.](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

En la página de información general también se muestra la evaluación de red para el cliente como promedio ponderado en todas las ubicaciones de la oficina.

> [!div class="mx-imgBorder"]
> ![Evaluación de red.](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Puede ver una vista de tabla de las ubicaciones donde se pueden filtrar, ordenar y editar en la pestaña **Ubicaciones** . Las ubicaciones con recomendaciones específicas también pueden incluir una posible mejora de latencia estimada. Esto se calcula tomando la latencia mediana de los usuarios de la organización en la ubicación y restando la latencia mediana de todas las organizaciones de la misma ciudad.

> [!div class="mx-imgBorder"]
> ![Ubicaciones de Network Insights.](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="remote-worker-assessment-and-user-connection-metrics"></a>Evaluación de trabajos remotos y métricas de conexión de usuario

Clasificamos los registros de tráfico de red como usuarios remotos o in situ y mostramos sus porcentajes en la sección de métricas de conexión de usuario del panel de información general. En el caso de las ciudades en las que tiene usuarios remotos, encontrará la puntuación de evaluación de red remota específica de la ubicación al abrir la página de esa ubicación. La lista de ubicaciones tendrá ubicaciones de oficina y ciudades de trabajo remotas, que se pueden filtrar y ordenar. Proporcionamos la puntuación de evaluación de trabajo remoto, con desglose de puntos para Exchange, SharePoint y Teams.

Las conclusiones de redes de usuarios domésticos se agregan y notifican a nivel de ciudad y se limitan a las ciudades con un mínimo de 5 empleados remotos. No estamos identificando empleados individuales que trabajan desde casa.

Las ubicaciones se clasifican automáticamente como in situ o remotas, sin embargo, tiene la opción de escribir todas las direcciones IP de salida in situ manualmente para garantizar una clasificación del 100 %. Si decide realizar esta ruta, tendrá que activar la casilla **Escribir manualmente todas las direcciones IP de salida in situ** en el control flotante Ubicaciones Configuración después de agregar todas las direcciones IP de salida. Cuando esto se hace, todos los registros de tráfico de red de las direcciones IP de salida que ha marcado como in situ siempre se clasificarán como oficinas y todas las demás direcciones IP de salida se clasificarán como remotas.

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Resumen y conclusiones específicos del rendimiento de la red de ubicación de office

Al seleccionar una ubicación de oficina, se abre una página de resumen específica de la ubicación que muestra los detalles de la salida de red que se ha identificado a partir de las medidas de esa ubicación de la oficina.

> [!div class="mx-imgBorder"]
> ![Detalles de Información de red por ubicación.](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Se muestra un mapa de la red perimetral para los usuarios de la organización en la ubicación con algunos o todos estos elementos:

- **Office ubicación**: la ubicación de la oficina de la página que está mirando
- **Perímetro de red** : ubicación de la dirección IP de origen para las conexiones desde la ubicación de la oficina. Esto depende de la precisión de las bases de datos de ubicación de IP geográfica.
- **Exchange servicio óptimo:** una de las puertas frontales de servicio Exchange recomendadas a las que deben conectarse los usuarios de esta ubicación de la oficina
- **Exchange puerta de recepción sub-óptima**: una puerta de servicio Exchange a la que los usuarios están conectados, pero no se recomienda
- **SharePoint servicio óptimo:** una de las puertas frontales de servicio SharePoint recomendadas a las que deben conectarse los usuarios de esta ubicación de la oficina
- **SharePoint puerta de recepción de servicio sub-óptima**: una puerta de servicio de SharePoint a la que los usuarios están conectados, pero no se recomienda
- **Servidor de resolución recursiva dns**: la ubicación de una base de datos de IP geográfica del solucionador recursivo DNS detectado que se usa para Exchange Online (si está disponible)
- **Servidor proxy** : la ubicación de una base de datos de IP geográfica del servidor proxy detectado (si está disponible)

La página de resumen de ubicación de la oficina también muestra la evaluación de la red de la ubicación, el historial de evaluación de red, una comparación de la evaluación de esta ubicación con otros clientes de la misma ciudad y una lista de conclusiones y recomendaciones específicas que puede realizar para mejorar el rendimiento y la confiabilidad de la red.

Las comparaciones entre clientes de la misma ciudad se basan en la expectativa de que todos los clientes tengan acceso igual a los proveedores de servicios de red, la infraestructura de telecomunicaciones y los puntos de presencia cercanos de la red de Microsoft.

Los nombres de ubicación se pueden personalizar al agregar una nueva ubicación o editar una ubicación existente en el control flotante de ubicación. Esto le proporciona la flexibilidad de personalizar los nombres de ubicación en cualquier momento. Además, al agregar subredes LAN directamente en el control flotante de ubicación, se muestra una lista desplegable de subredes LAN coincidentes temporalmente entre las que puede seleccionar. También se pueden agregar y editar nombres de circuito para direcciones IP de salida de oficina específicas.

La pestaña de detalles de la página de ubicación de la oficina muestra los resultados de mediciones específicas que se usaron para obtener las conclusiones, las recomendaciones y la evaluación de red. Esto se proporciona para que los ingenieros de red puedan validar las recomendaciones y tener en cuenta cualquier restricción o detalle en su entorno. También encontrará el número estimado de usuarios para las muestras recopiladas en esas oficinas, así como los trabajadores remotos de esa ciudad.

> [!div class="mx-imgBorder"]
> ![Detalles específicos de la ubicación.](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)

## <a name="sharing-network-assessment-data-with-microsoft"></a>Uso compartido de datos de evaluación de red con Microsoft

De forma predeterminada, las evaluaciones de red de su organización y la información de red se comparten con los empleados de Microsoft. Esto no incluye ningún dato personal del personal, sino solo las métricas de evaluación de red específicas y la información de red que se muestran en el centro de administración para las ubicaciones de su oficina. Tampoco incluye los nombres de ubicación de la oficina ni las direcciones de la calle, por lo que tendría que decirles la ciudad y el identificador de soporte técnico de la oficina que desea analizar. Si se desactiva, los ingenieros de Microsoft con los que está analizando la conectividad de red no podrán ver ninguna de esta información. Al habilitar esta configuración solo se comparten datos futuros a partir del día siguiente a su habilitación.

## <a name="csv-import-for-lan-subnet-office-locations"></a>Importación de CSV para ubicaciones de oficina de subred LAN

Para la identificación de la oficina de subred de LAN, debe agregar cada ubicación con antelación. En lugar de agregar ubicaciones de oficina individuales en la pestaña **Ubicaciones** , puede importarlas desde un archivo CSV. Es posible que pueda obtener estos datos de otros lugares donde los haya almacenado, como el panel de calidad de llamadas o los sitios y servicios de Active Directory.

En el archivo CSV, una ubicación de ciudad detectada se muestra en la columna userEntered como en blanco y una ubicación de office agregada manualmente se muestra como 1.

1. En la ventana principal _Conectividad a Microsoft 365_, haga clic en la pestaña **Ubicaciones**.

1. Haga clic en el botón **Importar** justo encima de la lista de ubicaciones. Aparecerá el control flotante **Importar ubicaciones de office** .

   > [!div class="mx-imgBorder"]
   > ![Mensaje de importación CSV.](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Haga clic en el vínculo **Descargar ubicaciones de oficina actuales (.csv)** para exportar la lista de ubicaciones actuales a un archivo CSV y guardarlo en el disco duro local. Esto le proporcionará un CSV con formato correcto con encabezados de columna a los que puede agregar ubicaciones. Puede dejar las ubicaciones exportadas existentes tal como están; no se duplicarán al importar el CSV actualizado. Si desea cambiar la dirección de una ubicación existente, se actualizará al importar el ARCHIVO CSV. No se puede cambiar la dirección de una ciudad detectada.

1. Abra el archivo CSV y agregue las ubicaciones rellenando los campos siguientes en una nueva línea para cada ubicación que quiera agregar. Deje todos los demás campos en blanco; se omitirán los valores especificados en otros campos.

   1. **userEntered** (obligatorio): debe ser 1 para agregar una nueva ubicación de oficina de subred LAN.
   1. **Nombre** (obligatorio): nombre de la ubicación de la oficina
   1. **Dirección** (obligatorio): la dirección física de la oficina
   1. **Latitud** (opcional): rellenado a partir de Bing búsqueda de mapas de la dirección si está en blanco
   1. **Longitud** (opcional): rellenada a partir de Bing búsqueda de mapas de la dirección si está en blanco
   1. **Egress intervalos de direcciones IP 1 a 5** (opcional): para cada intervalo, escriba el nombre del circuito seguido de una lista separada por espacios de direcciones CIDR IPv4 válidas. Estos valores se usan para diferenciar varias ubicaciones de office en las que se usan las mismas direcciones IP de subred LAN. Egress intervalos de direcciones IP todos deben tener un tamaño de red /24 y /24 no se incluye en la entrada.
   1. **LanIps** (obligatorio): enumere los intervalos de subred de LAN que se usan en esta ubicación de office. Los identificadores de subred de LAN deben tener un tamaño de red CIDR incluido donde el tamaño de red puede estar entre /8 y /29. Varios intervalos de subredes LAN se pueden separar por coma o punto y coma.

1. Cuando haya agregado las ubicaciones de la oficina y guardado el archivo, haga clic en el botón **Examinar** situado junto al **Upload el campo completado** y seleccione el archivo CSV guardado.

1. El archivo se validará automáticamente. Si hay errores de validación, verá el mensaje de error: _Hay algunos errores en el archivo de importación. Revise los errores, corrija el archivo de importación y vuelva a intentarlo._ Haga clic en el vínculo **Abrir detalles de error** para obtener una lista de errores de validación de campos específicos.

   > [!div class="mx-imgBorder"]
   > ![Mensaje de error de importación CSV.](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Si no hay errores en el archivo, verá el mensaje: _El informe está listo. Se encontraron ubicaciones x para agregar y x ubicaciones para actualizar._ Haga clic en el botón **Importar** para cargar el ARCHIVO CSV.

   > [!div class="mx-imgBorder"]
   > ![Mensaje listo para importación CSV.](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="cqd-tsv-import-for-lan-subnet-office-locations"></a>Importación de TSV de CQD para ubicaciones de oficina de subred LAN

Si ha cargado datos de compilación en el panel de calidad de llamadas, puede agregar esas ubicaciones aquí para empezar a evaluar su conectividad de red. Esto no afectará a las ubicaciones existentes.

[Vaya a Upload de datos de inquilino](https://cqd.teams.microsoft.com/spd/#/TenantDataUpload) en El panel de calidad de llamadas. Si ha cargado los datos de compilación, verá una opción para descargarlos en un archivo .tsv. Descargue el archivo .tsv del panel de calidad de llamadas y cárguelo en el control flotante CQD siguiendo los pasos siguientes. Si desea crear el archivo .tsv manualmente, alinee el esquema con el de Upload archivo de datos de compilación o pruebe en su lugar la importación csv para ubicaciones de oficina de subred LAN.

1. En la ventana principal Conectividad a Microsoft 365, haga clic en la pestaña **Ubicaciones**.

2. Haga clic en el botón **Administrar varias ubicaciones** justo encima de la lista de ubicaciones.

   > [!div class="mx-imgBorder"]
   > ![Menú Administrar varias ubicaciones.](../media/m365-mac-perf/m365-mac-perf-import-cqd-manage-multiple.png)

3. Haga clic en **agregar ubicaciones desde el panel de calidad de** llamadas, aparecerá el control flotante **Agregar ubicaciones desde el panel de calidad de llamadas** .

   > [!div class="mx-imgBorder"]
   > ![Agregue ubicaciones desde el control flotante Panel de calidad de llamadas.](../media/m365-mac-perf/m365-mac-perf-import-cqd-add-locations.png)

4. Haga clic en el botón **Examinar** situado junto al campo **Seleccionar un archivo .tsv para cargar** y seleccione el archivo TSV guardado. Asegúrese de que el valor del archivo está separado por tabulaciones.

5. El archivo se validará y analizará automáticamente en la lista de ubicaciones de office. Si hay errores de validación, el control flotante **No se pudo cargar el archivo** aparece para enumerar los errores.

   > [!div class="mx-imgBorder"]
   > ![No se pudo cargar el control flotante de archivos.](../media/m365-mac-perf/m365-mac-perf-import-cqd-couldnt-upload.png)

6. Si no hay errores en el archivo, verá el mensaje: _El archivo test.tsv está cargado y listo. Seleccione Importar para cargar la información._

   > [!div class="mx-imgBorder"]
   > ![Seleccione un archivo .tsc que se va a cargar.](../media/m365-mac-perf/m365-mac-perf-import-cqd-select-tsv.png)

7. Haga clic **en Upload** botón situado en la parte inferior del panel para cargar las ubicaciones de la oficina.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="what-is-a-microsoft-365-service-front-door"></a>¿Qué es una puerta de servicio Microsoft 365?

La puerta principal del servicio Microsoft 365 es un punto de entrada en la red global de Microsoft donde Office clientes y servicios finalizan su conexión de red. Para una conexión de red óptima a Microsoft 365, se recomienda que la conexión de red finalice en la puerta principal Microsoft 365 más cercana.

> [!NOTE]
> Microsoft 365 servicio front door no tiene ninguna relación directa con el producto Azure Front Door Service disponible en Azure Marketplace.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>¿Cuál es una puerta de servicio Microsoft 365 óptima?

Una puerta de servicio Microsoft 365 óptima es la más cercana a la salida de la red, generalmente en su ciudad o área metropolitana. Use la [herramienta de prueba de conectividad Microsoft 365](office-365-network-mac-perf-onboarding-tool.md) para determinar la ubicación de la puerta principal del servicio Microsoft 365 en uso y la puerta de recepción de servicio óptima. Si la herramienta determina que la puerta principal en uso es óptima, se conecta de forma óptima a la red global de Microsoft.

### <a name="what-is-an-internet-egress-location"></a>¿Qué es una ubicación de salida de Internet?

La ubicación de salida de Internet es la ubicación donde el tráfico de red sale de la red empresarial y se conecta a Internet. Esto también se identifica como la ubicación donde tiene un dispositivo de traducción de direcciones de red (NAT) y, normalmente, donde se conecta con un proveedor de servicios de Internet (ISP). Si ve una larga distancia entre su ubicación y su ubicación de salida de Internet, esto puede indicar un backhaul WAN significativo.

### <a name="what-license-is-needed-for-this-capability"></a>¿Qué licencia se necesita para esta funcionalidad?

Necesita una licencia que proporcione acceso a la Centro de administración de Microsoft 365.

## <a name="related-topics"></a>Temas relacionados

[Microsoft 365 información de red](office-365-network-mac-perf-insights.md)

[Microsoft 365 evaluación de red](office-365-network-mac-perf-score.md)

[Microsoft 365 herramienta de prueba de conectividad](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Servicios de ubicación de conectividad de red](office-365-network-mac-location-services.md)
