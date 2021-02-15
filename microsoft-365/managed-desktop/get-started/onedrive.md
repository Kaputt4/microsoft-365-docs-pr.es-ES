---
title: Microsoft OneDrive
description: Cómo el Escritorio administrado de Microsoft configura OneDrive para dispositivos inscritos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de LÍNEA DEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 6cd2c993e0ca9d4c456a2914b866b65b59799afa
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233952"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Escritorio administrado de Microsoft usa [OneDrive](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise) para la Empresa como servicio de almacenamiento en la nube para todos los dispositivos de Escritorio administrado de Microsoft para garantizar que los dispositivos son lo más sin estado posible. El usuario podrá encontrar sus archivos independientemente del dispositivo en el que inicie sesión. Por ejemplo, si reemplaza un dispositivo de Escritorio administrado de Microsoft por uno nuevo, los archivos se sincronizarán automáticamente con el nuevo dispositivo.

Configuramos automáticamente estas opciones de configuración de forma predeterminada en dispositivos administrados de Microsoft:

- OneDrive se configura silenciosamente con la cuenta de usuario e inicia sesión automáticamente (sin interacción del usuario) en la cuenta de usuario que se usó para iniciar sesión en Windows. Para obtener más información, vea [Configurar cuentas de usuario silenciosamente - OneDrive](https://docs.microsoft.com/onedrive/use-silent-account-configuration)

- La característica Archivos a petición está habilitada para que los usuarios puedan acceder a los archivos desde su almacenamiento en la nube en OneDrive sin tener que usar el espacio en disco innecesariamente. Para obtener más información, vea Guardar espacio en disco con Archivos a petición de [OneDrive para Windows 10.](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e)

- La característica Mover carpeta conocida se habilita de forma silenciosa para hacer una copia de seguridad de los datos de los usuarios en la nube, lo que les da acceso a sus archivos desde cualquier dispositivo. Para obtener más información, vea Copia de seguridad de [las carpetas Documentos, Imágenes y Escritorio con OneDrive.](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057)

- Los usuarios no pueden deshabilitar la característica mover carpetas conocidas ni cambiar la ubicación de las carpetas conocidas para garantizar una experiencia coherente en todos los dispositivos de Escritorio administrado de Microsoft.

## <a name="user-experience"></a>Experiencia del usuario

Cuando los usuarios de Escritorio administrado de Microsoft reciben un nuevo dispositivo, pasan por una experiencia de primera ejecución especificando sus credenciales de Azure al configurar el dispositivo. Una vez completado este proceso, pueden acceder a su escritorio y tener la experiencia de OneDrive.

1. El sistema indica a los usuarios que OneDrive se ha configurado y que han iniciado sesión automáticamente en OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="La lectura de notificaciones le permite sincronizar OneDrive y puede editar archivos en OneDrive. haga clic aquí para ver los archivos":::

2. El sistema indica a los usuarios que el movimiento de carpetas conocidas de OneDrive se ha configurado para ellos.

:::image type="content" source="media/onedrive-folders.png" alt-text="Notificación en la que el departamento de TI hace una copia de seguridad de las carpetas importantes. Ahora se hace una copia de seguridad de las carpetas en OneDrive y están disponibles desde otros dispositivos.":::

3. Para evitar iconos duplicados en el escritorio cuando los dispositivos se restablecen o se restablecen, el sistema quita automáticamente los iconos de Microsoft Edge y Microsoft Teams de la sincronización de OneDrive, como se muestra en esta vista en el Explorador de archivos.

:::image type="content" source="media/onedrive-teams.png" alt-text="Explorador de archivos que muestra las listas de Teams y Edge con las casillas desactivadas y la lectura de texto activada Excluida de la sincronización.":::


## <a name="onedrive-sync-restrictions"></a>Restricciones de sincronización de OneDrive

Si necesita restringir la sincronización de OneDrive, le recomendamos que controle el acceso con una directiva de acceso condicional de Azure Active Directory. Para obtener más información, vea [Habilitar la compatibilidad con el acceso condicional en la aplicación de sincronización de OneDrive.](https://docs.microsoft.com/onedrive/enable-conditional-access)

Si no puede usar una directiva de acceso condicional de Azure AD en su organización, el administrador de TI debe seguir estos pasos:

1. Si aún no lo sabe, busque su id. de espacio empresarial, como se describe en Buscar su id. de inquilino de [Microsoft 365.](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)
2. Inicie sesión en el Centro de administración de OneDrive y, a continuación, **seleccione Sincronizar** en el panel izquierdo. Active la **casilla Permitir sincronización solo** en equipos unidos a dominios específicos y, a continuación, agregue el identificador de inquilino a la lista de dominios. Para obtener más información, vea [Permitir la sincronización solo en equipos unidos a dominios específicos.](https://docs.microsoft.com/onedrive/allow-syncing-only-on-specific-domains)

> [!NOTE]
> Esta guía solo se aplica a los inquilinos del Escritorio administrado de Microsoft. Hay otras opciones de configuración en uso que no se de abordan en este artículo.
