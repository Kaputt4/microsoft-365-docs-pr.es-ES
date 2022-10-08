---
title: Trabajar con grupos de dispositivos en Microsoft 365 Empresa Premium
description: Obtenga información sobre los grupos de dispositivos y cómo aplicar directivas con Intune en Microsoft 365 Empresa Premium y aumente la protección contra ciberataques.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: high
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- tier1
ms.openlocfilehash: e32e315808a6ef240d9d1d3ab3b80fd19896fe07
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097542"
---
# <a name="device-groups-and-categories-in-microsoft-365-business-premium"></a>Grupos de dispositivos y categorías en Microsoft 365 Empresa Premium

Microsoft 365 Empresa Premium incluye protección de puntos de conexión a través de Microsoft Defender para Empresas y Microsoft Intune Las directivas de protección de dispositivos se aplican a los dispositivos a través de determinadas colecciones denominadas grupos de dispositivos. En Intune, los dispositivos se agrupan en categorías de dispositivos como una forma diferente de organizarlos. 

En este artículo se incluyen las siguientes secciones:  

- [Trabajar con grupos de dispositivos](#working-with-device-groups)
- [Cómo crear un nuevo grupo de dispositivos](#create-a-device-group-in-the-microsoft-365-defender-portal)
- [Cómo crear una nueva categoría de dispositivos en Intune](#create-a-device-category-in-intune)

## <a name="working-with-device-groups"></a>Trabajar con grupos de dispositivos

Un grupo de dispositivos es una colección de dispositivos que se agrupan debido a determinados criterios especificados, como la versión del sistema operativo. Los dispositivos que cumplen los criterios se incluyen en ese grupo de dispositivos, a menos que se excluyan.

Con Microsoft 365 Empresa Premium, tiene grupos de dispositivos predeterminados que puede usar. Los grupos de dispositivos predeterminados incluyen todos los dispositivos que se incorporan a Defender para Empresas. Sin embargo, también puede crear nuevos grupos de dispositivos para asignar directivas de protección de dispositivos con una configuración específica a determinados dispositivos.

Todos los grupos de dispositivos, incluidos los grupos de dispositivos predeterminados y los grupos de dispositivos personalizados que defina, se almacenan en [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD).

## <a name="create-a-device-group-in-the-microsoft-365-defender-portal"></a>Creación de un grupo de dispositivos en el portal de Microsoft 365 Defender

Puede crear un nuevo grupo de dispositivos mientras está creando o editando una directiva de protección de dispositivos.

1. Vaya al [portal de Microsoft 365 Defender](https://security.microsoft.com) e inicie sesión.

2. En el panel de navegación, elija **Configuración del dispositivo**.

3. Realice una de las acciones siguientes:

    1. Seleccione una directiva existente y, a continuación, elija **Editar**.

    2. Elija **+ Agregar** para crear una nueva directiva.

    > [!TIP]
    > Para obtener ayuda para crear o editar una directiva, vea [Ver o editar directivas en Microsoft Defender para Empresas](m365bp-view-edit-create-mdb-policies.md).

4. En el paso **Información general**, revise la información, edítela si es necesario y, a continuación, elija **Siguiente**.

5. Elija **Crear nuevo grupo**.

6. Especifique un nombre y una descripción para el grupo de dispositivos y, a continuación, elija **Siguiente**.

7. Seleccione los dispositivos que desea incluir en el grupo y, a continuación, elija **Crear grupo**.

8. En el paso **Grupos de dispositivos**, revise la lista de grupos de dispositivos de la directiva. Si es necesario, quite un grupo de la lista. A continuación, elija **Siguiente**.

9. En la página **Opciones de configuración**, revise y edite la configuración según sea necesario y, a continuación, elija **Siguiente**. Para obtener más información acerca de esta configuración, consulte [Comprender las opciones de configuración de última generación en Microsoft Defender para Empresas](../security/defender-business/mdb-next-gen-configuration-settings.md).

10. En el paso **Revisar la directiva**, revise toda la configuración, realice las modificaciones necesarias y, a continuación, elija **Crear directiva** o **Actualizar directiva**.

## <a name="create-a-device-category-in-intune"></a>Creación de una categoría de dispositivos en Intune

Cree categorías de dispositivos en Intune que los usuarios deben elegir cuando inscriban un dispositivo.

1. Inicie sesión en el [centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com).

2. Seleccione **Dispositivos** > **Categorías de dispositivo** > **Crear categoría de dispositivo** para agregar una nueva categoría.

3. En el panel **Crear categoría de dispositivos**, escriba un nombre para la nueva categoría y una descripción opcional.

4. Cuando haya terminado, seleccione **Crear**. Puede ver la nueva categoría en la lista.

Use el nombre de la categoría de dispositivos al crear grupos de seguridad de Azure Active Directory (Azure AD). Cuando los usuarios inscriben los dispositivos, se les presenta la lista de las categorías que ha configurado en Intune. Tras elegir una categoría y finalizar la inscripción, los dispositivos se agregan al grupo de seguridad de Active Directory asociado.

## <a name="create-dynamic-device-groups-in-azure-active-directory"></a>Creación de grupos de dispositivos dinámicos en Azure Active Directory

También puede entrar al portal de Azure Active Directory (Azure AD) ([https://portal.azure.com](https://portal.azure.com)) desde el centro de administración de Microsoft 365. En el centro de administración de Microsoft 365 ([https://admin.microsoft.com](https://admin.microsoft.com/)), elija **Todos los centros de administración** y, después, **Azure Active Directory**.

En el portal de Azure AD, puede crear grupos dinámicos basados en la categoría de dispositivo y el nombre de la categoría de dispositivo. Use reglas de grupo dinámicas para agregar y quitar dispositivos automáticamente. Si cambian los atributos de un dispositivo, el sistema examina las reglas de grupo dinámico del directorio para ver si el dispositivo cumple los requisitos de las reglas (se agrega) o ya no cumple los requisitos de las reglas (se quita).

Puede crear un grupo dinámico para dispositivos o para usuarios, pero no para ambos. Tampoco puede crear un grupo de dispositivos en función de los atributos de los propietarios de los dispositivos. Las reglas de pertenencia de los dispositivos solo pueden hacer referencia a las atribuciones de los dispositivos. 

## <a name="after-device-groups-are-created"></a>Después de crear grupos de dispositivos

Ahora que se han establecido categorías y grupos de dispositivos, los usuarios de dispositivos iOS y Android inscriben sus dispositivos y, a medida que lo hacen, deben elegir una categoría de la lista de categorías que se configuraron. Los usuarios de Windows pueden usar el sitio web del Portal de empresa o la aplicación Portal de empresa para seleccionar una categoría.

1. Después de inscribir el dispositivo, vaya al [portal de empresa](https://portal.microsoft.com) y elija **Mis dispositivos**.

2. Seleccione el dispositivo inscrito de la lista y, a continuación, seleccione una categoría.

Tras elegir una categoría, el dispositivo se agrega automáticamente al grupo correspondiente. Si ya hay un dispositivo inscrito antes de configurar las categorías, el usuario verá una notificación del dispositivo en el sitio web del Portal de empresa. De esta manera, el usuario sabrá que puede seleccionar una categoría la próxima vez que acceda a la aplicación Portal de empresa de iOS/iPadOS o Android.

> [!NOTE]
> - Puede editar una categoría de dispositivo en Azure Portal, pero debe actualizar manualmente los grupos de seguridad de Azure AD que hagan referencia a esta categoría.
> - Si elimina una categoría, los dispositivos asignados a esta mostrarán el nombre de la categoría **Sin asignar**.

## <a name="view-the-categories-of-devices-that-you-manage"></a>Ver las categorías de los dispositivos que administra

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), seleccione **Dispositivos** > **Todos los dispositivos**.

2. En la lista de dispositivos, examine la columna **Categoría de dispositivo**.

3. Si no se muestra la columna Categoría del dispositivo, seleccione **Columnas** > **Categoría** > **Aplicar**.

## <a name="change-the-category-of-a-device"></a>Cambiar la categoría de un dispositivo

1. Inicie sesión en el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), seleccione **Dispositivos** > **Todos los dispositivos**. 

2. Seleccione la categoría que desee de la lista para ver sus propiedades.

## <a name="next-steps"></a>Siguientes pasos

Ahora que ha completado las misiones principales, tómese su tiempo para configurar los [equipos de respuesta](m365bp-security-incident-management.md) y [mantener su entorno](m365bp-maintain-environment.md).
