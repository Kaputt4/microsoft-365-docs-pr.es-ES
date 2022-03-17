---
title: Ver o editar directivas de protección de dispositivos
description: Ver, editar, crear y eliminar directivas de protección de dispositivos en Microsoft 365 Empresa Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/08/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: ba322493b3900c099ab5525f052604604ef0ac23
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525268"
---
# <a name="view-and-edit-your-device-protection-policies"></a>Ver y editar las directivas de protección de dispositivos

En Microsoft 365 Empresa Premium, la configuración de seguridad de los dispositivos administrados se configura a través de directivas de protección de dispositivos. Para simplificar la configuración y la experiencia de configuración, tienes directivas preconfiguradas que pueden ayudar a proteger los dispositivos de la organización tan pronto como se incorpore. Puede usar las directivas predeterminadas, editar directivas o crear sus propias directivas.

**En este artículo se describe cómo**:

- Obtener información general sobre las directivas predeterminadas
- Ver las directivas existentes
- Editar una directiva existente
- Crear una nueva directiva

## <a name="default-device-protection-policies"></a>Directivas predeterminadas de protección de dispositivos

Microsoft 365 Empresa Premium incluye dos tipos principales de directivas para proteger los dispositivos de la organización:

- **Directivas de protección de próxima generación**, que determinan cómo se configuran Antivirus de Microsoft Defender y otras características de protección contra amenazas

- **Directivas de firewall**, que determinan qué tráfico de red puede fluir desde y hacia los dispositivos de la organización

Estas directivas forman parte de Microsoft Defender para empresas, que se incluye en la Microsoft 365 Empresa Premium suscripción.

## <a name="view-your-existing-device-protection-policies"></a>Ver las directivas de protección de dispositivos existentes

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente**) y el tipo de directiva (como la **protección de última** generación **y firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes**) y, a continuación, revise la lista de directivas  en las categorías Protección de próxima generación y **Firewall**. 

4. Para ver más detalles sobre una directiva, seleccione su nombre. Se abrirá un panel lateral que proporciona más información sobre esa directiva, como qué dispositivos están protegidos por esa directiva.

## <a name="edit-an-existing-device-protection-policy"></a>Editar una directiva de protección de dispositivos existente

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente**) y el tipo de directiva (como la **protección de última** generación **y firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes**) y, a continuación, revise la lista de directivas  en las categorías Protección de próxima generación y **Firewall**. 

4. Para editar una directiva, seleccione su nombre y, a continuación, elija **Editar**.

5. En la **pestaña Información general** , revise la información. Si es necesario, puede editar la descripción. A continuación, elija **Siguiente**.

6. En la **pestaña Grupos de dispositivos** , determine qué grupos de dispositivos deben recibir esta directiva.  

   - Para mantener el grupo de dispositivos seleccionado tal como está, elija **Siguiente**.
   - Para quitar un grupo de dispositivos de la directiva, selecciona **Quitar**.
   - Para configurar un nuevo grupo de dispositivos, selecciona **Crear nuevo grupo** y, a continuación, configura el grupo de dispositivos. (Para obtener ayuda con esta tarea, consulta [Grupos de dispositivos en Microsoft 365 Empresa Premium](m365bp-device-groups-mdb.md)).)
   - Para aplicar la directiva a otro grupo de dispositivos, selecciona **Usar grupo existente**.

   Después de especificar qué grupos de dispositivos deben recibir la directiva, elija **Siguiente**.

7. En la **pestaña Configuración** , revise la configuración. Si es necesario, puede editar la configuración de la directiva. Para obtener ayuda con esta tarea, consulte los artículos siguientes: 

   - [Comprender las opciones de configuración de próxima generación](../security/defender-business/mdb-next-gen-configuration-settings.md)   
   - [Configuración del firewall](../security/defender-business/mdb-firewall.md)

   Después de especificar la configuración de protección de próxima generación, elija **Siguiente**.

8. En la **pestaña Revisar la directiva** , revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Realice los cambios necesarios seleccionando **Editar**.
   - Cuando esté listo para continuar, elija **Actualizar directiva**.

## <a name="create-a-new-device-protection-policy"></a>Crear una nueva directiva de protección de dispositivos

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por el sistema operativo (como **Windows cliente**) y el tipo de directiva (como la **protección de última** generación **y firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **Windows clientes**) y, a continuación, revise la lista de directivas **de protección de próxima** generación. 

4. En **Protección de última generación** o **Firewall**, seleccione **+ Agregar**.

5. En la **pestaña Información general** , siga estos pasos:

   1. Especifique un nombre y una descripción. Esta información le ayudará a usted y a su equipo a identificar la directiva más adelante.
   2. Revise el orden de la directiva y edéclo si es necesario. (Para obtener más información, vea [Policy order](../security/defender-business/mdb-policy-order.md)).)
   3. Elija **Siguiente**. 

7. En la **pestaña Grupos de** dispositivos, crea un nuevo grupo de dispositivos o usa un grupo existente. Las directivas se asignan a dispositivos a través de grupos de dispositivos. Estos son algunos aspectos a tener en cuenta:

   - Inicialmente, es posible que solo tenga el grupo de dispositivos predeterminado, que incluye los dispositivos que los usuarios de su organización usan para tener acceso a los datos y el correo electrónico de la organización. Puedes conservar y usar el grupo de dispositivos predeterminado.
   - Crea un nuevo grupo de dispositivos para aplicar una directiva con una configuración específica que sea diferente de la directiva predeterminada. 
   - Cuando configuras el grupo de dispositivos, especificas determinados criterios, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que los excluyas. 
   - Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y personalizados que definas, se almacenan en Azure Active Directory (Azure AD).

   Para obtener más información sobre los grupos de dispositivos, consulta [Grupos de dispositivos en Microsoft Defender para empresas](../security/defender-business/mdb-create-edit-device-groups.md).

8. En la **pestaña Configuración** , especifique la configuración de la directiva y, a continuación, elija **Siguiente**. Para obtener más información acerca de la configuración individual, consulte [Understand next-generation configuration settings in Microsoft Defender for Business](../security/defender-business/mdb-next-gen-configuration-settings.md).

9. En la **pestaña Revisar la directiva** , revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Realice los cambios necesarios seleccionando **Editar**.
   - Cuando esté listo para continuar, elija **Crear directiva**.


## <a name="next-steps"></a>Siguientes pasos

[Grupos de dispositivos en Microsoft 365 Empresa Premium](m365bp-device-groups-mdb.md)