---
title: Microsoft OneDrive
description: Cómo Microsoft Managed Desktop configura OneDrive para dispositivos inscritos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones lob
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

Microsoft Managed Desktop usa [OneDrive para](/onedrive/plan-onedrive-enterprise) la Empresa como servicio de almacenamiento en la nube para todos los dispositivos de Escritorio administrado de Microsoft para asegurarse de que los dispositivos son lo más sin estado posible. El usuario podrá encontrar sus archivos independientemente del dispositivo en el que inicie sesión. Por ejemplo, si reemplazas un dispositivo de Escritorio administrado de Microsoft por uno nuevo, los archivos se sincronizarán automáticamente con el nuevo dispositivo.

Configuramos automáticamente estas opciones de configuración de forma predeterminada en dispositivos administrados de Microsoft:

- OneDrive se configura silenciosamente con la cuenta de usuario e inicia sesión automáticamente (sin interacción del usuario) en la cuenta de usuario que se usó para iniciar sesión en Windows. Para obtener más información, vea [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)

- La característica Files-On-Demand está habilitada para que los usuarios puedan acceder a los archivos desde su almacenamiento en la nube en OneDrive sin tener que usar el espacio en disco innecesariamente. Para obtener más información, consulta [Guardar espacio en disco con Archivos de OneDrive a petición para Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).

- La característica Mover carpeta conocida se habilita de forma silenciosa para hacer una copia de seguridad de los datos de los usuarios en la nube, lo que les da acceso a sus archivos desde cualquier dispositivo. Para obtener más información, vea [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).

- Los usuarios no pueden deshabilitar la característica Mover carpeta conocida ni cambiar la ubicación de las carpetas conocidas para garantizar una experiencia coherente en todos los dispositivos de Escritorio administrado de Microsoft.

## <a name="user-experience"></a>Experiencia del usuario

Cuando los usuarios de Escritorio administrado de Microsoft reciben un nuevo dispositivo, pasan por una experiencia de primera ejecución especificando sus credenciales de Azure al configurar el dispositivo. Una vez completado este proceso, pueden acceder a su escritorio y tener la experiencia de OneDrive.

1. El sistema indica a los usuarios que OneDrive se ha configurado y que han iniciado sesión automáticamente en OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="La lectura de notificaciones ahora está sincronizando OneDrive y puede editar archivos en OneDrive. haga clic aquí para ver los archivos":::

2. El sistema indica a los usuarios que oneDrive Known Folder Move se ha configurado para ellos.

:::image type="content" source="media/onedrive-folders.png" alt-text="Notificación en la que el departamento de TI ha copiado de seguridad de las carpetas importantes. Las carpetas ahora se copian de seguridad en OneDrive y están disponibles desde otros dispositivos":::

3. Para evitar iconos duplicados en el escritorio cuando los dispositivos se restablecen o se restablecen, el sistema quita automáticamente los iconos de Microsoft Edge y Microsoft Teams de la sincronización de OneDrive, como se muestra en esta vista en el Explorador de archivos.

:::image type="content" source="media/onedrive-teams.png" alt-text="Explorador de archivos que muestra las listas de Teams y Edge con las casillas desactivadas y la lectura de texto activada Excluido de la sincronización.":::


## <a name="onedrive-sync-restrictions"></a>Restricciones de sincronización de OneDrive

Si necesita restringir la sincronización de OneDrive, le recomendamos que controle el acceso con una directiva de acceso condicional de Azure Active Directory. Para obtener más información, vea [Enable conditional access support in the OneDrive sync app](/onedrive/enable-conditional-access).

Si no puede usar una directiva de acceso condicional de Azure AD en su organización, el administrador de TI debe seguir estos pasos:

1. Si aún no lo sabe, busque su identificador de inquilino, como se describe en Buscar el identificador de inquilino de [Microsoft 365](/onedrive/find-your-office-365-tenant-id).
2. Inicie sesión en el Centro de administración de OneDrive y, a continuación, **seleccione Sincronizar** en el panel izquierdo. Active la **casilla Permitir la sincronización solo** en equipos unidos a dominios específicos y, a continuación, agregue el identificador de inquilino a la lista de dominios. Para obtener más información, vea [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).

> [!NOTE]
> Esta guía solo se aplica a los inquilinos de Microsoft Managed Desktop. Hay otras opciones de configuración en uso que no se debatieron en este artículo.