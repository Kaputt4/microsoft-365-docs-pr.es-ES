---
title: Grupos de dispositivos en Microsoft Defender para Empresas
description: Obtenga información sobre los grupos de dispositivos en Microsoft Defender para Empresas
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 04/12/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 6c02a92132f7f5249f2ba67ca2841902b889d52b
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "64861753"
---
# <a name="device-groups-in-microsoft-defender-for-business"></a>Grupos de dispositivos en Microsoft Defender para Empresas

> [!NOTE]
> Microsoft Defender para Empresas ahora se incluye en [Microsoft 365 Empresa Premium](../../business-premium/index.md). 

En Microsoft Defender para Empresas, las directivas se aplican a los dispositivos a través de ciertas colecciones que se denominan grupos de dispositivos. 

**En este artículo se describe lo siguiente**:  

- [Qué son los grupos de dispositivos](#what-is-a-device-group)   
- [Creación de grupos de dispositivos en Defender para empresas](#create-a-new-device-group)
- [Visualización de un grupo de dispositivos existente](#view-an-existing-device-group)
- [Qué hace la opción Agregar todos los dispositivos](#what-does-the-add-all-devices-option-do)

>
> **¿Tiene un minuto?**
> Realice nuestra <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">breve encuesta sobre seguridad</a>. Nos encantaría conocer su opinión.
>

## <a name="what-is-a-device-group"></a>¿Qué es un grupo de dispositivos?

Un grupo de dispositivos es una colección de dispositivos que se agrupan debido a determinados criterios especificados, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que los excluya. En Microsoft Defender para Empresas, las directivas se aplican a los dispositivos mediante grupos de dispositivos.

Defender for Business incluye grupos de dispositivos predeterminados que puede usar. Los grupos de dispositivos predeterminados incluyen todos los dispositivos incorporados a Defender for Business. Por ejemplo, hay un grupo de dispositivos predeterminado para Windows dispositivos. Cada vez que incorpore Windows dispositivos, se agregan automáticamente al grupo de dispositivos predeterminado.

También puede crear nuevos grupos de dispositivos para asignar directivas con una configuración específica a determinados dispositivos. Por ejemplo, puede tener una directiva de firewall asignada a un conjunto de dispositivos Windows y una directiva de firewall diferente asignada a otro conjunto de dispositivos Windows. Puede definir grupos de dispositivos específicos para usarlos con las directivas.

> [!NOTE]
> Al crear directivas en Defender para empresas, se asigna un orden de prioridad. Si aplica varias directivas a un conjunto determinado de dispositivos, estos solo recibirán la primera directiva aplicada. Para obtener más información, consulte [Descripción del orden de la directiva en Microsoft Defender para Empresas](mdb-policy-order.md).

Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y los grupos de dispositivos personalizados que defina, se almacenan en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD).

## <a name="create-a-new-device-group"></a>Creación de un nuevo grupo de dispositivos

Actualmente, en Defender para empresas, puede crear un nuevo grupo de dispositivos mientras está en proceso de crear o editar una directiva, como se describe en el procedimiento siguiente: 

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración del dispositivo**. 

3. Realice una de las siguientes acciones:

    1. Seleccione una directiva existente y, a continuación, elija **Editar**.
    2. Elija **+ Agregar** para crear una nueva directiva.

    > [!TIP]
    > Para obtener ayuda para crear o editar una directiva, consulte [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-policies.md).

4. En el paso **Información general** , revise la información, edite si es necesario y, a continuación, elija **Siguiente**.

5. Elija **+ Crear nuevo grupo**. 

6. Especifique un nombre y una descripción para el grupo de dispositivos y, a continuación, elija **Siguiente**.

7. Seleccione los dispositivos que se van a incluir en el grupo y, a continuación, elija **Crear grupo**.

8. En el paso **Grupos de dispositivos** , revise la lista de grupos de dispositivos de la directiva. Si es necesario, quite un grupo de la lista. A continuación, elija **Siguiente**.

9. En la página **Configuración** , revise y edite la configuración según sea necesario y, a continuación, elija **Siguiente**. Para obtener más información sobre estas opciones, consulte [Configuración](mdb-next-gen-configuration-settings.md).

10. En el paso **Revisar la directiva** , revise toda la configuración, realice las modificaciones necesarias y, a continuación, elija **Crear directiva** o **Actualizar directiva**.

## <a name="view-an-existing-device-group"></a>Visualización de un grupo de dispositivos existente

Actualmente, en Defender para empresas, puede ver los grupos de dispositivos existentes mientras está en proceso de crear o editar una directiva, como se describe en el procedimiento siguiente: 

1. Vaya al portal de Microsoft 365 Defender ([https://security.microsoft.com](https://security.microsoft.com)) e inicie sesión.

2. En el panel de navegación, elija **Configuración del dispositivo**. 

3. Realice una de las siguientes acciones:

    1. Seleccione una directiva existente y, a continuación, elija **Editar**.
    2. Elija **+ Agregar** para crear una nueva directiva.

    > [!TIP]
    > Para obtener ayuda para crear o editar una directiva, consulte [Ver o editar directivas en Microsoft Defender para Empresas](mdb-view-edit-policies.md).

4. En el paso **Información general** , revise la información, edite si es necesario y, a continuación, elija **Siguiente**.

5. Elija **Usar grupo existente**. Se abre un control flotante y muestra los grupos de dispositivos. Si aún no tiene ningún grupo de dispositivos, se le pedirá que cree un nuevo grupo de dispositivos.

## <a name="what-does-the-add-all-devices-option-do"></a>¿Qué hace la opción Agregar todos los dispositivos?

Al crear o editar una directiva, es posible que vea la opción **Agregar todos los dispositivos** .

:::image type="content" source="media/add-all-devices-option.png" alt-text="Captura de pantalla de la opción Agregar todos los dispositivos.":::

Si selecciona esta opción, todos los dispositivos inscritos en Microsoft Endpoint Manager (lo que incluye Microsoft Intune) recibirán la directiva que está creando o editando de forma predeterminada. 

## <a name="next-steps"></a>Siguientes pasos

Elija una o varias de las siguientes tareas:

- [Ver o editar directivas](mdb-view-edit-policies.md)
- [Crear una nueva directiva](mdb-create-new-policy.md)
- [Visualización y administración de incidentes en Microsoft Defender para Empresas](mdb-view-manage-incidents.md)
- [Respuesta y mitigación de amenazas en Microsoft Defender para Empresas](mdb-respond-mitigate-threats.md)
- [Revisión de las acciones de corrección en el Centro de acciones](mdb-review-remediation-actions.md)