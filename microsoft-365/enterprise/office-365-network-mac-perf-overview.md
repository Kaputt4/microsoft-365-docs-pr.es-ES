---
title: Conectividad de red en el Centro Administración de Microsoft 365 red
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
description: Información general sobre la conectividad de red en el Centro Administración de Microsoft 365 red
ms.openlocfilehash: 8ad589ede747975ca9dcd3c81e661a2147fc1b88
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2021
ms.locfileid: "53277006"
---
# <a name="network-connectivity-in-the-microsoft-365-admin-center"></a>Conectividad de red en el Centro Administración de Microsoft 365 red

El Centro Administración de Microsoft 365 ahora incluye métricas de conectividad de red agregadas recopiladas desde el inquilino de Microsoft 365 y disponibles para que solo las puedan ver los usuarios administrativos del espacio empresarial.

> [!div class="mx-imgBorder"]
> ![Herramienta de prueba de conectividad de red](../media/m365-mac-perf/m365-mac-perf-admin-center.png)

**Las evaluaciones de** red **y las perspectivas** de red se muestran en el Centro de Administración de Microsoft 365 en **Health | Conectividad de red**.

> [!div class="mx-imgBorder"]
> ![Página de rendimiento de red](../media/m365-mac-perf/m365-mac-perf-page-nav.png)

>[!NOTE]
>La conectividad de red en el Centro de administración admite inquilinos en WW Commercial y Alemania, pero no GCC moderado, GCC High, DoD o China.

Cuando navegue por primera vez a la página de rendimiento de la red, tendrá que configurar las ubicaciones para ver el mapa del rendimiento global de la red, una evaluación de red en el ámbito de todo el inquilino, un porcentaje de los usuarios que trabajan de forma remota frente a in situ y una lista de problemas actuales en los que tomar medidas y/o investigar más. En el panel de información general, puede explorar en profundidad para ver métricas y problemas específicos de rendimiento de red por ubicación. Para obtener más información, vea [Network performance overview in the Administración de Microsoft 365 Center](#network-connectivity-overview-in-the-microsoft-365-admin-center).

Es posible que se le pida que se una a la versión preliminar pública de esta característica en nombre de su organización. La aceptación suele ocurrir inmediatamente, después de lo cual vería la página de conectividad de red.

Para obtener acceso a la página de conectividad de red, debe ser administrador de la organización en Microsoft 365. El rol administrativo Lector de informes tendrá acceso de lectura a esta información. Para configurar ubicaciones y otros elementos de conectividad de red, un administrador debe formar parte de un rol de administrador de servidor, como el rol de administrador de soporte técnico del servicio.

## <a name="pre-requisites-for-network-connectivity-assessments-to-appear"></a>Requisitos previos para que aparezcan las evaluaciones de conectividad de red

Para empezar, active la configuración de participación en la ubicación para recopilar automáticamente datos de dispositivos con servicios de ubicación de Windows, vaya a la lista Ubicaciones para agregar o cargar datos de ubicación o ejecute la prueba de conectividad de red de Microsoft 365 desde las ubicaciones de la oficina. Aunque la conectividad de red se puede evaluar en toda la organización, las mejoras de diseño de red tendrán que realizarse para ubicaciones de oficina específicas. La información de conectividad de red se proporciona para cada ubicación de oficina una vez que se puedan determinar esas ubicaciones. Existen tres opciones para obtener evaluaciones de red desde las ubicaciones de la oficina:

### <a name="1-enable-windows-location-services"></a>1. Habilitar Windows location services

Para esta opción, debe tener al menos dos equipos en ejecución en cada ubicación de la oficina que admitan los requisitos previos. OneDrive para Windows versión debe estar actualizada e instalada en cada equipo. Para obtener más información sobre OneDrive versiones anteriores, vea [el OneDrive notas de la versión](https://support.office.com/article/onedrive-release-notes-845dcf18-f921-435e-bf28-4e24b95e5fc0). Las medidas de red están planeadas para agregarse a otras Office 365 cliente en un futuro próximo.

Windows El servicio de ubicación debe estar consentido en las máquinas. Para probar esto, ejecute la **Mapas** y localíctese. Se puede habilitar en una sola máquina con **Configuración | Privacidad | Ubicación** en la que debe _habilitarse la opción Permitir que las_ aplicaciones accedan a su ubicación. Windows El consentimiento de los Servicios de ubicación se puede implementar en equipos con MDM o directiva de grupo con la configuración _LetAppsAccessLocation_.

No es necesario agregar ubicaciones en el Centro de administración con este método, ya que se identifican automáticamente en la resolución de la ciudad. No se mostrarán varias ubicaciones de oficina dentro de la misma ciudad al usar Windows Location Services. La información de ubicación se redondea a los 300 metros más cercanos por 300 metros para que no se obtenga acceso a la información de ubicación más precisa.

Las máquinas deben tener Wi-Fi de red en lugar de un cable ethernet. Las máquinas con un cable ethernet no tienen información de ubicación precisa.

Las muestras de medida y las ubicaciones de oficina deben empezar a aparecer 24 horas después de que se hayan cumplido estos requisitos previos.

### <a name="2-add-locations-and-provide-lan-subnet-information"></a>2. Agregar ubicaciones y proporcionar información de subred LAN

Para esta opción, no Windows servicios de ubicación ni Wi-Fi son necesarios. El OneDrive para Windows versión debe estar actualizado e instalado en al menos un equipo en la ubicación.

También debe agregar ubicaciones en la página **Ubicaciones** o importarlas desde un archivo CSV. Las ubicaciones agregadas deben incluir la información de subred DE LAN de office.

Esta opción le permite tener varias oficinas definidas dentro de una ciudad.

Todas las medidas de prueba de los equipos cliente incluyen la información de subred DE LAN, que está correlacionada con los detalles de ubicación de la oficina que ha especificado. Las muestras de medida y las ubicaciones de oficina deben empezar a aparecer 24 horas después de que se hayan cumplido estos requisitos previos.

### <a name="3-manually-gather-test-reports-with-the-microsoft-365-network-connectivity-test-tool"></a>3. Recopilar manualmente informes de prueba con la Microsoft 365 de prueba de conectividad de red

Para esta opción, debe identificar a una persona en cada ubicación. Pídales que busquen la [Microsoft 365](https://connectivity.office.com) de conectividad de red en una máquina Windows en la que tienen permisos administrativos. En el sitio web, deben iniciar sesión en su cuenta Office 365 para la misma organización que desea ver los resultados. A continuación, deben hacer clic **en Ejecutar prueba**. Durante la prueba hay una prueba de conectividad descargada EXE. Deben abrir y ejecutar eso. Una vez completadas las pruebas, el resultado de la prueba se carga en el Centro de administración.

Los informes de prueba se vinculan a una ubicación si se agregaron con información de subred DE LAN, de lo contrario solo se muestran en la ubicación de la ciudad.

Las muestras de medida y las ubicaciones de oficina deben empezar a aparecer entre 2 y 3 minutos después de que se complete un informe de prueba. Para obtener más información, [vea Microsoft 365 prueba de conectividad de red](office-365-network-mac-perf-onboarding-tool.md).

> [!NOTE]
> Al agregar las ubicaciones de oficina Microsoft 365 conectividad de red en el Centro de administración de Microsoft 365, puede proporcionar direcciones IPv4 o IPv6 para las subredes laN. Egress Las direcciones IP deben usar IPv4.

## <a name="how-do-i-use-this-information"></a>¿Cómo se usa esta información?

**Los conocimientos de red,** sus recomendaciones de rendimiento relacionadas y las evaluaciones de red están diseñadas para ayudar a diseñar perímetros de red para las ubicaciones de la oficina. Cada información proporciona detalles sobre las características de rendimiento de un problema de red común específico para cada ubicación geográfica en la que los usuarios tienen acceso a su espacio empresarial. **Las recomendaciones de rendimiento** para cada información de red ofrecen cambios de diseño de arquitectura de red específicos que puede realizar para mejorar la experiencia del usuario relacionada con la Microsoft 365 de red. La evaluación de red muestra cómo afecta la conectividad de red a la experiencia del usuario, lo que permite comparar las diferentes conexiones de red de ubicación de usuario.

**Las evaluaciones de** red destilan un agregado de muchas métricas de rendimiento de red en una instantánea del estado de la red empresarial, representada por un valor de puntos de 0 a 100. Las evaluaciones de red están en el ámbito de todo el inquilino y de cada ubicación geográfica desde la que los usuarios se conectan a su inquilino, lo que proporciona a los administradores de Microsoft 365 una forma fácil de comprender instantáneamente el estado de la red de la empresa y profundizar rápidamente en un informe detallado para cualquier ubicación de oficina global.

Las empresas complejas con varias ubicaciones de oficina y arquitecturas perimetrales de red no triviales pueden beneficiarse de esta información durante su incorporación inicial a Microsoft 365 o para corregir los problemas de rendimiento de red detectados con el crecimiento del uso. Esto normalmente no es necesario para pequeñas empresas que usan Microsoft 365, o cualquier empresa que ya tenga una conectividad de red sencilla y directa. Se espera que las empresas con más de 500 usuarios y varias ubicaciones de oficina sean las que más se beneficien.

>[!IMPORTANT]
>Los conocimientos de red, las recomendaciones de rendimiento y las evaluaciones del Centro de Administración de Microsoft 365 se encuentran actualmente en estado de vista previa y solo están disponibles para los inquilinos Microsoft 365 que se han inscrito en el programa de vista previa de características.

## <a name="enterprise-network-connectivity-challenges"></a>Enterprise de conectividad de red

> [!div class="mx-imgBorder"]
> ![Red de cliente a nube](../media/m365-mac-perf/m365-mac-perf-first-last-mile.png)

Muchas empresas tienen configuraciones perimetrales de red que han aumentado con el tiempo y están diseñadas principalmente para dar cabida al acceso de los empleados a sitios web de Internet, donde la mayoría de los sitios web no se conocen de antemano y no son de confianza. El enfoque prevaleciendo y necesario es evitar ataques de malware y suplantación de identidad desde estos sitios web desconocidos. Esta estrategia de configuración de red, si bien es útil por motivos de seguridad, puede provocar la degradación del rendimiento Microsoft 365 usuario y la experiencia del usuario.

## <a name="how-we-can-solve-these-challenges"></a>Cómo podemos resolver estos desafíos

Las empresas pueden mejorar la experiencia general del usuario y proteger su entorno siguiendo Office 365 [principios](./microsoft-365-network-connectivity-principles.md) de conectividad y usando la característica de conectividad de red Administración de Microsoft 365 Centro de administración. En la mayoría de los casos, seguir estos principios generales tendrá un impacto positivo significativo en la latencia del usuario final, la confiabilidad del servicio y el rendimiento general de Microsoft 365.

A veces se le pide a Microsoft que investigue los problemas de rendimiento de la red con Microsoft 365 para los clientes de grandes empresas, y estos suelen tener una causa raíz relacionada con la infraestructura perimetral de red del cliente. Cuando se encuentra una causa raíz común de un problema perimetral de red de clientes, buscamos identificar medidas de prueba sencillas que lo identifiquen. Una prueba con un umbral de medida que identifique un problema específico es valiosa porque podemos probar la misma medida en cualquier ubicación, saber si esta causa raíz está presente allí y compartirla como información de red con el administrador.

Algunas perspectivas de red simplemente indicarán un problema que necesita más investigación. Una información de red donde tenemos suficientes pruebas para mostrar una acción de corrección específica para corregir la causa raíz se muestra como **una acción recomendada**. Estas recomendaciones, basadas en métricas en directo que revelan valores que se encuentran fuera de un umbral predeterminado, son mucho más valiosas que los consejos de procedimientos recomendados generales, ya que son específicas de su entorno y mostrarán la mejora real una vez que se hayan realizado los cambios recomendados.

## <a name="network-connectivity-overview-in-the-microsoft-365-admin-center"></a>Introducción a la conectividad de red en el Centro Administración de Microsoft 365 red

Microsoft tiene medidas de red existentes de varios Office de escritorio y web que admiten el funcionamiento de Microsoft 365. Estas medidas se usan ahora para proporcionar información sobre el diseño  de arquitectura de red y una evaluación de red que se muestra en la página Conectividad de red del Centro de Administración de Microsoft 365 red.

De forma predeterminada, la información de ubicación aproximada asociada a las medidas de red identifica la ciudad donde se encuentran los dispositivos cliente. La evaluación de red en cada ubicación se muestra con color y el número relativo de usuarios en cada ubicación se representa por el tamaño del círculo.

> [!div class="mx-imgBorder"]
> ![Mapa de información general de red](../media/m365-mac-perf/m365-mac-perf-overview-map.png)

La página de información general también muestra la evaluación de red del cliente como promedio ponderado en todas las ubicaciones de oficina.

> [!div class="mx-imgBorder"]
> ![Evaluación de la red](../media/m365-mac-perf/m365-mac-perf-overview-score.png)

Puede ver una vista de tabla de las ubicaciones donde se pueden filtrar, ordenar y editar en la **pestaña** Ubicaciones. Las ubicaciones con recomendaciones específicas también pueden incluir una posible mejora de latencia estimada. Esto se calcula tomando la latencia mediana de los usuarios de la organización en la ubicación y restando la latencia mediana para todas las organizaciones de la misma ciudad.

> [!div class="mx-imgBorder"]
> ![Ubicaciones de información de red](../media/m365-mac-perf/m365-mac-perf-locations.png)

## <a name="remote-worker-assessment-and-user-connection-metrics"></a>Evaluación de trabajadores remotos y métricas de conexión de usuario

Clasificamos los registros de tráfico de red como usuarios remotos o in situ y mostramos sus porcentajes en la sección métricas de conexión de usuario del panel de información general. Para las ciudades donde tiene usuarios remotos, encontrará la puntuación de evaluación de red remota específica de la ubicación cuando abra la página de esa ubicación. La lista de ubicaciones tendrá ubicaciones de oficina y ciudades de trabajo remotos, que se pueden filtrar y ordenar. Proporcionamos la puntuación de evaluación de trabajadores remotos, con desglose de puntos para Exchange, SharePoint y Teams.

Los conocimientos de redes del usuario principal se agregan e informan a nivel de ciudad y se limitan a ciudades con un mínimo de 5 empleados remotos. No identificamos empleados individuales que trabajan desde casa.

Sin embargo, las ubicaciones se clasifican automáticamente como in situ o remotas, pero tiene la opción de escribir todas las direcciones IP de salida en el sitio manualmente para garantizar una clasificación del 100 %. Si decide seguir esta ruta, tendrá que activar la casilla Introducir todas las direcciones **IP** de salida en el sitio manualmente en el control desplegable Ubicaciones Configuración después de agregar todas las direcciones IP de salida. Cuando esto se haga, todos los registros de tráfico de red de las direcciones IP de salida que haya marcado como in situ siempre se clasificarán como oficinas y todas las demás direcciones IP de salida se clasificarán como remotas.

## <a name="specific-office-location-network-performance-summary-and-insights"></a>Resumen y conocimientos específicos del rendimiento de la red de ubicación de oficina

Al seleccionar una ubicación de oficina, se abre una página de resumen específica de la ubicación que muestra los detalles de la salida de red que se ha identificado a partir de las medidas de esa ubicación de oficina.

> [!div class="mx-imgBorder"]
> ![Detalles de información de red por ubicación](../media/m365-mac-perf/m365-mac-perf-locations-plan-overview.png)

Se muestra un mapa de la red perimetral para los usuarios de la organización en la ubicación con algunos o todos estos elementos:

- **Office:** la ubicación de la oficina de la página que está buscando
- **Perímetro de red:** la ubicación de la dirección IP de origen para las conexiones desde la ubicación de la oficina. Esto depende de la precisión de las bases de datos de ubicación de ip geográfica
- **Exchange de servicio** óptimo: una de las puertas Exchange de servicio recomendadas a las que los usuarios de esta ubicación de oficina deben conectarse
- **Exchange puerta principal sub-óptima:** una puerta frontal de servicio Exchange a la que los usuarios están conectados, pero no se recomienda
- **SharePoint de servicio** óptimo: una de las puertas SharePoint de servicio recomendados a las que los usuarios de esta ubicación de oficina deben conectarse
- **SharePoint puerta principal de** servicio sub-óptimo: una puerta SharePoint de servicio a la que los usuarios están conectados, pero no se recomienda
- **Servidor de resolución recursiva DNS:** la ubicación de una base de datos IP geográfica del solucionador recursivo DNS detectado usado para Exchange Online (si está disponible)
- **Su servidor proxy:** la ubicación de una base de datos IP geográfica del servidor proxy detectado (si está disponible) 

La página de resumen de ubicación de la oficina muestra, además, la evaluación de red, el historial de evaluación de red de la ubicación, una comparación de la evaluación de esta ubicación con otros clientes de la misma ciudad y una lista de información y recomendaciones específicas que puede realizar para mejorar el rendimiento y la confiabilidad de la red.

Las comparaciones entre clientes de la misma ciudad se basan en la expectativa de que todos los clientes tengan el mismo acceso a proveedores de servicios de red, infraestructura de telecomunicaciones y puntos de presencia de red de Microsoft cercanos.

Los nombres de ubicación se pueden personalizar al agregar una nueva ubicación o editar una ubicación existente en el menú desplegable de la ubicación. Esto le proporciona la flexibilidad para personalizar los nombres de ubicación en cualquier momento. Además, al agregar subredes LAN directamente en el menú desplegable de ubicación, se muestra una lista desplegable de subredes DE LAN coincidentes con software entre las que puede seleccionar. Los nombres de circuito para direcciones IP de salida de oficina específicas también se pueden agregar y editar.

La pestaña detalles de la página de ubicación de la oficina muestra los resultados de medida específicos que se usaron para obtener información, recomendaciones y la evaluación de la red. Esto se proporciona para que los ingenieros de red puedan validar las recomendaciones y factores en cualquier restricción o especificación en su entorno. También encontrará el número estimado de usuarios para las muestras recopiladas en esa oficina, así como los trabajadores remotos de esa ciudad.

> [!div class="mx-imgBorder"]
> ![Detalles específicos de la ubicación](../media/m365-mac-perf/m365-mac-perf-locations-plan-details-all.png)


## <a name="sharing-network-assessment-data-with-microsoft"></a>Compartir datos de evaluación de red con Microsoft

De forma predeterminada, las evaluaciones de red para su organización y la información de red se comparten con los empleados de Microsoft. Esto no incluye ningún dato personal de su personal, sino solo las métricas de evaluación de red específicas y los conocimientos de red que se muestran en el Centro de administración para las ubicaciones de la oficina. Tampoco incluye los nombres de ubicación de la oficina ni las direcciones de calle, por lo que tendría que decirles la ciudad y el identificador de soporte técnico de la oficina que desea analizar. Si esto está desactivado, los ingenieros de Microsoft con los que está hablando de la conectividad de red no podrán ver ninguna de esta información. Al habilitar esta configuración, solo se comparten los datos futuros a partir del día después de habilitarlo.

## <a name="csv-import-for-lan-subnet-office-locations"></a>Importar CSV para ubicaciones de oficina de subred LAN

Para la identificación de la oficina de subred LAN, debe agregar cada ubicación por adelantado. En lugar de agregar ubicaciones de oficina individuales en la **pestaña Ubicaciones,** puede importarlas desde un archivo CSV. Es posible que pueda obtener estos datos de otros lugares en los que los ha almacenado, como el Panel de calidad de llamadas o los sitios y servicios de Active Directory

En el archivo CSV, una ubicación de ciudad detectada se muestra en la columna userEntered como en blanco y una ubicación de oficina agregada manualmente se muestra como 1.

1. En la ventana _principal Conectividad a Microsoft 365,_ haga clic en la **pestaña** Ubicaciones.

1. Haga clic en **el botón** Importar justo encima de la lista de ubicaciones. Aparecerá el menú desplegable **Importar** ubicaciones de oficina.

   > [!div class="mx-imgBorder"]
   > ![Mensaje de importación CSV](../media/m365-mac-perf/m365-mac-perf-import.png)

1. Haga clic en el vínculo Descargar ubicaciones de oficina **actuales (.csv)** para exportar la lista de ubicaciones actuales a un archivo CSV y guárdelo en el disco duro local. Esto le proporcionará un CSV con el formato correcto con encabezados de columna a los que puede agregar ubicaciones. Puede dejar las ubicaciones exportadas existentes tal como están; no se duplicarán al importar el CSV actualizado. Si desea cambiar la dirección de una ubicación existente, se actualizará al importar el CSV. No puede cambiar la dirección de una ciudad detectada.

1. Abra el CSV y agregue las ubicaciones rellenando los siguientes campos en una nueva línea para cada ubicación que desee agregar. Deje todos los demás campos en blanco; se omitirán los valores especificados en otros campos.

   1. **userEntered** (obligatorio): debe ser 1 para una nueva ubicación de oficina de subred LAN que se va a agregar
   1. **Nombre** (obligatorio): el nombre de la ubicación de la oficina
   1. **Dirección** (obligatorio): la dirección física de la oficina
   1. **Latitud** (opcional): se rellena a partir Bing búsqueda de mapas de la dirección si está en blanco
   1. **Longitud** (opcional): se rellena a partir de Bing búsqueda de mapas de la dirección si está en blanco
   1. Egress intervalos de direcciones **IP 1-5** (opcional): para cada intervalo, escriba el nombre del circuito seguido de una lista separada por espacios de direcciones CIDR IPv4 o IPv6 válidas. Estos valores se usan para diferenciar varias ubicaciones de oficina donde se usan las mismas direcciones IP de subred LAN. Egress Todos los intervalos de direcciones IP deben tener un tamaño de red /24 y /24 no se incluye en la entrada.
   1. **LanIps** (obligatorio): enumera los intervalos de subred de LAN que se usan en esta ubicación de oficina. Los id. de subred LAN deben tener un tamaño de red CIDR incluido donde el tamaño de red puede estar entre /8 y /29. Varios intervalos de subred de LAN se pueden separar por comas o punto y coma.
   
1. Cuando haya agregado las ubicaciones de la oficina  y guardado  el archivo, haga clic en el botón Examinar situado junto al Upload campo completado y seleccione el archivo CSV guardado.

1. El archivo se validará automáticamente. Si hay errores de validación, verá el mensaje de error: Hay algunos _errores en el archivo de importación. Revise los errores, corrija el archivo de importación y vuelva a intentarlo._ Haga clic en el vínculo **Abrir detalles de error** para obtener una lista de errores de validación de campo específicos.

   > [!div class="mx-imgBorder"]
   > ![Mensaje de error de importación CSV](../media/m365-mac-perf/m365-mac-perf-import-error.png)

1. Si no hay errores en el archivo, verá el mensaje: _el informe está listo. Se encontraron x ubicaciones para agregar y x ubicaciones para actualizar._ Haga clic **en el botón** Importar para cargar el CSV.

   > [!div class="mx-imgBorder"]
   > ![Mensaje listo para importar CSV](../media/m365-mac-perf/m365-mac-perf-import-ready.png)

## <a name="faq"></a>Preguntas más frecuentes

### <a name="what-is-a-microsoft-365-service-front-door"></a>¿Qué es una Microsoft 365 de servicio principal?

La Microsoft 365 principal del servicio es un punto de entrada en la red global de Microsoft donde Office clientes y servicios finalizan su conexión de red. Para una conexión de red óptima a Microsoft 365, se recomienda que la conexión de red finalice en la puerta Microsoft 365 puerta principal.

>[!NOTE]
>Microsoft 365 la puerta principal del servicio no tiene ninguna relación directa con el producto servicio de puerta frontal de Azure disponible en azure marketplace.

### <a name="what-is-an-optimal-microsoft-365-service-front-door"></a>¿Cuál es una puerta Microsoft 365 servicio óptimo?

Una puerta Microsoft 365 servicio óptimo es la más cercana a la salida de la red, generalmente en su ciudad o área metropolitana. Use la Microsoft 365 de prueba de conectividad (versión [preliminar)](office-365-network-mac-perf-onboarding-tool.md) para determinar la ubicación de la puerta principal del servicio Microsoft 365 servicio en uso y la puerta principal de servicio óptima. Si la herramienta determina que la puerta principal en uso es óptima, se está conectando de forma óptima a la red global de Microsoft.

### <a name="what-is-an-internet-egress-location"></a>¿Qué es una ubicación de salida de Internet?

La ubicación de salida de Internet es la ubicación donde el tráfico de red sale de la red empresarial y se conecta a Internet. Esto también se identifica como la ubicación donde tiene un dispositivo de traducción de direcciones de red (NAT) y, por lo general, donde se conecta con un proveedor de servicios de Internet (ISP). Si ve una larga distancia entre la ubicación y la ubicación de salida de Internet, esto puede indicar un backhaul wan significativo.

### <a name="what-license-is-needed-for-this-capability"></a>¿Qué licencia se necesita para esta funcionalidad?

Necesita una licencia que proporciona acceso a la Centro de administración de Microsoft 365.

## <a name="related-topics"></a>Temas relacionados

[Microsoft 365 de red (versión preliminar)](office-365-network-mac-perf-insights.md)

[Microsoft 365 de red (versión preliminar)](office-365-network-mac-perf-score.md)

[Microsoft 365 de prueba de conectividad (versión preliminar)](office-365-network-mac-perf-onboarding-tool.md)

[Microsoft 365 Servicios de ubicación de conectividad de red (versión preliminar)](office-365-network-mac-location-services.md)
