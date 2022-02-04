---
title: Microsoft OneDrive
description: Cómo configura Microsoft Managed Desktop OneDrive dispositivos inscritos
keywords: 'Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación, aplicaciones, aplicaciones de línea de negocio, aplicaciones de línea de negocio, aplicaciones de LOB'
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
---

# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop usa [OneDrive para la Empresa](/onedrive/plan-onedrive-enterprise) como servicio de almacenamiento en la nube para todos los dispositivos de Escritorio administrado de Microsoft. Se asegura de que los dispositivos sean tan sin estado como sea posible. Los usuarios podrán encontrar sus archivos independientemente del dispositivo en el que inicien sesión. Por ejemplo, si reemplazas un dispositivo de Escritorio administrado de Microsoft por uno nuevo, los archivos se sincronizarán automáticamente con el nuevo dispositivo.

Configuramos automáticamente estas opciones de configuración de forma predeterminada en dispositivos administrados de Microsoft:

| Característica | Descripción |
| ------ | ------ |
| Configuración silenciosa | OneDrive se configura de forma silenciosa con la cuenta de usuario. Inicia sesión automáticamente, sin interacción del usuario, en la cuenta de usuario que se usó para iniciar sesión Windows. Para obtener más información, [vea Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration) |
| Files-On-Demand | La característica Files-On-Demand permite a los usuarios obtener acceso a los archivos desde su almacenamiento en la nube en OneDrive sin tener que usar el espacio en disco innecesariamente. Para obtener más información, vea [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e). |
| Movimiento de carpetas conocidas | La característica Mover carpeta conocida se habilita de forma silenciosa para hacer una copia de seguridad de los datos de los usuarios en la nube, lo que les da acceso a sus archivos desde cualquier dispositivo. Para obtener más información, consulta [Copia de seguridad de las carpetas Documentos, Imágenes y Escritorio con OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057). <p> Los usuarios no pueden deshabilitar la característica Mover carpeta conocida ni cambiar la ubicación de las carpetas conocidas para garantizar una experiencia coherente en todos los dispositivos de Escritorio administrado de Microsoft.</p>|

## <a name="user-experience"></a>Experiencia del usuario

Cuando los usuarios de Escritorio administrado de Microsoft reciben un nuevo dispositivo, pasan por una experiencia de primera ejecución, especificando sus credenciales de Azure y configurando el dispositivo. Una vez completado este proceso, pueden acceder a su escritorio y tener la OneDrive experiencia.

1. El sistema indica a los usuarios OneDrive se han configurado y que han iniciado sesión automáticamente en OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="La lectura de notificaciones que ahora está sincronizando OneDrive puede editar archivos en OneDrive. Haga clic aquí para ver los archivos.":::

2. El sistema indica a los usuarios OneDrive se ha configurado el movimiento de carpetas conocidos para ellos.

:::image type="content" source="media/onedrive-folders.png" alt-text="Notificación en la que el departamento de TI ha copiado de seguridad de las carpetas importantes. Las carpetas ahora se copian de seguridad OneDrive y están disponibles desde otros dispositivos.":::

3. Para evitar iconos duplicados en el escritorio cuando los dispositivos se restablecen o se restablecen, el sistema quita automáticamente Microsoft Edge y Microsoft Teams iconos de la Sincronización de OneDrive. Esta información se muestra en el Explorador de archivos.

:::image type="content" source="media/onedrive-teams.png" alt-text="Explorador de archivos que muestra Teams y listas perimetrales con casillas desactivadas y texto activando la lectura Excluido de la sincronización.":::

## <a name="onedrive-sync-restrictions"></a>Sincronización de OneDrive restricciones

Si necesita restringir el Sincronización de OneDrive, se recomienda controlar el acceso con una Azure Active Directory de acceso condicional. Para obtener más información, consulta [Habilitar la compatibilidad con el acceso condicional en la Sincronización de OneDrive aplicación](/onedrive/enable-conditional-access).

Si no puede usar una directiva de Azure AD de acceso condicional en su organización, el administrador de TI debe seguir estos pasos:

1. Si aún no lo sabe, busque su identificador de inquilino, tal como se describe en [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).
1. Inicie sesión en el centro OneDrive administración.
1. En el panel izquierdo, seleccione **Sincronizar**.
1. Active la **casilla Permitir la sincronización solo** en equipos unidos a dominios específicos y, a continuación, agregue el identificador de inquilino a la lista de dominios. Para obtener más información, vea [Permitir la sincronización solo en equipos unidos a dominios específicos](/onedrive/allow-syncing-only-on-specific-domains).

> [!NOTE]
> Esta guía solo se aplica a los inquilinos de Microsoft Managed Desktop. Hay otras opciones de configuración en uso que no se debatieron en este artículo.
