---
title: Crear una nueva directiva en Microsoft Defender para empresas
description: Obtenga información sobre cómo crear una nueva directiva de seguridad en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/27/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: bb6ec4c3488eff847933935ce7cf84ec5194c3cc
ms.sourcegitcommit: 27eb93a7d46bcbb9c948a50b0a8481ffd3832ca0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/28/2021
ms.locfileid: "61612517"
---
# <a name="create-a-new-policy-in-microsoft-defender-for-business-preview"></a>Crear una nueva directiva en Microsoft Defender para empresas (versión preliminar)

> [!IMPORTANT]
> Microsoft Defender para empresas ya está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán aquí [para](https://aka.ms/mdb-preview) solicitarlo. Incorporaremos un conjunto inicial de clientes y asociados en las próximas semanas y ampliaremos la versión preliminar antes de la disponibilidad general. Ten en cuenta que la vista previa se iniciará con un [conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios)y agregaremos funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 


Microsoft Defender para empresas (versión preliminar) incluye directivas predeterminadas que usan la configuración recomendada para proteger los dispositivos de la empresa desde el primer día. Por ejemplo, tiene directivas de protección **de** última generación y directivas de **firewall** integradas con la configuración de seguridad recomendada. Pero no está limitado a las directivas predeterminadas. También puede crear nuevas directivas, como se describe en este artículo.

> [!TIP]
> Si desea editar una directiva existente, vea Ver o editar directivas [en Microsoft Defender para empresas (versión preliminar).](mdb-view-edit-policies.md)

## <a name="create-a-new-policy"></a>Crear una nueva directiva

1. Vaya al portal de Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente)** y el tipo de directiva (como **la protección de última** generación y **firewall).** 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes)** y, a continuación, revise la lista de directivas **de protección de próxima** generación. 

4. En **Protección de última generación** o **Firewall,** seleccione **+ Agregar**.

5. En la **pestaña Información general,** siga estos pasos:

   1. Especifique un nombre y una descripción. Esta información le ayudará a usted y a su equipo a identificar la directiva más adelante.
   2. Revise el orden de la directiva y edéclo si es necesario. (Para obtener más información, vea [Policy order](mdb-policy-order.md).)
   3. Elija **Siguiente**. 

7. En la **pestaña Grupos de** dispositivos, crea un nuevo grupo de dispositivos o usa un grupo existente. Las directivas se asignan a dispositivos a través de grupos de dispositivos. Estos son algunos aspectos a tener en cuenta:

   - Inicialmente, es posible que solo tenga el grupo de dispositivos predeterminado, que incluye los dispositivos que los usuarios de su empresa usan para tener acceso a los datos y el correo electrónico de la compañía. Puedes conservar y usar el grupo de dispositivos predeterminado.
   - Crea un nuevo grupo de dispositivos para aplicar una directiva con una configuración específica que sea diferente de la directiva predeterminada. 
   - Cuando configuras el grupo de dispositivos, especificas determinados criterios, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que los excluyas. 
   - Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y personalizados que definas, se almacenan en Azure Active Directory (Azure AD).

   Para obtener más información sobre los grupos de dispositivos, consulta [Grupos de dispositivos en Defender para empresas (versión preliminar).](mdb-create-edit-device-groups.md)

8. En la **pestaña Configuración,** especifique la configuración de la directiva y, a continuación, elija **Siguiente**. Para obtener más información acerca de las opciones individuales, vea [Configuración de Microsoft Defender para empresas (versión preliminar).](mdb-next-gen-configuration-settings.md)

9. En la **pestaña Revisar la directiva,** revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Realice los cambios necesarios seleccionando **Editar**.
   - Cuando esté listo para continuar, elija **Crear directiva**.

## <a name="next-steps"></a>Siguientes pasos

Elija una o varias de las siguientes tareas:

- [Introducción al uso de Defender para empresas (versión preliminar)](mdb-get-started.md)

- [Ver o editar directivas](mdb-view-edit-policies.md)

- [Administrar dispositivos](mdb-manage-devices.md)

- [Ver y administrar incidentes](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)
