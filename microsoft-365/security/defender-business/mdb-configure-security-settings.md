---
title: Ver y editar la configuración de seguridad en Microsoft Defender para empresas
description: Configurar las directivas de seguridad en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: bccbc7cf33d8be285bac801512de974f0277cf06
ms.sourcegitcommit: a216617d6ff27fe7d3089a047fbeaac5d72fd25c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63512466"
---
# <a name="view-and-edit-your-security-policies-and-settings-in-microsoft-defender-for-business"></a>Ver y editar las directivas de seguridad y la configuración en Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando [para Microsoft 365 Empresa Premium](../../business-premium/index.md) clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

## <a name="overview"></a>Información general

Después de incorporar los dispositivos de la empresa a Microsoft Defender para empresas, el siguiente paso es ver y, si es necesario, editar las directivas de seguridad y la configuración. Las directivas de seguridad incluyen:

- **[Directivas de protección de última generación](#view-or-edit-your-next-generation-protection-policies)**, que determinan la protección antivirus y antimalware para los dispositivos de su empresa

- **[Reglas y protección de firewall](#view-or-edit-your-firewall-policies-and-custom-rules)**, que determinan qué tráfico de red puede fluir hacia o desde los dispositivos de la empresa

- **[Filtrado de contenido web](#set-up-web-content-filtering)**, que impide que las personas visiten determinados sitios web (URL) en función de categorías, como contenido para adultos o responsabilidad legal.

En Defender para empresas, las directivas de seguridad se aplican a dispositivos a través [de grupos de dispositivos](mdb-create-edit-device-groups.md#what-is-a-device-group). 

Además de las directivas de seguridad, puede ver y editar la [configuración, como](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal) la zona horaria que se usará en el portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) y si va a recibir características de vista previa a medida que estén disponibles.

Use este artículo como guía para administrar las directivas y la configuración de seguridad.

## <a name="what-to-do"></a>Qué hacer

1. [Elige dónde administrar tus dispositivos y directivas de seguridad](#choose-where-to-manage-security-policies-and-devices).

2. [Ver o editar las directivas de protección de próxima generación](#view-or-edit-your-next-generation-protection-policies).

3. [Ver o editar las directivas de firewall y las reglas personalizadas](#view-or-edit-your-firewall-policies-and-custom-rules).

4. [Configurar el filtrado de contenido web](#set-up-web-content-filtering).

5. [Ver y editar otras opciones de configuración en el portal Microsoft 365 Defender web](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal). 

6. [Continúe con los pasos siguientes](#next-steps).

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="choose-where-to-manage-security-policies-and-devices"></a>Elegir dónde administrar dispositivos y directivas de seguridad

Defender para empresas cuenta con un [proceso de configuración simplificado](mdb-simplified-configuration.md) que ayuda a simplificar el proceso de configuración y configuración. Si selecciona el proceso de configuración simplificado, puede ver y administrar las directivas de seguridad en el portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)). Sin embargo, no está limitado a esta opción. Si ha estado usando Microsoft Endpoint Manager (que incluye Microsoft Intune), puede seguir usando su Endpoint Manager.

La siguiente tabla puede ayudarle a elegir dónde administrar sus dispositivos y directivas de seguridad. <br/><br/>

| Opción | Descripción |
|:---|:---|
| **Usar el Microsoft 365 Defender web** (*recomendado*) | El Microsoft 365 Defender web ([https://security.microsoft.com/](https://security.microsoft.com/)) puede ser tu tienda única para administrar los dispositivos de tu empresa, las directivas de seguridad y la configuración de seguridad. Puede acceder a sus directivas y configuraciones de seguridad, usar el panel de administración de vulnerabilidades [&](mdb-view-tvm-dashboard.md) amenazas [](mdb-view-manage-incidents.md) y ver y administrar incidentes en un solo lugar. <br/><br/>Si usas Microsoft Endpoint Manager, los dispositivos que incorpores a Defender for Business y tus directivas de seguridad son visibles en Endpoint Manager. Para obtener más información, consulte los artículos siguientes:<br/><br/>- [Configuración y configuración predeterminadas de Defender para empresas Microsoft Endpoint Manager](mdb-next-gen-configuration-settings.md#defender-for-business-default-settings-and-microsoft-endpoint-manager)<br/><br/>- [Firewall en Microsoft Defender para empresas](mdb-firewall.md)   |
| **Use Microsoft Endpoint Manager** | Si su empresa ya usa Endpoint Manager (que incluye Microsoft Intune) para administrar directivas de seguridad, puede seguir usando Endpoint Manager para administrar dispositivos y directivas de seguridad. Para obtener más información, consulta [Administrar la seguridad de dispositivos con directivas de seguridad de puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). <br/><br/>Si decide cambiar al proceso de configuración simplificado en [Defender para](mdb-simplified-configuration.md) empresas, se le pedirá que elimine las directivas de seguridad existentes en Endpoint Manager para evitar [conflictos](mdb-troubleshooting.yml) de directivas más adelante. |

> [!IMPORTANT]
> Si va a administrar directivas de seguridad en el portal de Microsoft 365 Defender, puede ver  dichas directivas en Endpoint Manager, enumeradas como directivas de antivirus o firewall. Cuando vea las directivas de firewall en Endpoint Manager, verá dos directivas enumeradas: una directiva para la protección de firewall y otra para reglas personalizadas.

## <a name="view-or-edit-your-next-generation-protection-policies"></a>Ver o editar las directivas de protección de próxima generación

En función de si usa el portal de Microsoft 365 Defender o Microsoft Endpoint Manager para administrar las directivas de protección de próxima generación, use uno de los procedimientos de la tabla siguiente: <br/><br/>

| Portal | Procedure |
|:---|:---|
| Microsoft 365 Defender web ([https://security.microsoft.com](https://security.microsoft.com)) | 1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. <br/><br/>2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo y tipo de directiva.<br/><br/>3. Seleccione una pestaña del sistema operativo (por ejemplo **, Windows clientes**).<br/><br/>4. Expanda **La protección de última generación** para ver la lista de directivas.<br/><br/>5. Seleccione una directiva para ver más detalles sobre la directiva. Para realizar cambios o obtener más información sobre la configuración de directivas, consulte los artículos siguientes: <br/>- [Ver o editar directivas de dispositivos](mdb-view-edit-policies.md)<br/>- [Comprender las opciones de configuración de próxima generación](mdb-next-gen-configuration-settings.md)  |
| Microsoft Endpoint Manager de administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. Vaya a [https://endpoint.microsoft.com](https://endpoint.microsoft.com) e inicie sesión. Ahora estás en el Centro de administración Microsoft Endpoint Manager administración.<br/><br/>2. Seleccione Seguridad **del extremo**.<br/><br/>3. Seleccione **Antivirus** para ver las directivas de esa categoría. <br/><br/>Para obtener ayuda para administrar la configuración de seguridad en Microsoft Endpoint Manager, comience con Administrar la seguridad [de puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security). |

## <a name="view-or-edit-your-firewall-policies-and-custom-rules"></a>Ver o editar las directivas de firewall y las reglas personalizadas

En función de si usa el portal de Microsoft 365 Defender o Microsoft Endpoint Manager para administrar la protección del firewall, use uno de los procedimientos de la tabla siguiente: <br/><br/>

| Portal | Procedure |
|:---|:---|
| Microsoft 365 Defender web ([https://security.microsoft.com](https://security.microsoft.com)) | 1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. <br/><br/>2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo y tipo de directiva.<br/><br/>3. Seleccione una pestaña del sistema operativo (por ejemplo **, Windows clientes**).<br/><br/>4. Expanda **Firewall** para ver la lista de directivas.<br/><br/>5. Seleccione una directiva para ver más detalles sobre la directiva. Para realizar cambios o obtener más información sobre la configuración de directivas, consulte los artículos siguientes: <br/>- [Ver o editar directivas de dispositivos](mdb-view-edit-policies.md)<br/>- [Configuración del firewall](mdb-firewall.md)<br/>- [Administrar las reglas personalizadas para directivas de firewall](mdb-custom-rules-firewall.md)  |
| Microsoft Endpoint Manager de administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. Vaya a [https://endpoint.microsoft.com](https://endpoint.microsoft.com) e inicie sesión. Ahora estás en el Centro de administración Microsoft Endpoint Manager administración.<br/><br/>2. Seleccione Seguridad **del extremo**.<br/><br/>3. Seleccione **Firewall** para ver las directivas de esa categoría. Las reglas personalizadas que se definen para la protección de firewall se enumeran como directivas independientes.<br/><br/>Para obtener ayuda para administrar la configuración de seguridad en Microsoft Endpoint Manager, comience con Administrar la seguridad [de puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security). |

## <a name="set-up-web-content-filtering"></a>Configurar el filtrado de contenido web

El filtrado de contenido web permite al equipo de seguridad realizar un seguimiento y regular el acceso a los sitios web en función de sus categorías de contenido, como:

- Contenido para adultos: sitios relacionados con sectas, juegos de azar, desnudez, pornografía, material sexualmente explícito o violencia

- Ancho de banda alto: descargar sitios, sitios de uso compartido de imágenes o hosts punto a punto

- Responsabilidad legal: sitios que incluyen imágenes de maltrato infantil, promueven actividades ilegales, fomentan el plagio o el engaño escolar, o que promueven actividades dañinas

- Ocio: sitios que proporcionan salas de chat basadas en web, juegos en línea, correo electrónico basado en web o redes sociales

- Sin categorizar: sitios que no tienen contenido o que están recién registrados

No todos los sitios web de estas categorías son malintencionados, pero podrían ser problemáticos para su empresa debido a las normativas de cumplimiento, el uso del ancho de banda u otras preocupaciones. Además, puede crear una directiva de solo auditoría para comprender mejor si su equipo de seguridad debe bloquear las categorías de sitios web.

El filtrado de contenido web está disponible en los principales exploradores web, con bloques realizados por Windows Defender SmartScreen (Microsoft Edge) y Network Protection (Chrome, Firefox, Brave y Opera). Para obtener más información, vea [Prerequisites for web content filtering](../defender-endpoint/web-content-filtering.md#prerequisites).

### <a name="to-set-up-web-content-filtering"></a>Para configurar el filtrado de contenido web

1. En el portal Microsoft 365 Defender web ([https://security.microsoft.com](https://security.microsoft.com)), elija **Configuración** >  **Web content filtering** > **+ Add policy**.

2. Especifique un nombre y una descripción para la directiva.

3. Seleccione las categorías que desea bloquear. Use el icono expandir para expandir completamente cada categoría principal y seleccionar categorías de contenido web específicas.

   Para configurar una directiva de solo auditoría que no bloquee ningún sitio web, no seleccione ninguna categoría.

   No seleccione **Uncategorized**.

4. Especifica el ámbito de directiva seleccionando grupos de dispositivos para aplicar la directiva. Solo se impedirá el acceso a los sitios web de los grupos de dispositivos seleccionados en las categorías seleccionadas.

5. Revise el resumen y guarde la directiva. La actualización de directiva puede tardar hasta 2 horas en aplicarse a los dispositivos seleccionados.

> [!TIP]
> Para obtener más información sobre el filtrado de contenido web, consulte [Filtrado de contenido web](../defender-endpoint/web-content-filtering.md).

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>Ver y editar otras opciones en el portal Microsoft 365 Defender web

Además de las directivas de seguridad que se aplican a los dispositivos, hay otras opciones de configuración que puedes ver y editar en Defender para empresas. Por ejemplo, especifica la zona horaria que se va a usar y puede incorporar dispositivos (o fuera de la pantalla). 

> [!NOTE]
> Es posible que veas más opciones de configuración en el espacio empresarial de las que aparecen en este artículo. En este artículo se resalta la configuración más importante que debe revisar en Defender para empresas.

### <a name="settings-to-review-for-defender-for-business"></a>Configuración revisar para Defender for Business

En la tabla siguiente se describe la configuración para ver (y, si es necesario, editar) en Defender para empresas.

<br/><br/>

| Categoría | Configuración | Descripción |
|:---|:---|:---|
| **Centro de seguridad** | **Zona horaria** | Seleccione la zona horaria que se usará para las fechas y horas mostradas en incidentes, amenazas detectadas e investigación automatizada & corrección. Puede usar UTC o la zona horaria local (*recomendado*).  |
| **Microsoft 365 Defender** | **Account** | Ver detalles, como dónde se almacenan los datos, el identificador de inquilino y el identificador de la organización (organización). |
| **Microsoft 365 Defender**  | **Versión preliminar de las características**  | Activa las características de vista previa para probar las próximas características y nuevas funcionalidades. Puede ser uno de los primeros en obtener una vista previa de las nuevas características y proporcionar comentarios. |
| **Puntos de conexión**  | **Notificaciones de correo electrónico** | Configurar o editar las reglas de notificación de correo electrónico. Cuando se detectan vulnerabilidades o se crea una alerta, los destinatarios especificados en las reglas de notificación de correo electrónico recibirán un correo electrónico. [Obtenga más información sobre las notificaciones por correo electrónico](mdb-email-notifications.md). |
| **Puntos de conexión**   | **Administración de dispositivos** >  **Incorporación** | Incorporar dispositivos a Defender para empresas mediante un script descargable. Para obtener más información, consulta [Incorporación de dispositivos a Microsoft Defender para empresas](mdb-onboard-devices.md).   |  
| **Puntos de conexión**  |  **Administración de dispositivos** >  **Offboarding** | Dispositivos offboard (quitar) de Defender para empresas. Al salir de un dispositivo, ya no envía datos a Defender para empresas, pero los datos recibidos antes de la salida se conservan. Para obtener más información, consulta [Offboarding a device](mdb-onboard-devices.md#offboarding-a-device).  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>Acceder a la configuración en el Microsoft 365 Defender web

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) e inicie sesión.

2. Seleccione **Configuración** y, a continuación, seleccione una categoría (como Centro de **seguridad,** **Microsoft 365 Defender** o **Extremos**).

3. En la lista de opciones, seleccione un elemento para ver o editar.


## <a name="next-steps"></a>Pasos siguientes

Continúe con una o varias de las siguientes tareas:

- [Introducción al uso de Microsoft Defender para empresas](mdb-get-started.md)

- [Administrar dispositivos en Microsoft Defender para empresas](mdb-manage-devices.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)

- [Ver o editar directivas en Microsoft Defender para empresas](mdb-view-edit-policies.md)
