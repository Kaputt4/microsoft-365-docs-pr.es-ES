---
title: Ver o editar directivas en Microsoft Defender para Empresas
description: Obtenga información sobre cómo ver, editar, crear y eliminar directivas de ciberseguridad en Defender para empresas. Proteja los dispositivos con directivas de seguridad.
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
ms.openlocfilehash: c5606c19e4cef64e701d34a5e4ccc2143f51f394
ms.sourcegitcommit: 66228a5506fdceb4cbf0d55b9de3f2943740134f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "66090374"
---
# <a name="view-or-edit-policies-in-microsoft-defender-for-business"></a>Ver o editar directivas en Microsoft Defender para Empresas

En Microsoft Defender para Empresas, la configuración de seguridad se configura mediante directivas que se aplican a los dispositivos. Para simplificar la experiencia de configuración y configuración, Defender for Business incluye directivas preconfiguradas para ayudar a proteger los dispositivos de su empresa en cuanto se incorporan. Puede usar las directivas predeterminadas, editar directivas o crear sus propias directivas.

**En este artículo se describe cómo**:

- [Obtener información general de las directivas predeterminadas](#default-policies-in-defender-for-business)
- [Ver las directivas existentes](#view-your-existing-policies)
- [Editar una directiva existente](#edit-an-existing-policy)
- [Crear una nueva directiva](#create-a-new-policy)


## <a name="default-policies-in-defender-for-business"></a>Directivas predeterminadas en Defender para empresas

En Defender para empresas, hay dos tipos principales de directivas para proteger los dispositivos de su empresa:

- **Directivas de protección de última generación**, que determinan la configuración de Antivirus de Microsoft Defender y otras características de protección contra amenazas
- **Directivas de firewall**, que determinan qué tráfico de red puede fluir hacia y desde los dispositivos de la empresa


## <a name="view-your-existing-policies"></a>Ver las directivas existentes

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo (como **Cliente de Windows**) y por tipo de directiva (como **Protección de última generación** y **Firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas en las categorías **Protección de última generación** y **Firewall**. 

4. Para ver más detalles sobre una directiva, seleccione su nombre. Se abre un panel lateral que proporciona más información sobre la directiva, por ejemplo, qué dispositivos están protegidos por esa directiva.

## <a name="edit-an-existing-policy"></a>Editar una directiva existente

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo (como **Cliente de Windows**) y por tipo de directiva (como **Protección de última generación** y **Firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas en las categorías **Protección de última generación** y **Firewall**. 

4. Para editar una directiva, seleccione su nombre y, a continuación, elija **Editar**.

5. En la pestaña **Información general**, revise la información. Si es necesario, puede editar la descripción. A continuación, elija **Siguiente**.

6. En la pestaña **Grupos de dispositivos**, determine qué grupos de dispositivos deben recibir esta directiva.  

   - Para dejar el grupo de dispositivos seleccionado tal y como está, elija **Siguiente**.
   - Para quitar un grupo de dispositivos de la directiva, seleccione **Quitar**.
   - Para configurar un nuevo grupo de dispositivos, seleccione **Crear nuevo grupo** y, a continuación, configure el grupo de dispositivos. (Para obtener ayuda con esta tarea, consulte [Grupos de dispositivos en Microsoft Defender para Empresas](mdb-create-edit-device-groups.md)).
   - Para aplicar la directiva a otro grupo de dispositivos, seleccione **Usar grupo existente**.

   Después de especificar qué grupos de dispositivos deben recibir la directiva, elija **Siguiente**.

7. En la pestaña **Opciones de configuración**, revise la configuración. Si es necesario, puede editar la configuración de la directiva. Para obtener ayuda con esta tarea, consulte los artículos siguientes: 

   - [Comprender las opciones de configuración de última generación](mdb-next-gen-configuration-settings.md)   
   - [Configuración de firewall](mdb-firewall.md)

   Una vez que haya especificado las opciones de configuración de protección de última generación, elija **Siguiente**.

8. En la pestaña **Revisar la directiva**, revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Si necesita realizar cambios, seleccione **Editar**.
   - Cuando esté listo para continuar, elija **Actualizar directiva**.

## <a name="create-a-new-policy"></a>Crear una nueva directiva

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo (como **Cliente de Windows**) y por tipo de directiva (como **Protección de última generación** y **Firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas de **Protección de última generación**. 

4. En **Protección de última generación** o **Firewall**, seleccione **+ Agregar**.

5. En la pestaña **Información general**, siga estos pasos:

   1. Especifique un nombre y una descripción. Esta información le ayudará a usted y a los miembros de su equipo a identificarla más adelante.
   2. Revise el orden de la directiva y edítelo si fuera necesario. (Para obtener más información, consulte [Orden de directiva](mdb-policy-order.md)).
   3. Elija **Siguiente**. 

7. En la pestaña **Grupos de dispositivos**, cree un nuevo grupo de dispositivos o use un grupo existente. Las directivas se asignan a los dispositivos a través de grupos de dispositivos. Estos son algunos aspectos que debe tener en cuenta:

   - Inicialmente, es posible que solo tenga el grupo de dispositivos predeterminado, que incluye los dispositivos que usan los usuarios de su empresa para acceder a los datos y el correo electrónico de la empresa. Puede conservar y usar el grupo de dispositivos predeterminado.
   - Cree un nuevo grupo de dispositivos para aplicar una directiva con una configuración específica que sea diferente de la directiva predeterminada. 
   - Al configurar el grupo de dispositivos, se especifican determinados criterios, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que se excluyan. 
   - Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y personalizados que defina, se almacenan en Azure Active Directory (Azure AD).

   Para más información sobre los grupos de dispositivos, consulte [Grupos de dispositivos en Defender para empresas](mdb-create-edit-device-groups.md).

8. En la pestaña **Opciones de configuración**, especifique la configuración de la directiva y, a continuación, elija **Siguiente**. Para obtener más información sobre la configuración individual, consulte [Configuración para Microsoft Defender para Empresas](mdb-next-gen-configuration-settings.md).

9. En la pestaña **Revisar la directiva**, revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Si necesita realizar cambios, seleccione **Editar**.
   - Cuando esté listo para continuar, elija **Crear directiva**.


## <a name="next-steps"></a>Pasos siguientes

Elija una o varias de las siguientes tareas:

- [Administrar dispositivos](mdb-manage-devices.md)
- [Creación de una nueva directiva en Microsoft Defender para Empresas](mdb-create-new-policy.md)
- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)