---
title: Microsoft OneDrive
description: Cómo Escritorio administrado de Microsoft configurar OneDrive dispositivos inscritos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de línea de negocio, aplicaciones de LOB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904845"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Escritorio administrado de Microsoft usa [OneDrive para la Empresa](/onedrive/plan-onedrive-enterprise) como servicio de almacenamiento en la nube para todos los dispositivos Escritorio administrado de Microsoft para garantizar que los dispositivos son lo más sin estado posible. El usuario podrá encontrar sus archivos independientemente del dispositivo en el que inicie sesión. Por ejemplo, si reemplazas un dispositivo Escritorio administrado de Microsoft por uno nuevo, los archivos se sincronizarán automáticamente con el nuevo dispositivo.

Configuramos automáticamente estas opciones de configuración de forma predeterminada en dispositivos administrados de Microsoft:

- OneDrive se configura silenciosamente con la cuenta de usuario y se inicia sesión automáticamente (sin interacción del usuario) en la cuenta de usuario que se usó para iniciar sesión Windows. Para obtener más información, [vea Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)

- La característica Files-On-Demand está habilitada para que los usuarios puedan acceder a los archivos desde su almacenamiento en la nube en OneDrive sin tener que usar el espacio en disco innecesariamente. Para obtener más información, vea [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).

- La característica Mover carpeta conocida se habilita de forma silenciosa para hacer una copia de seguridad de los datos de los usuarios en la nube, lo que les da acceso a sus archivos desde cualquier dispositivo. Para obtener más información, vea [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).

- Los usuarios no pueden deshabilitar la característica Mover carpeta conocida ni cambiar la ubicación de las carpetas conocidas para garantizar una experiencia coherente en Escritorio administrado de Microsoft dispositivos.

## <a name="user-experience"></a>Experiencia del usuario

Cuando Escritorio administrado de Microsoft usuarios reciben un nuevo dispositivo, pasan por una experiencia de primera ejecución especificando sus credenciales de Azure al configurar el dispositivo. Una vez completado este proceso, pueden acceder a su escritorio y tener la OneDrive experiencia.

1. El sistema indica a los usuarios OneDrive se han configurado y que han iniciado sesión automáticamente en OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="La lectura de notificaciones que ahora está sincronizando OneDrive y puede editar archivos en OneDrive. haga clic aquí para ver los archivos":::

2. El sistema indica a los usuarios OneDrive se ha configurado el movimiento de carpetas conocidos para ellos.

:::image type="content" source="media/onedrive-folders.png" alt-text="Notificación en la que el departamento de TI ha copiado de seguridad de las carpetas importantes. Las carpetas ahora se copian de seguridad OneDrive y están disponibles desde otros dispositivos":::

3. Para evitar iconos duplicados en el escritorio cuando los dispositivos se restablecen o se restablecen, el sistema quita automáticamente Microsoft Edge y Microsoft Teams iconos de la sincronización de OneDrive, como se muestra en esta vista en el Explorador de archivos.

:::image type="content" source="media/onedrive-teams.png" alt-text="Explorador de archivos que muestra Teams y listas perimetrales con casillas desactivadas y texto activando la lectura Excluido de la sincronización.":::


## <a name="onedrive-sync-restrictions"></a>OneDrive de sincronización

Si necesita restringir la sincronización OneDrive, se recomienda controlar el acceso con una Azure Active Directory de acceso condicional. Para obtener más información, consulta [Habilitar la compatibilidad con acceso condicional en la OneDrive de sincronización.](/onedrive/enable-conditional-access)

Si no puede usar una directiva de acceso condicional de Azure AD en su organización, el administrador de TI debe seguir estos pasos:

1. Si aún no lo sabe, busque su identificador de inquilino, tal como se describe en [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).
2. Inicie sesión en el centro OneDrive administración y, a continuación, **seleccione Sincronizar** en el panel izquierdo. Active la **casilla Permitir la sincronización solo** en equipos unidos a dominios específicos y, a continuación, agregue el identificador de inquilino a la lista de dominios. Para obtener más información, vea [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).

> [!NOTE]
> Esta guía solo se aplica a los inquilinos de Escritorio administrado de Microsoft. Hay otras opciones de configuración en uso que no se debatieron en este artículo.