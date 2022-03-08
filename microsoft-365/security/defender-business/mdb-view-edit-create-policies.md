---
title: Ver o editar directivas en Microsoft Defender para empresas
description: Obtenga información sobre cómo ver, editar, crear y eliminar directivas de protección de próxima generación en Microsoft Defender para empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/03/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 11ab3f20b6e0b96b28dd285d05c2d57dd9455baa
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63327749"
---
# <a name="view-or-edit-policies-in-microsoft-defender-for-business"></a>Ver o editar directivas en Microsoft Defender para empresas

> [!IMPORTANT]
> Microsoft Defender para empresas se está implementando para Microsoft 365 Empresa Premium clientes, a partir del 1 de marzo de 2022. Defender para empresas como suscripción independiente está en versión preliminar y se irá lanzando gradualmente a los clientes y partners de TI que se inscribirán [aquí para](https://aka.ms/mdb-preview) solicitarla. La vista previa incluye [un conjunto inicial de escenarios](mdb-tutorials.md#try-these-preview-scenarios) y vamos a agregar funcionalidades con regularidad.
> 
> Parte de la información de este artículo se refiere a productos o servicios predefinidos que podrían modificarse considerablemente antes de su lanzamiento comercial. Microsoft no ofrece garantías, explícitas o implícitas, de la información proporcionada aquí. 

En Microsoft Defender para empresas, la configuración de seguridad se configura a través de directivas que se aplican a dispositivos. Para simplificar la configuración y la experiencia de configuración, Defender para empresas incluye directivas preconfiguradas para ayudar a proteger los dispositivos de la organización tan pronto como se incorpore. Puede usar las directivas predeterminadas, editar directivas o crear sus propias directivas.

**En este artículo se describe cómo**:

- [Obtener información general sobre las directivas predeterminadas](#default-policies-in-defender-for-business)

- [Ver las directivas existentes](#view-your-existing-policies)

- [Editar una directiva existente](#edit-an-existing-policy)

- [Crear una nueva directiva](#create-a-new-policy)

>
> **¿Tiene un minuto?**
> Por favor, haga <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">nuestra breve encuesta sobre Microsoft Defender para empresas</a>. Nos encantaría conocer su opinión.
>

## <a name="default-policies-in-defender-for-business"></a>Directivas predeterminadas en Defender para empresas

En Defender para empresas, hay dos tipos principales de directivas para proteger los dispositivos de la organización:

- **Directivas de protección de próxima generación**, que determinan cómo se configuran Antivirus de Microsoft Defender y otras características de protección contra amenazas

- **Directivas de firewall**, que determinan qué tráfico de red puede fluir desde y hacia los dispositivos de la organización


## <a name="view-your-existing-policies"></a>Ver las directivas existentes

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente**) y el tipo de directiva (como la **protección de última** generación **y firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes**) y, a continuación, revise la lista de directivas  en las categorías Protección de próxima generación y **Firewall**. 

4. Para ver más detalles sobre una directiva, seleccione su nombre. Se abrirá un panel lateral que proporciona más información sobre esa directiva, como qué dispositivos están protegidos por esa directiva.

## <a name="edit-an-existing-policy"></a>Editar una directiva existente

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente**) y el tipo de directiva (como la **protección de última** generación **y firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes**) y, a continuación, revise la lista de directivas  en las categorías Protección de próxima generación y **Firewall**. 

4. Para editar una directiva, seleccione su nombre y, a continuación, elija **Editar**.

5. En la **pestaña Información general** , revise la información. Si es necesario, puede editar la descripción. A continuación, elija **Siguiente**.

6. En la **pestaña Grupos de dispositivos** , determine qué grupos de dispositivos deben recibir esta directiva.  

   - Para mantener el grupo de dispositivos seleccionado tal como está, elija **Siguiente**.
   - Para quitar un grupo de dispositivos de la directiva, selecciona **Quitar**.
   - Para configurar un nuevo grupo de dispositivos, selecciona **Crear nuevo grupo** y, a continuación, configura el grupo de dispositivos. (Para obtener ayuda con esta tarea, consulta [Grupos de dispositivos en Microsoft Defender para empresas](mdb-create-edit-device-groups.md)).
   - Para aplicar la directiva a otro grupo de dispositivos, selecciona **Usar grupo existente**.

   Después de especificar qué grupos de dispositivos deben recibir la directiva, elija **Siguiente**.

7. En la **pestaña Configuración** , revise la configuración. Si es necesario, puede editar la configuración de la directiva. Para obtener ayuda con esta tarea, consulte los artículos siguientes: 

   - [Comprender las opciones de configuración de próxima generación](mdb-next-gen-configuration-settings.md)   
   - [Configuración del firewall](mdb-firewall.md)

   Después de especificar la configuración de protección de próxima generación, elija **Siguiente**.

8. En la **pestaña Revisar la directiva** , revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Realice los cambios necesarios seleccionando **Editar**.
   - Cuando esté listo para continuar, elija **Actualizar directiva**.

## <a name="create-a-new-policy"></a>Crear una nueva directiva

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente**) y el tipo de directiva (como la **protección de última** generación **y firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes**) y, a continuación, revise la lista de directivas **de protección de próxima** generación. 

4. En **Protección de última generación** o **Firewall**, seleccione **+ Agregar**.

5. En la **pestaña Información general** , siga estos pasos:

   1. Especifique un nombre y una descripción. Esta información le ayudará a usted y a su equipo a identificar la directiva más adelante.
   2. Revise el orden de la directiva y edéclo si es necesario. (Para obtener más información, vea [Policy order](mdb-policy-order.md)).)
   3. Elija **Siguiente**. 

7. En la **pestaña Grupos de** dispositivos, crea un nuevo grupo de dispositivos o usa un grupo existente. Las directivas se asignan a dispositivos a través de grupos de dispositivos. Estos son algunos aspectos a tener en cuenta:

   - Inicialmente, es posible que solo tenga el grupo de dispositivos predeterminado, que incluye los dispositivos que los usuarios de su organización usan para tener acceso a los datos y el correo electrónico de la organización. Puedes conservar y usar el grupo de dispositivos predeterminado.
   - Crea un nuevo grupo de dispositivos para aplicar una directiva con una configuración específica que sea diferente de la directiva predeterminada. 
   - Cuando configuras el grupo de dispositivos, especificas determinados criterios, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que los excluyas. 
   - Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y personalizados que definas, se almacenan en Azure Active Directory (Azure AD).

   Para obtener más información sobre los grupos de dispositivos, consulta [Grupos de dispositivos en Defender para empresas](mdb-create-edit-device-groups.md).

8. En la **pestaña Configuración** , especifique la configuración de la directiva y, a continuación, elija **Siguiente**. Para obtener más información acerca de las opciones individuales, consulta [Configuración de Microsoft Defender para empresas](mdb-next-gen-configuration-settings.md).

9. En la **pestaña Revisar la directiva** , revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Realice los cambios necesarios seleccionando **Editar**.
   - Cuando esté listo para continuar, elija **Crear directiva**.


## <a name="next-steps"></a>Siguientes pasos

Elija una o varias de las siguientes tareas:

- [Administrar dispositivos](mdb-manage-devices.md)

- [Crear una nueva directiva en Microsoft Defender para empresas](mdb-create-new-policy.md)

- [Ver y administrar incidentes en Microsoft Defender para empresas](mdb-view-manage-incidents.md)

- [Responder y mitigar amenazas en Microsoft Defender para empresas](mdb-respond-mitigate-threats.md)

- [Revisar acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)