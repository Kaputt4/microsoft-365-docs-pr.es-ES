---
title: Configurar la configuración de seguridad en Microsoft Defender para empresas
description: Configurar las directivas de seguridad en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/29/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 941189e1db95d493eedd67297a2dd19abc3ecc9e
ms.sourcegitcommit: 4c207a9bdbb6c8ba372ae37907ccefca031a49f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "62463482"
---
# <a name="configure-your-security-policies-in-microsoft-defender-for-business-preview"></a>Configurar las directivas de seguridad en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

Después de incorporar los dispositivos de la organización a Microsoft Defender para empresas (versión preliminar), el siguiente paso es ver y, si es necesario, editar las directivas de seguridad. En Defender para empresas (versión preliminar), la configuración de seguridad se aplica a los dispositivos a través de directivas. Estas directivas se aplican a grupos [de dispositivos](mdb-create-edit-device-groups.md#what-is-a-device-group). 

También hay otras opciones de configuración que puede configurar en Defender para empresas (versión preliminar). Estas opciones incluyen la zona horaria, si se reciben características de vista previa y mucho más.

## <a name="what-to-do"></a>Qué hacer

1. [Obtener una introducción rápida a las directivas de seguridad predeterminadas en Defender para empresas](#default-policies-in-defender-for-business)

2. [Elige dónde administrar tus dispositivos y directivas de seguridad](#choose-where-to-manage-security-policies-and-devices).

3. [Ver las directivas de seguridad](#view-your-security-policies).

4. [Ver y editar otras opciones en el portal Microsoft 365 Defender web](#view-and-edit-other-settings-in-the-microsoft-365-defender-portal) 

5. [Continúe con los pasos siguientes](#next-steps).

## <a name="default-policies-in-defender-for-business"></a>Directivas predeterminadas en Defender para empresas

Defender para empresas (versión preliminar) incluye directivas predeterminadas que usan la configuración recomendada. Estas directivas incluyen:

- [Configuración de protección de última](mdb-next-gen-configuration-settings.md) generación que determina Antivirus de Microsoft Defender y otras características de protección contra amenazas; y 
- [Configuración de firewall](mdb-firewall.md) que determina qué tráfico de red puede fluir hacia y desde los dispositivos cliente Windows la organización.

Puedes aplicar las directivas predeterminadas a Windows dispositivos cliente durante el proceso de configuración inicial. También puede definir nuevas directivas y editar directivas existentes para que se adapten a sus necesidades empresariales. 

## <a name="choose-where-to-manage-security-policies-and-devices"></a>Elegir dónde administrar dispositivos y directivas de seguridad

Defender para empresas (versión preliminar) cuenta con un [proceso de configuración simplificado](mdb-simplified-configuration.md) que ayuda a simplificar el proceso de configuración y configuración. Si selecciona el proceso de configuración simplificado, puede ver y administrar las directivas de seguridad en el portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)). Sin embargo, no está limitado a esta opción. Si has estado usando Microsoft Endpoint Manager (que incluye Microsoft Intune) o una solución de productividad que no sea de Microsoft para administrar tus dispositivos y directivas de seguridad, puedes seguir usando la solución actual.

La siguiente tabla puede ayudarle a elegir dónde administrar sus dispositivos y directivas de seguridad. <br/><br/>

| Opción | Descripción |
|:---|:---|
| **Usar las directivas de seguridad predeterminadas en el portal de Microsoft 365 Defender (***recomendado*) | Defender para empresas (versión preliminar) se diseñó para la pequeña o mediana empresa ocupada en mente. Las directivas de seguridad predeterminadas de Defender para empresas están diseñadas para proteger los dispositivos de su organización desde el primer día.<br/><br/>Puede usar el portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) para ver y administrar las directivas de seguridad.<br/><br/>Para obtener más información, consulta [Ver o editar directivas de dispositivo.](mdb-view-edit-policies.md) |
| **Use Microsoft Endpoint Manager** | Si su organización usa Microsoft Endpoint Manager para administrar directivas de seguridad, puede seguir usando Endpoint Manager y aplicar directivas de seguridad a algunos o todos los dispositivos. Para obtener más información, consulta [Administrar la seguridad de dispositivos con directivas de seguridad de puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security-policy). <br/><br/>Considere la posibilidad de cambiar al [proceso de configuración simplificado en Defender para empresas](mdb-simplified-configuration.md). Si realiza el cambio, se le pedirá que elimine las directivas de seguridad existentes en Microsoft Endpoint Manager antes de continuar con el proceso de configuración simplificado en Defender para empresas. Eliminar las directivas en Microsoft Endpoint Manager ayuda a evitar conflictos de directivas más adelante. |

> [!TIP]
> Si desea registrarse en el programa de vista previa de Microsoft Defender para empresas, visite [https://aka.ms/MDB-Preview](https://aka.ms/MDB-Preview). Para obtener más información, consulta [Obtener Microsoft Defender para empresas (versión preliminar).](get-defender-business.md)

## <a name="view-your-security-policies"></a>Ver las directivas de seguridad

Para ver la lista de directivas de seguridad, use uno de los procedimientos de la tabla siguiente:
<br/><br/>

| Portal | Procedure |
|:---|:---|
| Microsoft 365 Defender web ([https://security.microsoft.com](https://security.microsoft.com)) | 1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. <br/><br/>2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo y tipo de directiva.<br/><br/>3. Seleccione una pestaña del sistema operativo (por ejemplo **, Windows clientes**).<br/><br/>4. Expanda una categoría (como Protección de  última generación o **Firewall**) para ver la lista de directivas.<br/><br/>5. Seleccione una directiva para ver más detalles sobre la directiva. Para realizar cambios o obtener más información sobre la configuración de directivas, consulte los artículos siguientes: <br/>- [Ver o editar directivas de dispositivos](mdb-view-edit-policies.md)<br/>- [Comprender las opciones de configuración de próxima generación](mdb-next-gen-configuration-settings.md)<br/>- [Configuración del firewall](mdb-firewall.md)  |
| Microsoft Endpoint Manager de administración ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) | 1. Vaya a [https://endpoint.microsoft.com](https://endpoint.microsoft.com) e inicie sesión. Ahora estás en el Centro de administración Microsoft Endpoint Manager administración.<br/><br/>2. Seleccione Seguridad **del extremo**.<br/><br/>3. Seleccione una categoría, como **Antivirus**, **Firewall****,** Detección y respuesta de puntos de conexión o **Reducción** de superficie de ataque para ver las directivas de esa categoría. <br/><br/>Para obtener ayuda para administrar la configuración de seguridad en Microsoft Endpoint Manager, comience con Administrar la seguridad [de puntos de conexión en Microsoft Intune](/mem/intune/protect/endpoint-security). |

## <a name="view-and-edit-other-settings-in-the-microsoft-365-defender-portal"></a>Ver y editar otras opciones en el portal Microsoft 365 Defender web

Además de las directivas de seguridad que se aplican a los dispositivos, hay otras opciones de configuración que puedes ver y editar en Defender para empresas (versión preliminar). Por ejemplo, especifica la zona horaria que se va a usar y puede incorporar dispositivos (o fuera de la pantalla). 

> [!NOTE]
> Es posible que veas más opciones de configuración en el espacio empresarial de las que aparecen en este artículo. Estamos resaltando la configuración que debes revisar en Defender para empresas (versión preliminar).

### <a name="settings-to-review-for-defender-for-business"></a>Configuración revisar para Defender for Business

En la tabla siguiente se describe la configuración para ver (y, si es necesario, editar) en Defender para empresas (versión preliminar).

<br/><br/>

| Categoría | Configuración | Descripción |
|:---|:---|:---|
| **Centro de seguridad** | **Zona horaria** | Seleccione la zona horaria que se usará para las fechas y horas mostradas en incidentes, amenazas detectadas e investigación automatizada & corrección. Puede usar UTC o la zona horaria local (*recomendado*).  |
| **Microsoft 365 Defender** | **Account** | Ver detalles, como dónde se almacenan los datos, el identificador de inquilino y el identificador de la organización (organización). |
| **Microsoft 365 Defender**  | **Versión preliminar de las características**  | Activa las características de vista previa para probar las próximas características y nuevas funcionalidades. Puede ser uno de los primeros en obtener una vista previa de las nuevas características y proporcionar comentarios. |
| **Puntos de conexión**  | **Notificaciones por correo electrónico** | Configurar o editar las reglas de notificación de correo electrónico. Cuando se detectan vulnerabilidades o se crea una alerta, los destinatarios especificados en las reglas de notificación de correo electrónico recibirán un correo electrónico. [Obtenga más información sobre las notificaciones por correo electrónico](mdb-email-notifications.md). |
| **Puntos de conexión**   | **Administración de dispositivos** >  **Incorporación** | Incorporar dispositivos a Defender para empresas mediante un script descargable. Para obtener más información, consulta [Incorporación de un dispositivo con un script local en Defender para empresas](mdb-onboard-devices.md#onboard-a-device-using-a-local-script-in-defender-for-business).   |  
| **Puntos de conexión**  |  **Administración de dispositivos** >  **Offboarding** | Dispositivos offboard (quitar) de Defender para empresas (versión preliminar). Al salir de un dispositivo, ya no envía datos a Defender para empresas (versión preliminar), pero los datos recibidos antes de la salida se conservan. Para obtener más información, consulta [Offboard a device](mdb-onboard-devices.md#what-if-i-want-to-offboard-a-device).  |

### <a name="access-your-settings-in-the-microsoft-365-defender-portal"></a>Acceder a la configuración en el portal de Microsoft 365 Defender web

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com/](https://security.microsoft.com/)) e inicie sesión.

2. Seleccione **Configuración** y, a continuación, seleccione una categoría (como **Centro** de seguridad, **Microsoft 365 Defender** o **Extremos**).

3. En la lista de opciones, seleccione un elemento para ver o editar.


## <a name="next-steps"></a>Siguientes pasos

Continúe con una o varias de las siguientes tareas:

- [Introducción al uso de Microsoft Defender para empresas (versión preliminar)](mdb-get-started.md)

- [Administrar dispositivos en Microsoft Defender para empresas (versión preliminar)](mdb-manage-devices.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas (versión preliminar)](mdb-view-manage-incidents.md)

- [Ver o editar directivas en Microsoft Defender para empresas (versión preliminar)](mdb-view-edit-policies.md)

