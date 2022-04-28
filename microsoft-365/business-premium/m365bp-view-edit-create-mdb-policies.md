---
title: Ver o editar directivas de protección de dispositivos
description: Ver, editar, crear y eliminar directivas de protección de dispositivos en Microsoft 365 Empresa Premium
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/14/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 816b425fbbd511b68d2c21f313b497bbd4b77f8a
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65087055"
---
# <a name="view-and-edit-your-device-protection-policies"></a>Ver y editar las directivas de protección de dispositivos

En Microsoft 365 Empresa Premium, la configuración de seguridad de los dispositivos administrados se realiza mediante directivas de protección de dispositivos. Para simplificar la experiencia de configuración, existen directivas preconfiguradas que ayudan a proteger los dispositivos de la organización en cuanto se incorporan. Use las directivas predeterminadas, edite las directivas existentes o cree sus propias directivas.

**Esta guía indica cómo**:

- Obtener información general de las directivas predeterminadas
- Ver las directivas existentes
- Editar una directiva existente
- Crear una nueva directiva

## <a name="default-device-protection-policies"></a>Directivas de protección de dispositivos predeterminadas

Microsoft 365 Empresa Premium incluye dos tipos principales de directivas para proteger los dispositivos de la organización:

- **Directivas de protección de última generación**, que determinan la configuración de Antivirus de Microsoft Defender y otras características de protección contra amenazas

- **Directivas de firewall**, que determinan el tráfico de red que puede fluir hacia y desde los dispositivos de la organización

Estas directivas forman parte de Microsoft Defender para Empresas, que se incluye en la suscripción de Microsoft 365 Empresa Premium.

## <a name="view-your-existing-device-protection-policies"></a>Ver las directivas de protección existentes de los dispositivos

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo (por ejemplo, **cliente de Windows**) y por tipo de directiva (por ejemplo, **protección de última generación** y **Firewall**). 

    :::image type="content" source="../media/mdb-deviceconfiguration.png" lightbox="../media/mdb-deviceconfiguration.png" alt-text="Página Configuración del dispositivo.":::

3. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas en las categorías **Protección de última generación** y **Firewall**. 

4. Para ver más detalles sobre una directiva, seleccione su nombre. Se abre un panel lateral que proporciona más información sobre la directiva, por ejemplo, qué dispositivos están protegidos por esa directiva.

   :::image type="content" source="../media/mdb-deviceconfig-selectedpolicy.png" lightbox="../media/mdb-deviceconfig-selectedpolicy.png" alt-text="Captura de pantalla de una directiva seleccionada en la página Configuración del dispositivo.":::

## <a name="edit-an-existing-device-protection-policy"></a>Editar una directiva existente de protección de dispositivos

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo (por ejemplo, **cliente de Windows**) y por tipo de directiva (por ejemplo, **protección de última generación** y **Firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas en las categorías **Protección de última generación** y **Firewall**. 

4. Para editar una directiva, seleccione su nombre y, a continuación, elija **Editar**.

5. En la pestaña **Información general**, revise la información. Si es necesario, puede editar la descripción. A continuación, elija **Siguiente**.

6. En la pestaña **Grupos de dispositivos**, determine qué grupos de dispositivos deben recibir esta directiva.  

   - Para dejar el grupo de dispositivos seleccionado tal y como está, elija **Siguiente**.
   - Para quitar un grupo de dispositivos de la directiva, seleccione **Quitar**.
   - Para configurar un nuevo grupo de dispositivos, seleccione **Crear nuevo grupo** y, a continuación, configure el grupo de dispositivos. (Para obtener ayuda con esta tarea, consulte [Grupos de dispositivos en Microsoft 365 Empresa Premium](m365bp-device-groups-mdb.md)).
   - Para aplicar la directiva a otro grupo de dispositivos, seleccione **Usar grupo existente**.

   Después de especificar qué grupos de dispositivos deben recibir la directiva, elija **Siguiente**.

7. En la pestaña **Opciones de configuración**, revise la configuración. Si es necesario, puede editar la configuración de la directiva. Para obtener ayuda con esta tarea, consulte los artículos siguientes: 

   - [Comprender las opciones de configuración de última generación](../security/defender-business/mdb-next-gen-configuration-settings.md)   
   - [Configuración de firewall](../security/defender-business/mdb-firewall.md)

   Una vez que haya especificado las opciones de configuración de protección de última generación, elija **Siguiente**.

8. En la pestaña **Revisar la directiva**, revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Si necesita realizar cambios, seleccione **Editar**.
   - Cuando esté listo para continuar, elija **Actualizar directiva**.

## <a name="create-a-new-device-protection-policy"></a>Crear una nueva directiva de protección de dispositivos

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión. 

2. En el panel de navegación, elija **Configuración del dispositivo**. Las directivas se organizan por sistema operativo (por ejemplo, **cliente de Windows**) y por tipo de directiva (por ejemplo, **protección de última generación** y **Firewall**). 

3. Seleccione una pestaña del sistema operativo (por ejemplo, **clientes de Windows**) y, a continuación, revise la lista de directivas de **Protección de última generación**. 

4. En **Protección de última generación** o **Firewall**, seleccione **+ Agregar**.

5. En la pestaña **Información general**, siga estos pasos:

   1. Especifique un nombre y una descripción. Esta información le ayudará a usted y a su equipo a identificar la directiva más adelante.
   2. Revise el orden de la directiva y edítelo si fuera necesario. (Para obtener más información, consulte [Orden de directiva](../security/defender-business/mdb-policy-order.md)).
   3. Elija **Siguiente**. 

7. En la pestaña **Grupos de dispositivos**, cree un nuevo grupo de dispositivos o use un grupo existente. Las directivas se asignan a los dispositivos a través de grupos de dispositivos. Estos son algunos aspectos que debe tener en cuenta:

   - Inicialmente, es posible que solo tenga el grupo de dispositivos predeterminado, que incluye los dispositivos que usan los usuarios de la organización para acceder a los datos y al correo electrónico de la organización. Puede conservar y usar el grupo de dispositivos predeterminado.
   - Cree un nuevo grupo de dispositivos para aplicar una directiva con una configuración específica que sea diferente de la directiva predeterminada. 
   - Al configurar el grupo de dispositivos, se especifican determinados criterios, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que se excluyan. 
   - Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y personalizados que defina, se almacenan en Azure Active Directory (Azure AD).

   Para más información sobre los grupos de dispositivos, consulte [Grupos de dispositivos en Microsoft Defender para Empresas](../security/defender-business/mdb-create-edit-device-groups.md).

8. En la pestaña **Opciones de configuración**, especifique la configuración de la directiva y, a continuación, elija **Siguiente**. Para obtener más información sobre la configuración individual, consulte [Comprender las opciones de configuración de última generación en Microsoft Defender para Empresas](../security/defender-business/mdb-next-gen-configuration-settings.md).

9. En la pestaña **Revisar la directiva**, revise la información general, los dispositivos de destino y las opciones de configuración. 

   - Si necesita realizar cambios, seleccione **Editar**.
   - Cuando esté listo para continuar, elija **Crear directiva**.

## <a name="next-objective"></a>Siguiente objetivo

Configurar y administrar [grupos de dispositivos](m365bp-device-groups-mdb.md).

