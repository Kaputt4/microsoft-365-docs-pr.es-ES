---
title: Novedades de Microsoft Defender para punto de conexión
description: Vea qué características están disponibles con carácter general (GA) en la versión más reciente de Microsoft Defender para punto de conexión, así como las características de seguridad en Windows 10 y Windows Server.
keywords: novedades de Microsoft Defender para punto de conexión, ga, disponibilidad general, funcionalidades, disponibles, nuevas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 08/25/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9d7e89a55a70cef1f8957792346ca09f05416439
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497146"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint"></a>Novedades de Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Las siguientes características están en versión preliminar o están disponibles con carácter general en la versión más reciente de Microsoft Defender para punto de conexión.

Para obtener más información sobre las características en versión preliminar, consulte [Características en versión preliminar](preview.md).

> [!TIP]
> Fuente RSS: para recibir notificaciones cuando esta página se actualice, copie y pegue la dirección URL siguiente en el lector de fuentes: 
>
> ```https
> https://docs.microsoft.com/api/search/rss?search=%22features+are+generally+available+%28GA%29+in+the+latest+release+of+Microsoft+Defender+for+Endpoint%22&locale=en-us&facet=
> ```

Para obtener más información sobre las novedades de otros productos de seguridad de Microsoft Defender, consulte:

- [Novedades de Microsoft 365 Defender](../defender/whats-new.md)
- [Novedades de Microsoft Defender para Office 365](../office-365-security/whats-new-in-defender-for-office-365.md)
- [Novedades de Microsoft Defender for Identity](/defender-for-identity/whats-new)
- [Novedades de Microsoft Defender for Cloud Apps](/cloud-app-security/release-notes)

Para obtener más información sobre Microsoft Defender para punto de conexión en otros sistemas operativos:

- [Novedades de Defender para punto de conexión en macOS](mac-whatsnew.md)
- [Novedades de Defender para punto de conexión en iOS](ios-whatsnew.md)
- [Novedades de Defender para punto de conexión en Linux](linux-whatsnew.md)

## <a name="august-2022"></a>Agosto de 2022

- [Estado de mantenimiento del dispositivo](investigate-machines.md#device-health-status)<br>La tarjeta estado de mantenimiento del dispositivo muestra un informe de estado resumido para el dispositivo específico.
- [Informes de estado del dispositivo (versión preliminar)](/microsoft-365/security/defender-endpoint/machine-reports)<br> El informe de estado de dispositivos proporciona información de alto nivel sobre los dispositivos de la organización. El informe incluye información de tendencias que muestra el estado de mantenimiento del sensor, el estado del antivirus, las plataformas del sistema operativo y las versiones de Windows 10.
- [La protección contra alteraciones en macOS ya está disponible con carácter general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/tamper-protection-on-macos-is-now-generally-available/ba-p/3595422)<br> Esta característica se publicará con el modo de auditoría habilitado de forma predeterminada y puede decidir si quiere aplicar (bloquear) o desactivar la funcionalidad. Más adelante este año, ofreceremos un mecanismo de implementación gradual que cambiará automáticamente los puntos de conexión al modo de bloqueo; tenga en cuenta que esto solo se aplicará si no ha elegido específicamente habilitar (modo de bloque) o deshabilitar la funcionalidad.
- [Protección de red y protección web para macOS y Linux ya está en versión preliminar pública.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-protection-and-web-protection-for-macos-and-linux-is-now/ba-p/3601576)<br>Protección de red ayuda a reducir la superficie expuesta a ataques de los dispositivos a partir de eventos basados en Internet. Impide que los empleados usen cualquier aplicación para acceder a dominios peligrosos que pueden hospedar estafas de phishing, vulnerabilidades de seguridad y otro contenido malintencionado en Internet. Es la base sobre la que se basa nuestra protección web para Microsoft Defender para punto de conexión. Estas funcionalidades incluyen la protección contra amenazas web, el filtrado de contenido web y los indicadores ip/url personalizados. La protección web le permite proteger los dispositivos frente a amenazas web y ayuda a regular el contenido no deseado.
- [Incorporación mejorada de Microsoft Defender para punto de conexión (MDE) para Windows Server 2012 R2 y Windows Server 2016](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2207#improved-microsoft-defender-for-endpoint-mde-onboarding-for-windows-server-2012-r2-and-windows-server-2016)<br>Configuration Manager versión 2207 ahora admite la implementación automática de Microsoft Defender para punto de conexión modernas y unificadas para Windows Server 2012 R2 & 2016. los dispositivos Windows Server 2012 y 2016 destinados a Microsoft Defender para punto de conexión directiva de incorporación usarán el agente unificado frente a la solución existente basada en Microsoft Monitoring Agent, si se configura a través de la configuración de cliente.


## <a name="july-2022"></a>Julio de 2022
- [Adición de dispositivos de controlador de dominio: mejora del laboratorio de evaluación](evaluation-lab.md#add-a-domain-controller)<br>Ahora disponible con carácter general: agregue un controlador de dominio para ejecutar escenarios complejos, como el movimiento lateral y los ataques de varias fases en varios dispositivos.
- [Anuncio de mejoras de página de archivos en Microsoft Defender para punto de conexión](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-file-page-enhancements-in-microsoft-defender-for/ba-p/3584004)<br>¿Alguna vez ha investigado los archivos en Microsoft Defender para punto de conexión? Ahora lo facilitamos aún más con nuestro anuncio reciente de mejoras en la página Archivo y en el panel lateral. Los usuarios ahora pueden simplificar los procesos al tener una experiencia de navegación más eficaz que hospede toda esta información en un solo lugar.
- [Presentación de la nueva experiencia de supresión de alertas](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/introducing-the-new-alert-suppression-experience/ba-p/3562719)<br>Nos complace compartir la nueva y avanzada experiencia de supresión de alertas ahora está disponible con carácter general. La nueva experiencia proporciona una granularidad y un control más estrictos, lo que permite a los usuarios ajustar Microsoft Defender para punto de conexión alertas.
- [Impedir que los dispositivos no administrados en peligro se muevan lateralmente en la organización con "Contener"](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/prevent-compromised-unmanaged-devices-from-moving-laterally-in/ba-p/3482134)<br>A partir de hoy, cuando se sospeche que un dispositivo que no está inscrito en Microsoft Defender para punto de conexión está en peligro, como analista de SOC, podrá "contenerlo". Como resultado, cualquier dispositivo inscrito en Microsoft Defender para punto de conexión bloqueará ahora cualquier comunicación entrante o saliente con el dispositivo sospechoso.
- [La compatibilidad con dispositivos móviles ya está disponible para los clientes del gobierno de EE. UU. que usan Defender para punto de conexión.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/mobile-device-support-is-now-available-for-us-government/ba-p/3472590)<br>Microsoft Defender para punto de conexión para clientes del Gobierno de EE. UU. está integrado en el entorno de Azure US Government y usa las mismas tecnologías subyacentes que Defender en Azure Commercial. Esta oferta está disponible para los clientes de GCC, GCC High y DoD y amplía aún más la disponibilidad de nuestra plataforma desde Windows, MacOS y Linux hasta dispositivos Android e iOS.


## <a name="june-2022"></a>Junio de 2022
- [El plan 2 de Defender para servidores ahora se integra con la solución unificada MDE](https://techcommunity.microsoft.com/t5/microsoft-defender-for-cloud/defender-for-servers-plan-2-now-integrates-with-mde-unified/ba-p/3527534)<br>Ahora puede empezar a implementar la solución moderna y unificada para Windows Server 2012 R2 y 2016 en los servidores cubiertos por el plan 2 de Defender para servidores con un solo botón.
- [Mobile Network Protection en Microsoft Defender para punto de conexión en Android & iOS ahora en versión preliminar pública](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/mobile-network-protection-in-microsoft-defender-for-endpoint-on/ba-p/3559121)<br>Microsoft ofrece una característica de protección de red móvil en Defender para punto de conexión que ayuda a las organizaciones a identificar, evaluar y corregir las debilidades de los puntos de conexión con la ayuda de una sólida inteligencia sobre amenazas. Nos complace anunciar que los usuarios ahora pueden beneficiarse de esta nueva característica en plataformas Android e iOS con Microsoft Defender para punto de conexión.

## <a name="may-2022"></a>Mayo de 2022
- [Protección contra alteraciones para macOS (versión preliminar)](tamperprotection-macos.md)<br>La protección contra alteraciones ayuda a evitar la eliminación no autorizada de Microsoft Defender para punto de conexión en macOS.
- [Agregar dispositivos de controlador de dominio: mejora del laboratorio de evaluación (versión preliminar)](evaluation-lab.md#add-a-domain-controller)<br>Agregue un controlador de dominio para ejecutar escenarios complejos, como movimiento lateral y ataques de varias fases en varios dispositivos.
- [Modo de solución de problemas de Microsoft Defender para punto de conexión ahora disponible con carácter general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/troubleshooting-mode-for-microsoft-defender-for-endpoint-now/ba-p/3347344)<br>Introducción al modo de solución de problemas, una manera única, innovadora y segura de investigar y ajustar las configuraciones en los dispositivos. Este modo permitirá al administrador local del dispositivo invalidar las configuraciones de directiva de seguridad del Antivirus de Microsoft Defender en el dispositivo, incluida la protección contra alteraciones. 
- [Anuncio de la versión preliminar pública del perfil personal de Defender para punto de conexión para Android Enterprise](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-defender-for-endpoint-personal/ba-p/3370979)<br>Nos complace anunciar que los usuarios que deseen inscribir sus propios dispositivos en el programa BYOD de su lugar de trabajo ahora pueden beneficiarse de la protección proporcionada por Microsoft Defender para punto de conexión también en su perfil personal.
- [La administración de la configuración de seguridad en Microsoft Defender para punto de conexión ya está disponible con carácter general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/security-settings-management-in-microsoft-defender-for-endpoint/ba-p/3356970)<br>A finales de 2021, anunciamos que Microsoft Defender para punto de conexión expandió sus funcionalidades de administración de configuración. Esta versión facultó a los equipos de seguridad para configurar los dispositivos con sus opciones de seguridad deseadas sin necesidad de implementar e implementar herramientas o infraestructura adicionales.  Gracias a microsoft Endpoint Manager, las organizaciones han podido administrar las directivas de antivirus (AV), detección y respuesta de puntos de conexión (EDR) y firewall (FW) desde una sola vista para todos los dispositivos inscritos. En la actualidad, anunciamos que esta funcionalidad ya está disponible con carácter general para el cliente de Windows y Windows Server, lo que admite Windows 10, Windows 11 y Windows Server 2012 R2 o posterior.

## <a name="april-2022"></a>Abril de 2022
- [Incorporación actualizada y paridad de características para Windows Server 2012 R2 y Windows Server 2016)](configure-server-endpoints.md)<br/> El nuevo paquete de solución unificada ya está disponible con carácter general y facilita la incorporación de servidores mediante la eliminación de dependencias y los pasos de instalación. Además, este paquete de solución unificada incluye muchas mejoras de características nuevas.
- [Integración con Tunnel para iOS](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/what-s-new-in-microsoft-endpoint-manager-2204-april-edition/ba-p/3297995). Microsoft Defender para punto de conexión en iOS ahora se puede integrar con Microsoft Tunnel, una solución de puerta de enlace de VPN para habilitar la seguridad y la conectividad en una sola aplicación. Esta característica solo estaba disponible anteriormente en Android.
- [Protección antimalware mejorada en Microsoft Defender para punto de conexión Android](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/enhanced-antimalware-protection-in-microsoft-defender-for/ba-p/3290320)<br>Nos complace compartir las principales actualizaciones de las funcionalidades de protección contra malware de Microsoft Defender para punto de conexión en Android. Estas nuevas funcionalidades forman un componente importante de la protección de próxima generación en Microsoft Defender para punto de conexión. Esta protección reúne el aprendizaje automático, el análisis de macrodatos, la investigación de amenazas en profundidad y la infraestructura en la nube de Microsoft para proteger los dispositivos Android (o puntos de conexión) de su organización.
- [Funcionalidades mejoradas del motor antimalware para Linux y macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/enhanced-antimalware-engine-capabilities-for-linux-and-macos/ba-p/3292003)<br>Estamos anunciando una actualización significativa a nuestra protección de próxima generación en Linux y macOS con un nuevo motor mejorado. El motor antimalware antivirus de Microsoft Defender es un componente clave de la protección de próxima generación. Esta protección proporciona aprendizaje automático, análisis de macrodatos, investigación detallada de amenazas y la infraestructura en la nube de Microsoft para proteger los dispositivos (o puntos de conexión) de su organización. Las principales ventajas de esta actualización principal incluyen mejoras de rendimiento y prevención, así como la adición de compatibilidad con indicadores de archivos personalizados en macOS y Linux.
- [Nueva funcionalidad de informes para el control de dispositivos y el firewall de Windows Defender](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/new-reporting-functionality-for-device-control-and-windows/ba-p/3290601)<br>Nos complace anunciar las nuevas funcionalidades de informes de punto de conexión en el portal de Microsoft 365 Defender. Este trabajo reúne nuevos informes de punto de conexión para que pueda ver lo que sucede en su entorno con solo un par de clics. Nuestros informes están diseñados para proporcionar información sobre el comportamiento y la actividad del dispositivo, a la vez que le permiten aprovechar al máximo las experiencias integradas en Microsoft 365 Defender portal, como la escala de tiempo del dispositivo y la búsqueda avanzada.
- [Envíos unificados en Microsoft 365 Defender ahora disponible con carácter general.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/unified-submissions-in-microsoft-365-defender-now-generally/ba-p/3270770)<br>Tu equipo de seguridad ahora tiene una "tienda integral" para enviar correos electrónicos, direcciones URL, datos adjuntos de correo electrónico y archivos en una experiencia de envío sencilla. Para simplificar el proceso de envío, nos complace anunciar una nueva experiencia unificada de envíos en el portal de Microsoft 365 Defender (https://security.microsoft.com). Con envíos unificados, puede enviar archivos a Microsoft 365 Defender para su revisión desde el portal. También agregamos la capacidad de enviar un archivo directamente desde una página de alerta de Microsoft Defender para punto de conexión.  
- [Anuncio de compatibilidad y funcionalidad ampliadas para las API de live response](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-expanded-support-and-functionality-for-live-response/ba-p/3178432)<br>Nos complace compartir que seguimos ampliando el soporte de las API existentes en todas nuestras plataformas admitidas en Microsoft Defender para punto de conexión, además de anunciar otras nuevas que ayudarán a simplificar y aumentar la automatización y orquestación de respuestas de la organización.

## <a name="february-2022"></a>Febrero de 2022

- [El complemento Splunk para Microsoft Security ya está disponible](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/the-splunk-add-on-for-microsoft-security-is-now-available/ba-p/3171272)<br>Nos complace compartir que el complemento Splunk compatible con Splunk para Microsoft Security ya está disponible. Este complemento se basa en el complemento de Microsoft 365 Defender para Splunk 1.3.0 y asigna las propiedades de la API de alertas de Microsoft Defender para punto de conexión o las propiedades de la API Microsoft 365 Defender Incidents a Common Information Model (CIM) de Splunk.
- [Desuso de la API SIEM heredada: pospuesto](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/deprecating-the-legacy-siem-api-postponed/ba-p/3139643)<br>Anteriormente anunciamos que la API REST siem estaría en desuso el 1/4/2022. Hemos escuchado los comentarios de los clientes y el desuso de la API se ha pospuesto por ahora, se esperan más detalles en el tercer trimestre de 2022. Esperamos compartir detalles interesantes sobre las API de Microsoft 365 Defender en Microsoft Graph en el tercer trimestre de 2022.

## <a name="january-2022"></a>Enero de 2022

- [La administración de vulnerabilidades para Android e iOS ya está disponible con carácter general](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663)<br>Con esta nueva cobertura multiplataforma, las funcionalidades de Administración de amenazas y vulnerabilidades ahora admiten todas las plataformas de dispositivos principales de toda la organización: estaciones de trabajo, servidores y dispositivos móviles. 
- [Microsoft Defender para punto de conexión plan 1 ahora incluido en licencias M365 E3/A3](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-for-endpoint-plan-1-now-included-in-m365-e3/ba-p/3060639)<br>A partir del 14 de enero, Microsoft Defender para punto de conexión Plan 1 (P1) se incluirá automáticamente en las licencias de Microsoft 365 E3/A3.
- [Incorporación sin interacción de Microsoft Defender para punto de conexión en iOS ahora en versión preliminar pública](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/zero-touch-onboarding-of-microsoft-defender-for-endpoint-on-ios/ba-p/3038045)<br>Con esta nueva funcionalidad, las empresas ahora pueden implementar Microsoft Defender para punto de conexión en dispositivos iOS inscritos con Microsoft Endpoint Manager automáticamente, sin necesidad de que los usuarios finales interactúen con la aplicación. Esto facilita las fricciones de implementación y reduce significativamente el tiempo necesario para implementar la aplicación en todos los dispositivos a medida que Microsoft Defender para punto de conexión se activa silenciosamente en los dispositivos de destino y comienza a proteger el patrimonio de iOS.

## <a name="december-2021"></a>Diciembre de 2021

- [Administración de vulnerabilidades de Microsoft Defender puede ayudar a identificar vulnerabilidades de Log4j en aplicaciones y componentes](https://www.microsoft.com/security/blog/2021/12/11/guidance-for-preventing-detecting-and-hunting-for-cve-2021-44228-log4j-2-exploitation/#TVM)<br>La administración de amenazas y vulnerabilidades identifica automáticamente y sin problemas los dispositivos afectados por las vulnerabilidades de Log4j y el riesgo asociado en el entorno y reduce significativamente el tiempo de mitigación. Microsoft sigue iterando sobre estas características en función de la información más reciente del panorama de amenazas.
- Detección de dispositivos IoT (versión preliminar): la [detección](device-discovery.md) de dispositivos ahora tiene la capacidad de ayudarle a encontrar dispositivos IoT no administrados conectados a la red corporativa. Esto le proporciona una única vista unificada del inventario de IoT junto con el resto de los dispositivos de TI (estaciones de trabajo, servidores y dispositivos móviles).
- [Integración de Microsoft Defender para IoT (versión preliminar):](enable-microsoft-defender-for-iot-integration.md) esta integración mejora las funcionalidades de detección de dispositivos con las funcionalidades de supervisión sin agente proporcionadas por Microsoft Defender para IoT. Esto proporciona una mayor visibilidad para ayudar a localizar, identificar y proteger los dispositivos IoT en la red.

## <a name="november-2021"></a>Noviembre de 2021

- [Administración de configuración de seguridad](security-config-management.md) <br/> Una funcionalidad para que los dispositivos que no están administrados por un Endpoint Manager de Microsoft, ya sea Microsoft Intune o microsoft endpoint Configuration Manager, reciban configuraciones de seguridad para Microsoft Defender directamente desde Endpoint Manager.
- [Laboratorio de evaluación: compatibilidad del sistema operativo expandido & simulaciones de atomic Red Team](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/evaluation-lab-expanded-os-support-amp-atomic-red-team/ba-p/2993927)<br>El laboratorio de evaluación ahora admite la adición de dispositivos Windows 11, Windows Server 2016 y Linux. Además, también nos gustaría anunciar una nueva asociación con la biblioteca de simulación de código abierto de Red Canary, Atomic Red Team!
- [Anuncio de la versión preliminar pública de Microsoft Defender para punto de conexión Mobile: protección contra alteraciones](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-microsoft-defender-for-endpoint/ba-p/2971038)<br>Marque un dispositivo no compatible después de 7 días de inactividad en la aplicación móvil Microsoft Defender para punto de conexión.
- [Aumente la protección de su patrimonio de Linux con la supervisión del comportamiento, la cobertura de distribución extendida y mucho más.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/boost-protection-of-your-linux-estate-with-behavior-monitoring/ba-p/2909320)<br>Estamos encantados de compartir las últimas noticias sobre Microsoft Defender para punto de conexión en protección de última generación de Linux, detección y respuesta de puntos de conexión (EDR), Administración de amenazas y vulnerabilidades (TVM). La protección de Microsoft para su patrimonio de Linux está obteniendo un aumento impresionante en todo el espectro del conjunto de seguridad. Con Microsoft Defender para punto de conexión recientes en la integración de Linux en Azure Security Center, las ventajas de nuestros EDR y TVM de Linux ahora se extienden a los clientes de Azure Defender.

## <a name="october-2021"></a>Octubre de 2021

- [Incorporación actualizada y paridad de características para Windows Server 2012 R2 y Windows Server 2016 (versión preliminar)](configure-server-endpoints.md)<br/> El nuevo paquete de solución unificada facilita la incorporación de servidores mediante la eliminación de dependencias y los pasos de instalación. Además, este paquete de solución unificada incluye muchas mejoras de características nuevas.
- Windows 11 compatibilidad agregada a Microsoft Defender para punto de conexión y Microsoft 365 Defender.

## <a name="september-2021"></a>Septiembre de 2021

- [Filtrado de contenido web](web-content-filtering.md) <br/>Como parte de las funcionalidades de protección web en Microsoft Defender para punto de conexión, el filtrado de contenido web permite al equipo de seguridad de su organización realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido. Las categorías incluyen contenido para adultos, alto ancho de banda, responsabilidad legal, ocio y sin categoría. Aunque muchos sitios web que entran en una o varias de estas categorías podrían no ser malintencionados, podrían ser problemáticos debido a las regulaciones de cumplimiento, el uso de ancho de banda u otros problemas. [Obtenga más información sobre el filtrado de contenido web](web-content-filtering.md).

## <a name="august-2021"></a>Agosto de 2021

- (versión preliminar) [plan 1 de Microsoft Defender para punto de conexión ](defender-endpoint-plan-1.md) <br/>Defender for Endpoint Plan 1 (versión preliminar) es una solución de protección de puntos de conexión que incluye protección de última generación, reducción de la superficie expuesta a ataques, administración centralizada e informes y API. El plan 1 de Defender para punto de conexión (versión preliminar) es una nueva oferta para los clientes que quieren probar nuestras funcionalidades de Endpoint Protection, tienen Microsoft 365 E3 y aún no tienen Microsoft 365 E5. 

   Para obtener más información, consulte [Microsoft Defender para punto de conexión Plan 1 (versión preliminar).](defender-endpoint-plan-1.md) Las funcionalidades existentes de [Defender para punto de conexión](microsoft-defender-endpoint.md) se conocerán como Defender para el plan de punto de conexión 2. 
- (versión preliminar) [Filtrado de contenido web](web-content-filtering.md)<br>  El filtrado de contenido web forma parte de las funcionalidades de protección web de Microsoft Defender para punto de conexión. Permite a su organización realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido. Muchos de estos sitios web, aunque no son malintencionados, pueden ser problemáticos debido a las regulaciones de cumplimiento, el uso del ancho de banda u otros problemas.

## <a name="july-2021"></a>Julio de 2021

- (versión preliminar) [Informe de cumplimiento y estado del dispositivo](machine-reports.md) <br>  El informe de estado y cumplimiento del dispositivo proporciona información de alto nivel sobre los dispositivos de su organización.

## <a name="june-2021"></a>Junio de 2021

- [Evaluación de vulnerabilidades de software de exportación delta](get-assessment-methods-properties.md#31-methods) Api <br> Una adición a las [evaluaciones de exportación de vulnerabilidades y la recopilación de API de configuraciones seguras](get-assessment-methods-properties.md) . <br> A diferencia de la evaluación completa de vulnerabilidades de software (respuesta JSON) (que se usa para obtener una instantánea completa de la evaluación de vulnerabilidades de software de su organización por dispositivo), la llamada a la API de exportación delta se usa para capturar solo los cambios que se han producido entre una fecha seleccionada y la fecha actual (la llamada API "delta"). En lugar de obtener una exportación completa con una gran cantidad de datos cada vez, solo obtendrá información específica sobre las vulnerabilidades nuevas, fijas y actualizadas. La llamada a la API de exportación delta también se puede usar para calcular KPI diferentes, como "cuántas vulnerabilidades se corrigieron" o "cuántas nuevas vulnerabilidades se agregaron a una organización".
- [Exportación de evaluaciones de vulnerabilidades y configuraciones seguras](get-assessment-methods-properties.md) Api <br> Agrega una colección de API que extraen datos de Administración de vulnerabilidades de Defender por dispositivo. Hay diferentes llamadas API para obtener diferentes tipos de datos: evaluación de configuración segura, evaluación del inventario de software y evaluación de vulnerabilidades de software. Cada llamada API contiene los datos necesarios para los dispositivos de la organización.
- [Actividad de corrección](get-remediation-methods-properties.md) Api <br> Agrega una colección de API con respuestas que contienen actividades de corrección de Defender Vulnerability Management que se han creado en el inquilino. Los tipos de información de respuesta incluyen una actividad de corrección por identificador, todas las actividades de corrección y los dispositivos expuestos de una actividad de corrección.
- [Detección de dispositivo](device-discovery.md) <br> Ayuda a encontrar dispositivos no administrados conectados a la red corporativa sin necesidad de dispositivos adicionales ni cambios en los procesos engorrosos. Con los dispositivos incorporados, puede encontrar dispositivos no administrados en la red y evaluar vulnerabilidades y riesgos. A continuación, puede incorporar dispositivos detectados para reducir los riesgos asociados a tener puntos de conexión no administrados en la red.

   > [!IMPORTANT]
   > La detección estándar será el modo predeterminado para todos los clientes a partir del 19 de julio de 2021. Puede optar por conservar el modo básico a través de la página de configuración.

- [Las definiciones de grupos de](/microsoft-365/security/defender-endpoint/machine-groups) dispositivos ahora pueden incluir varios valores para cada condición. Puede establecer varias etiquetas, nombres de dispositivo y dominios en la definición de un único grupo de dispositivos.
- [Compatibilidad con la administración de aplicaciones móviles](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> Esta mejora permite Microsoft Defender para punto de conexión proteger los datos de una organización dentro de una aplicación administrada cuando se usa Intune para administrar aplicaciones móviles. Para obtener más información sobre la administración de aplicaciones móviles, consulte [esta documentación](/mem/intune/apps/mam-faq).
- [Integración de VPN de Microsoft Tunnel](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-new-capabilities-on-android-and-ios/ba-p/2442730) <br> Las funcionalidades de VPN de Microsoft Tunnel ahora se integran con Microsoft Defender para punto de conexión aplicación para Android. Esta unificación permite a las organizaciones ofrecer una experiencia de usuario final simplificada con una aplicación de seguridad, que ofrece tanto la defensa contra amenazas móviles como la capacidad de acceder a los recursos locales desde su dispositivo móvil, mientras que los equipos de seguridad y TI pueden mantener las mismas experiencias de administración con las que están familiarizados.
- [Detección de jailbreak en iOS](/microsoft-365/security/defender-endpoint/ios-configure-features#conditional-access-with-defender-for-endpoint-on-ios) <br> La funcionalidad de detección de jailbreak en Microsoft Defender para punto de conexión en iOS ya está disponible con carácter general. Esto se suma a la protección contra suplantación de identidad (phishing) que ya existe.  Para obtener más información, consulte [Configuración de la directiva de acceso condicional en función de las señales de riesgo del dispositivo](/microsoft-365/security/defender-endpoint/ios-configure-features).


## <a name="march-2021"></a>Marzo 2021
- [Administración de la protección contra alteraciones de la organización mediante Microsoft 365 Defender portal](manage-tamper-protection-microsoft-365-defender.md) <br> Puede administrar la configuración de protección contra alteraciones en Windows 10, Windows Server 2016, Windows Server 2019 y Windows Server 2022 mediante un método denominado *asociación de inquilinos*.


## <a name="january-2021"></a>Enero de 2021

- [Azure Virtual Desktop](https://azure.microsoft.com/services/virtual-desktop/) <br> Microsoft Defender para punto de conexión ahora agrega compatibilidad con Azure Virtual Desktop.
