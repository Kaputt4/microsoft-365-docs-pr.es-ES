---
title: Ver y editar la configuración de seguridad en Microsoft Defender para Empresas
description: Visualización y edición de directivas de seguridad y configuración en Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 757545231a7bbe544bfbacf082fc03d88fb2df2f
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "65174167"
---
# <a name="view-and-edit-your-security-policies-and-settings-in-microsoft-defender-for-business"></a>Ver y editar las directivas de seguridad y la configuración en Microsoft Defender para Empresas

Después de incorporar los dispositivos de la empresa a Microsoft Defender para Empresas, el siguiente paso es revisar las directivas de seguridad. Si es necesario, puede editar las directivas de seguridad y la configuración. 

> [!TIP]
> Defender for Business incluye directivas de seguridad preconfiguradas que usan la configuración recomendada. Sin embargo, puede editar la configuración para satisfacer sus necesidades empresariales.

Las directivas de seguridad que se van a revisar y configurar incluyen:

- **[Directivas de protección de última generación](#view-or-edit-your-next-generation-protection-policies)**, que determinan la protección antivirus y antimalware para los dispositivos de la empresa
- **[Protección y reglas de firewall](#view-or-edit-your-firewall-policies-and-custom-rules)**, que determinan qué tráfico de red puede fluir hacia o desde los dispositivos de la empresa
- **[Filtrado de contenido web](#set-up-web-content-filtering)**, que impide que las personas visiten determinados sitios web (URL) en función de categorías, como contenido para adultos o responsabilidad legal.
- **[Características avanzadas](#review-settings-for-advanced-features)**, como investigación y respuesta automatizadas, y detección y respuesta de puntos de conexión (EDR) en modo de bloque.

En Defender para empresas, las directivas de seguridad se aplican a los dispositivos a través de [grupos de dispositivos](mdb-create-edit-device-groups.md#what-is-a-device-group). 

Además de las directivas de seguridad, puede [ver y editar la configuración](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal), como la zona horaria que se va a usar en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) y si se van a recibir características en versión preliminar a medida que estén disponibles.

Use este artículo como guía para administrar las directivas de seguridad y la configuración.

## <a name="what-to-do"></a>Qué hacer

1. [Elija dónde administrar las directivas de seguridad y los dispositivos](#choose-where-to-manage-security-policies-and-devices).
2. [Revise las directivas de protección de próxima generación](#view-or-edit-your-next-generation-protection-policies).
3. [Revise las directivas de firewall y las reglas personalizadas](#view-or-edit-your-firewall-policies-and-custom-rules).
4. [Configurar el filtrado de contenido web](#set-up-web-content-filtering).
5. [Revise la configuración de las características avanzadas](#review-settings-for-advanced-features).
6. [Vea otras opciones de configuración en el portal de Microsoft 365 Defender](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal). 
7. [Continúe con los pasos siguientes](#next-steps).

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="choose-where-to-manage-security-policies-and-devices"></a>Elección de dónde administrar directivas y dispositivos de seguridad

Defender for Business ofrece un [proceso de configuración simplificado](mdb-simplified-configuration.md) que ayuda a simplificar el proceso de configuración y configuración. Si selecciona el proceso de configuración simplificado, puede ver y administrar las directivas de seguridad en el portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)). Sin embargo, no se limita a esta opción. Si ha estado usando Microsoft Intune, puede seguir usando el centro de administración de Microsoft Endpoint Manager.

La tabla siguiente puede ayudarle a elegir dónde administrar las directivas de seguridad y los dispositivos. <br/><br/>

| Opción | Descripción |
|:---|:---|
| **Uso del portal de Microsoft 365 Defender** (*recomendado*) | El portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) puede ser tu tienda integral para administrar los dispositivos, las directivas de seguridad y la configuración de seguridad de tu empresa. Puede acceder a las directivas de seguridad y la configuración, usar el [panel de administración de vulnerabilidades de Threat &](mdb-view-tvm-dashboard.md) y [ver y administrar incidentes](mdb-view-manage-incidents.md) en un solo lugar. <br/><br/>Si usa Intune, los dispositivos que incorpore a Defender for Business y las directivas de seguridad estarán visibles en el centro de administración de Endpoint Manager. Para más información, consulte los artículos siguientes:<br/>- [Configuración predeterminada de Defender for Business y Microsoft Intune](mdb-next-gen-configuration-settings.md#defender-for-business-default-settings-and-microsoft-intune) <br/>- [Firewall en Microsoft Defender para Empresas](mdb-firewall.md)   |
| **Uso del centro de administración de Microsoft Endpoint Manager** | Si su empresa ya usa Intune para administrar directivas de seguridad, puede seguir usando el centro de administración de Endpoint Manager para administrar los dispositivos y las directivas de seguridad. Para más información, consulte [Administración de la seguridad de dispositivos con directivas de seguridad de punto de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). <br/><br/>Si decide cambiar al [proceso de configuración simplificado en Defender for Business](mdb-simplified-configuration.md), se le pedirá que elimine las directivas de seguridad existentes en Intune para evitar [conflictos de directivas](mdb-troubleshooting.yml) más adelante. |

> [!IMPORTANT]
> Si está administrando directivas de seguridad en el portal de Microsoft 365 Defender, puede *ver* esas directivas en el centro de administración de Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), que aparece como **directivas antivirus** o **de firewall**. Cuando vea las directivas de firewall en el centro de administración de Endpoint Manager, verá dos directivas en la lista: una directiva para la protección del firewall y otra para reglas personalizadas.

## <a name="view-or-edit-your-next-generation-protection-policies"></a>Visualización o edición de las directivas de protección de próxima generación

En función de si usa el portal de Microsoft 365 Defender o el centro de administración de Microsoft Endpoint Manager para administrar las directivas de protección de próxima generación, use uno de los procedimientos de la tabla siguiente:

| Portal | Procedure |
|:---|:---|
| portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) | 1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. <br/><br/>2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo y tipo de directiva.<br/><br/>3. Seleccione una pestaña del sistema operativo (por ejemplo **, Windows clientes**).<br/><br/>4. Expanda **Protección de próxima generación** para ver la lista de directivas.<br/><br/>5. Seleccione una directiva para ver más detalles sobre la directiva. Para realizar cambios o obtener más información sobre la configuración de directivas, consulte los artículos siguientes: <br/>- [Visualización o edición de directivas de dispositivo](mdb-view-edit-policies.md)<br/>- [Descripción de la configuración de próxima generación](mdb-next-gen-configuration-settings.md)  |
| Microsoft Endpoint Manager centro de administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. Vaya a [https://endpoint.microsoft.com](https://endpoint.microsoft.com) e inicie sesión. Ahora está en el centro de administración de Endpoint Manager.<br/><br/>2. Seleccione **Seguridad del punto de conexión**.<br/><br/>3. Seleccione **Antivirus** para ver las directivas en esa categoría. <br/><br/>Para obtener ayuda para administrar la configuración de seguridad en Intune, comience con [Administrar la seguridad de los puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security). |

## <a name="view-or-edit-your-firewall-policies-and-custom-rules"></a>Visualización o edición de directivas de firewall y reglas personalizadas

En función de si usa el portal de Microsoft 365 Defender o el centro de administración de Microsoft Endpoint Manager para administrar la protección del firewall, use uno de los procedimientos de la tabla siguiente:

| Portal | Procedure |
|:---|:---|
| portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) | 1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. <br/><br/>2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo y tipo de directiva.<br/><br/>3. Seleccione una pestaña del sistema operativo (por ejemplo **, Windows clientes**).<br/><br/>4. Expanda **Firewall** para ver la lista de directivas.<br/><br/>5. Seleccione una directiva para ver más detalles sobre la directiva. Para realizar cambios o obtener más información sobre la configuración de directivas, consulte los artículos siguientes: <br/>- [Visualización o edición de directivas de dispositivo](mdb-view-edit-policies.md)<br/>- [Configuración del firewall](mdb-firewall.md)<br/>- [Administración de reglas personalizadas para directivas de firewall](mdb-custom-rules-firewall.md)  |
| Microsoft Endpoint Manager centro de administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. Vaya a [https://endpoint.microsoft.com](https://endpoint.microsoft.com) e inicie sesión. Ahora está en el centro de administración de Endpoint Manager.<br/><br/>2. Seleccione **Seguridad del punto de conexión**.<br/><br/>3. Seleccione **Firewall** para ver las directivas en esa categoría. Las reglas personalizadas que se definen para la protección del firewall se enumeran como directivas independientes.<br/><br/>Para obtener ayuda para administrar la configuración de seguridad en Intune, comience con [Administrar la seguridad de los puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security). |

## <a name="set-up-web-content-filtering"></a>Configuración del filtrado de contenido web

El filtrado de contenido web permite al equipo de seguridad realizar un seguimiento y regular el acceso a sitios web en función de sus categorías de contenido, como:

- Contenido para adultos: Sitios relacionados con cultos, juegos de azar, desnudez, pornografía, material sexualmente explícito o violencia
- Ancho de banda alto: descarga de sitios, sitios de uso compartido de imágenes o hosts punto a punto
- Responsabilidad legal: Sitios que incluyen imágenes de abuso infantil, promueven actividades ilegales, fomentan plagios o engaños escolares, o que promueven actividades dañinas
- Ocio: sitios que proporcionan salas de chat basadas en web, juegos en línea, correo electrónico basado en web o redes sociales
- Sin categoría: sitios que no tienen contenido o que recién están registrados

No todos los sitios web de estas categorías son malintencionados, pero podrían ser problemáticos para su empresa debido a las regulaciones de cumplimiento, el uso de ancho de banda u otros problemas. Además, puede crear una directiva de solo auditoría para comprender mejor si el equipo de seguridad debe bloquear las categorías de sitios web.

El filtrado de contenido web está disponible en los principales exploradores web, con bloques realizados por Windows Defender SmartScreen (Microsoft Edge) y Network Protection (Chrome, Firefox, Brave y Opera). Para obtener más información, consulte [Requisitos previos para el filtrado de contenido web](../defender-endpoint/web-content-filtering.md#prerequisites).

### <a name="to-set-up-web-content-filtering"></a>Para configurar el filtrado de contenido web

1. En el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), elija **Configuración** >  **Filtro de** >  contenido web **+ Agregar directiva**.

2. Especifique un nombre y una descripción para la directiva.

3. Seleccione las categorías que desea bloquear. Use el icono expandir para expandir por completo cada categoría primaria y seleccionar categorías de contenido web específicas. Para configurar una directiva de solo auditoría que no bloquee ningún sitio web, no seleccione ninguna categoría.

   No seleccione **Sin categoría**.

4. Especifique el ámbito de la directiva seleccionando grupos de dispositivos para aplicar la directiva. Solo se impedirá que los dispositivos de los grupos de dispositivos seleccionados accedan a sitios web de las categorías seleccionadas.

5. Revise el resumen y guarde la directiva. La actualización de la directiva puede tardar hasta 2 horas en aplicarse a los dispositivos seleccionados.

> [!TIP]
> Para más información sobre el filtrado de contenido web, consulte [Filtrado de contenido web](../defender-endpoint/web-content-filtering.md).

## <a name="review-settings-for-advanced-features"></a>Revisar la configuración de las características avanzadas

Además de las directivas de filtrado de contenido web, firewall y protección de última generación, Defender for Business incluye características de seguridad avanzadas. Estas características se preconfigura mediante la configuración recomendada; sin embargo, puede revisarlos y, si es necesario, editar la configuración para satisfacer sus necesidades empresariales.

Para acceder a la configuración de las características avanzadas, en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)), vaya a **Configuración** >  EndpointsGeneralAdvanced >  **features(Características** **avanzadas** > ).

En la tabla siguiente se describe la configuración de las características avanzadas:

| Configuración | Descripción |
|:---|:---|
| **Investigación automatizada** <br/>(activado de forma predeterminada) | A medida que se generan alertas, pueden producirse investigaciones automatizadas. Cada investigación automatizada determina si una amenaza detectada requiere acción y, a continuación, realiza (o recomienda) acciones de corrección (como enviar un archivo a cuarentena, detener un proceso, aislar un dispositivo o bloquear una dirección URL). Durante la ejecución de una investigación, todas las demás alertas relacionadas que puedan surgir se agregarán a la investigación hasta que se finalice. Si ve una entidad afectada en otro lugar, la investigación automatizada expande su ámbito para incluir esa entidad, y el proceso de investigación se repite.<br/><br/>Puede ver las investigaciones en la página **Incidentes** . Seleccione un incidente y, a continuación, seleccione la pestaña **Investigaciones** .<br/><br/>De forma predeterminada, las funcionalidades automatizadas de investigación y respuesta están activadas, en todo el inquilino. **Se recomienda mantener activada la investigación automatizada**. Si la desactiva, la protección en tiempo real en Antivirus de Microsoft Defender se verá afectada y su nivel general de protección se reducirá. <br/><br/>[Obtenga más información sobre las investigaciones automatizadas](../defender-endpoint/automated-investigations.md).   |
| **Respuesta dinámica**  | Defender for Business incluye los siguientes tipos de acciones de respuesta manual: <br/>- Ejecutar examen de antivirus<br/>- Aislar el dispositivo<br/>- Detener y poner en cuarentena un archivo<br/>- Agregar un indicador para bloquear o permitir un archivo <br/><br/>[Obtenga más información sobre las acciones de respuesta](../defender-endpoint/respond-machine-alerts.md). |
| **Respuesta dinámica para servidores** | (Esta configuración no está disponible actualmente en Defender para empresas)   |
| **Ejecución de script sin firmar de Respuesta dinámica** | (Esta configuración no está disponible actualmente en Defender para empresas)  | 
| **Habilitar EDR en modo de bloque**<br/>(activado de forma predeterminada) | Proporciona protección adicional contra artefactos malintencionados cuando Antivirus de Microsoft Defender no es el producto antivirus principal y se ejecuta en modo pasivo en un dispositivo. La detección y respuesta de puntos de conexión (EDR) en modo de bloque funciona en segundo plano para corregir artefactos malintencionados detectados por EDR funcionalidades. Es posible que el producto antivirus principal que no es de Microsoft haya perdido estos artefactos.<br/><br/>[Obtenga más información sobre EDR en modo de bloque](../defender-endpoint/edr-in-block-mode.md). |
| **Permitir o bloquear un archivo** <br/>(activado de forma predeterminada) | Permite permitir o bloquear un archivo mediante [indicadores](../defender-endpoint/indicator-file.md). Esta funcionalidad requiere que Antivirus de Microsoft Defender esté en modo activo y que se active la [protección](../defender-endpoint/cloud-protection-microsoft-defender-antivirus.md) en la nube.<br/><br/>El bloqueo de un archivo impedirá que se lea, escriba o ejecute en dispositivos de la organización. <br/><br/>[Obtenga más información sobre los indicadores de los archivos](../defender-endpoint/indicator-file.md).  |
| **Indicadores de red personalizados**<br/>(activado de forma predeterminada) | Permite permitir o bloquear una dirección IP, una dirección URL o un dominio mediante [indicadores de red](../defender-endpoint/indicator-ip-domain.md). Esta funcionalidad requiere que Antivirus de Microsoft Defender esté en modo activo y que se active la [protección de red](../defender-endpoint/enable-network-protection.md).<br/><br/>Puede permitir o bloquear direcciones IP, direcciones URL o dominios en función de su propia inteligencia sobre amenazas. También puede advertir a los usuarios con un mensaje si abren una aplicación de riesgo. El símbolo del sistema no les impedirá usar la aplicación, pero puede proporcionar una advertencia para los usuarios.<br/><br/>[Obtenga más información sobre la protección de red](../defender-endpoint/network-protection.md). |
| **Protección contra alteraciones**<br/>(se recomienda activar esta configuración) | La protección contra alteraciones evita que las aplicaciones malintencionadas realicen acciones como:<br/>- Deshabilitación de la protección contra amenazas y virus<br/>- Deshabilitación de la protección en tiempo real<br/>- Desactivar la supervisión del comportamiento<br/>- Deshabilitación de la protección en la nube<br/>- Eliminación de actualizaciones de inteligencia de seguridad<br/>- Deshabilitación de acciones automáticas en las amenazas detectadas<br/><br/>La protección contra alteraciones básicamente bloquea Antivirus de Microsoft Defender a sus valores seguros y predeterminados e impide que las aplicaciones y los métodos no autorizados cambien la configuración de seguridad. <br/><br/>[Obtenga más información sobre la protección contra alteraciones](../defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection.md).  |
| **Mostrar los detalles del usuario**<br/>(activado de forma predeterminada) | Permite a los usuarios de su organización ver detalles, como la imagen, el nombre, el título y el departamento de los empleados. Estos detalles se almacenan en Azure Active Directory (Azure AD).<br/><br/>[Obtenga más información sobre los perfiles de usuario en Azure AD](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).  |
| **integración Skype Empresarial**<br/>(activado de forma predeterminada) | Skype Empresarial se retiró en julio de 2021. Si aún no se ha movido a Microsoft Teams, consulte [Configuración de Microsoft Teams en su pequeña empresa](/microsoftteams/deploy-small-business). <br/><br/>La integración con Microsoft Teams (o el Skype Empresarial anterior) permite la comunicación con un solo clic entre las personas de su empresa.   |
| **Filtrado de contenido web**<br/>(activado de forma predeterminada) | Bloquear el acceso a sitios web que contienen contenido no deseado y realizar un seguimiento de la actividad web en todos los dominios. Consulte [Configuración del filtrado de contenido web](#set-up-web-content-filtering). |
| **conexión Microsoft Intune**<br/>(Se recomienda activar esta configuración si tiene Intune) | Si la suscripción de su organización incluye Microsoft Intune (incluida en [Microsoft 365 Empresa Premium](../../business/index.yml)), esta configuración permite a Defender for Business compartir información sobre los dispositivos con Intune.  |
| **Detección de dispositivo**<br/>(activado de forma predeterminada) | Permite al equipo de seguridad encontrar dispositivos no administrados conectados a la red de la empresa. Los dispositivos desconocidos y no administrados presentan riesgos significativos para la red, ya sea una impresora sin revisiones, dispositivos de red con configuraciones de seguridad débiles o un servidor sin controles de seguridad. <br/><br/>La detección de dispositivos usa dispositivos incorporados para detectar dispositivos no administrados, de modo que el equipo de seguridad pueda incorporar los dispositivos no administrados y reducir la vulnerabilidad. <br/><br/>[Obtenga más información sobre la detección de dispositivos](../defender-endpoint/device-discovery.md).    |
| **Versión preliminar de las características** | Microsoft actualiza continuamente servicios, como Defender para empresas, para incluir nuevas mejoras y funcionalidades de características. Si opta por recibir características en versión preliminar, será uno de los primeros en probar las próximas características en la experiencia en versión preliminar. <br/><br/>[Obtenga más información sobre las características en versión preliminar](../defender-endpoint/preview.md).  |

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>Visualización y edición de otras configuraciones en el portal de Microsoft 365 Defender

Además de las directivas de seguridad que se aplican a los dispositivos, hay otras configuraciones que puede ver y editar en Defender para empresas. Por ejemplo, especifica la zona horaria que se va a usar y puede incorporar (o fuera del panel) dispositivos. 

> [!NOTE]
> Es posible que vea más opciones de configuración en el inquilino de las que se enumeran en este artículo. En este artículo se resalta la configuración más importante que debe revisar en Defender para empresas.

### <a name="settings-to-review-for-defender-for-business"></a>Configuración revisar para Defender para empresas

En la tabla siguiente se describe la configuración que se va a ver (y, si es necesario, editar) en Defender for Business:

| Categoría | Configuración | Descripción |
|:---|:---|:---|
| **Security Center** | **Zona horaria** | Seleccione la zona horaria que se usará para las fechas y horas que se muestran en incidentes, amenazas detectadas e investigación automatizada & corrección. Puede usar UTC o la zona horaria local (*recomendado*).  |
| **Microsoft 365 Defender** | **Account** | Vea los detalles, como dónde se almacenan los datos, el identificador de inquilino y el identificador de la organización (organización). |
| **Microsoft 365 Defender**  | **Versión preliminar de las características**  | Active las características en versión preliminar para probar las próximas características y nuevas funcionalidades. Puede estar entre las primeras en obtener una vista previa de las nuevas características y proporcionar comentarios. |
| **Puntos de conexión**  | **Notificaciones por correo electrónico** | Configure o edite las reglas de notificación por correo electrónico. Cuando se detectan vulnerabilidades o se crea una alerta, los destinatarios especificados en las reglas de notificación por correo electrónico recibirán un correo electrónico. [Obtenga más información sobre las notificaciones por correo electrónico](mdb-email-notifications.md). |
| **Puntos de conexión**   | **Administración de dispositivos** >  **Incorporación** | Incorporación de dispositivos a Defender for Business mediante un script descargable. Para más información, consulte [Incorporación de dispositivos para Microsoft Defender para Empresas](mdb-onboard-devices.md).   |  
| **Puntos de conexión**  |  **Administración de dispositivos** >  **Offboarding** | Dispositivos offboard (quitar) de Defender for Business. Al desconectar un dispositivo, ya no envía datos a Defender for Business, pero se conservan los datos recibidos antes de la retirada. Para obtener más información, consulte [Offboarding a device (Offboarding a device](mdb-offboard-devices.md)).  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>Acceso a la configuración en el portal de Microsoft 365 Defender

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) e inicie sesión.

2. Seleccione **Configuración** y, a continuación, seleccione una categoría (como **Security Center**, **Microsoft 365 Defender** o **Puntos de conexión**).

3. En la lista de configuraciones, seleccione un elemento para ver o editar.

## <a name="next-steps"></a>Siguientes pasos

Continúe con una o varias de las siguientes tareas:

- [Comenzar mediante Microsoft Defender para Empresas](mdb-get-started.md)
- [Administración de dispositivos en Microsoft Defender para Empresas](mdb-manage-devices.md)
- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
- [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-policies.md)

- [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-policies.md)
