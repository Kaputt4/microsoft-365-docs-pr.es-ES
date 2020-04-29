---
title: Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Los administradores pueden habilitar la compatibilidad con la etiqueta de confidencialidad para los archivos de Word, Excel y PowerPoint en SharePoint y OneDrive.
ms.openlocfilehash: 09b955a3cf5b987d2ca7dac37c4c604fb45a2e56
ms.sourcegitcommit: 90f7bbba5fc23f10b59c75b2b65d6c0903ce66dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2020
ms.locfileid: "43930156"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive-public-preview"></a>Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (vista previa)

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Antes de esta vista previa, no se pueden aplicar las [etiquetas de confidencialidad](sensitivity-labels.md) en Office en la Web. No se ha podido ver la opción de **sensibilidad** en la cinta o el nombre de etiqueta aplicado en la barra de estado. Además, si usó aplicaciones de escritorio para etiquetar los archivos y guardarlos en SharePoint o en Onedrive, el servicio no podrá procesar el contenido de estos archivos si la etiqueta aplicó el cifrado. La coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda, Delve y otras características de colaboración no funcionarán en estas circunstancias. 

Esta vista previa habilita todas estas funciones. Además de mostrar las etiquetas de confidencialidad a los usuarios, para los archivos nuevos y modificados que tengan una etiqueta de sensibilidad aplicada que incluya cifrado con una clave basada en la nube:

- SharePoint reconoce las etiquetas de confidencialidad que se aplican a los archivos de Word, Excel y PowerPoint en SharePoint y OneDrive: mientras el archivo está almacenado en SharePoint, se quita el cifrado de Azure Information Protection para que se pueda procesar el contenido del archivo. Para obtener información sobre cómo se protegen los documentos mientras se almacenan en SharePoint, vea [cifrado de datos en OneDrive para la empresa y SharePoint Online](data-encryption-in-odb-and-spo.md).

- Al descargar o tener acceso a este archivo desde SharePoint o OneDrive, la etiqueta de confidencialidad y la configuración de cifrado de la etiqueta se vuelve a aplicar con el archivo, y esta configuración se mantiene obligatoria siempre que el archivo se guarde. Debido a este comportamiento, asegúrese de proporcionar a los usuarios instrucciones para que solo usen etiquetas para proteger documentos. Para obtener más información, consulte [Opciones de Information Rights Management (IRM) y las etiquetas de confidencialidad](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Para que SharePoint Quite el cifrado del archivo al cargarlo, el usuario que cargue el archivo cifrado y etiquetado debe tener permisos de uso para al menos ver el archivo. SharePoint no quita el cifrado de los archivos si el usuario no puede abrirlos fuera de SharePoint.

- Use Office en la web (Word, Excel y PowerPoint) para abrir y editar archivos de Office con etiquetas de distinción que aplican el cifrado. Se aplican los permisos asignados al cifrado. Con Word en la web, también puede usar la etiqueta automática cuando edita estos documentos.

- Office 365 eDiscovery admite la búsqueda de texto completo para estos archivos. Las directivas de prevención de pérdida de datos (DLP) cubren el contenido de estos archivos.

> [!NOTE]
> Si no se ha aplicado el cifrado con una clave basada en la nube, pero con una clave local, una topología de administración de claves a menudo denominada "mantener su propia clave" (HYOK), el comportamiento de SharePoint para procesar el contenido del archivo no cambia con esta vista previa.
>
> El comportamiento de SharePoint tampoco cambia para los archivos con etiquetas y cifrados existentes en SharePoint antes de habilitar la vista previa. Para que estos archivos se beneficien de las nuevas funciones, deben descargarse y cargarse, o bien editarse después de habilitar la vista previa. Por ejemplo, se devolverán en los resultados de búsqueda y exhibición de documentos electrónicos.

Cuando se habilita esta vista previa, hay disponibles tres nuevos [eventos de auditoría](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) para supervisar las etiquetas de confidencialidad que se aplican con Office en la web:
- **Etiqueta de confidencialidad aplicada al archivo**
- **Se ha cambiado la etiqueta de confidencialidad aplicada al archivo**
- **Etiqueta de confidencialidad eliminada del sitio**

Vea el siguiente vídeo (sin audio) para ver estas nuevas funciones en acción:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Siempre tiene la opción de optar por no participar en esta vista previa en cualquier momento.

## <a name="requirements"></a>Requisitos

Estas características solo funcionan con las [etiquetas de confidencialidad](sensitivity-labels.md) . Si tiene etiquetas de Azure Information Protection, primero deberá migrarlas a las etiquetas de confidencialidad para que pueda habilitarlas para los nuevos archivos que cargue. Para obtener instrucciones, consulte [How to Migrate Azure Information Protection Labels to Unified Sensitivity Labels](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

Para esta vista previa, use la versión 19.002.0121.0008 o posterior de la aplicación de sincronización de OneDrive en Windows y la versión 19.002.0107.0008 o posterior en Mac. Ambas versiones se han lanzado el 28 de enero de 2019 y actualmente están publicadas para todos los anillos. Para obtener más información, vea las notas de la [versión de OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Una vez habilitada esta vista previa, se pedirá a los usuarios que ejecuten una versión anterior de la aplicación de sincronización que la actualicen.

## <a name="limitations"></a>Limitaciones

- Cuando habilita esta vista previa, los usuarios que cambian una etiqueta en un archivo en una carpeta de sincronización de OneDrive podrían no ser capaces de guardar otros cambios realizados en el archivo. Este escenario se aplica a los archivos etiquetados con cifrado, y también cuando el cambio de la etiqueta es de una etiqueta que no ha aplicado el cifrado a una etiqueta que aplica el cifrado. Los usuarios ven un [círculo rojo con un error de icono en forma de cruz blanca](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)y se les pide que guarden los cambios nuevos como una copia independiente.  
    
    Además de los cambios de etiqueta que inician los usuarios, se puede producir el mismo comportamiento si un administrador cambia la configuración de una etiqueta publicada que ya se ha aplicado a los archivos descargados en el cliente de sincronización de los usuarios.
    
    Para evitar la pérdida de trabajo en estos escenarios, realice una de estas acciones:
    - Para aplicar etiquetas, use las versiones web de las aplicaciones de Office.
    - Cierre un archivo después de aplicar una etiqueta y, a continuación, vuelva a abrir el archivo para realizar otros cambios.

- SharePoint no aplica automáticamente las etiquetas de confidencialidad a los archivos existentes que ya cifró mediante las etiquetas de Azure Information Protection. En su lugar, para que las características funcionen después de habilitar esta vista previa, complete estas tareas:
    
    1. Asegúrese de que ha migrado las etiquetas de Azure Information Protection a las etiquetas de confidencialidad y las ha publicado en el centro de cumplimiento de Microsoft 365, o bien en el centro de administración de etiquetas equivalente.
    
    2. Descargue los archivos y, a continuación, cárguelos en SharePoint.

- SharePoint no puede procesar archivos cifrados cuando la etiqueta que ha aplicado el cifrado tiene alguna de las siguientes configuraciones para el cifrado:
    - **Permitir que los usuarios asignen permisos cuando apliquen la etiqueta** y la casilla **en Word, PowerPoint y Excel, pedir a los usuarios que especifiquen permisos** está seleccionada. Esta configuración se denomina a veces "permisos definidos por el usuario".
    - El **acceso del usuario a las expiraciones de contenido** se establece en un valor que no es **nunca**.
    
    Para las etiquetas con cualquiera de estas configuraciones de cifrado, las etiquetas no se muestran a los usuarios en Office en la Web. Además, las nuevas funciones de esta vista previa no se pueden usar con documentos etiquetados que ya tienen esta configuración de cifrado. Por ejemplo, estos documentos no se devolverán en los resultados de la búsqueda, aunque se actualicen.

- En el caso de un documento cifrado que concede permisos de edición a un usuario, no se puede bloquear la copia en las versiones web de las aplicaciones de Office.

- No se admite el sitio de seguimiento de documentos de Azure Information Protection.

- Las aplicaciones de escritorio y las aplicaciones móviles de Office no admiten la coautoría para los archivos etiquetados con cifrado. Estas aplicaciones continúan a la vez que los archivos identificados y cifrados se abren en el modo de edición exclusivo.

- Si se carga un documento con etiquetas en SharePoint y la etiqueta aplicó el cifrado mediante una cuenta desde un nombre principal de servicio, el documento no se puede abrir en Office en la Web. Los escenarios de ejemplo incluyen Microsoft Cloud App Security y un archivo enviado a Teams por correo electrónico.

- Los usuarios pueden experimentar problemas de guardado después de pasarse sin conexión o a un modo de suspensión en lugar de usar Office para la web, usan las aplicaciones móviles y de escritorio de Word, Excel o PowerPoint. Para estos usuarios, cuando reanudan la sesión de la aplicación de Office y intentan guardar los cambios, ven un mensaje de error de carga con una opción para guardar una copia en lugar de guardar el archivo original. 

- Los documentos que se han cifrado de las maneras siguientes no se pueden abrir en Office en la web:
    - Cifrado que usa una clave local ("conserve su propia clave" o HYOK)
    - Cifrado que se aplicó de forma independiente de una etiqueta, por ejemplo, aplicando directamente una plantilla de protección de administración de derechos.

- Si elimina una etiqueta que se ha aplicado a un documento en SharePoint, en lugar de quitar la etiqueta de la Directiva de etiqueta aplicable, el documento cuando se descargue no se etiquetará ni cifrará. En comparación, si el documento etiquetado se almacena fuera de SharePoint, el documento permanece cifrado si se elimina la etiqueta. Tenga en cuenta que, aunque puede eliminar etiquetas durante una fase de pruebas, es muy raro eliminar una etiqueta en un entorno de producción.

## <a name="prepare-the-sharepoint-online-management-shell-for-the-preview"></a>Preparar el shell de administración de SharePoint Online para la versión preliminar

Para habilitar la vista previa con PowerShell, asegúrese de que está ejecutando la versión 16.0.19418.12000 o posterior del shell de administración de SharePoint Online. Si ya tiene la versión más reciente, puede seguir adelante y habilitar la vista previa.

1. Si tiene instalada una versión anterior de Shell de SharePoint Online Management de la galería de PowerShell, puede actualizar el módulo ejecutando el siguiente cmdlet.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, si ha instalado una versión anterior del shell de administración de SharePoint Online desde el centro de descarga de Microsoft, también puede ir a **Agregar o quitar programas** y desinstalar el shell de administración de SharePoint Online.

3. En un explorador web, vaya a la página del centro de descargas y [Descargue el Shell más reciente de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Seleccione el idioma y, a continuación, haga clic en **Descargar**.

5. Elija entre el archivo .msi x64 y x86. Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si ejecuta la versión de 32 bits. Si no lo sabe, consulte ¿ [qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Una vez que haya descargado el archivo, ejecute el archivo y siga los pasos del Asistente para la instalación.

## <a name="enable-the-preview-by-using-microsoft-powershell-opt-in"></a>Habilitación de la vista previa mediante PowerShell de Microsoft (opción opcional)

Para habilitar la vista previa, use el cmdlet Set-SPOTenant:

1. Con una cuenta profesional o educativa con privilegios de administrador global o de administrador de SharePoint en Office 365, conéctese a SharePoint. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    Nota: Si tiene Office 365 multigeográfico, use el parámetro-URL con [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice?view=sharepoint-ps)y especifique la dirección URL del sitio del centro de administración de SharePoint Online para una de las ubicaciones geográficas.

2. Ejecute el siguiente comando:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true  
    ```
3. Para Office 365 multi-geo: Repita los pasos 1 y 2 para cada una de las ubicaciones geográficas restantes.

## <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Usar el centro de cumplimiento para habilitar la compatibilidad con las etiquetas de confidencialidad

Esta opción actualmente se está implementando en los inquilinos como un método alternativo para habilitar la vista previa.

El administrador global de su organización tiene permisos totales para crear y administrar todos los aspectos de las etiquetas de confidencialidad. Si no va a iniciar sesión como administrador global, consulte [Permisos necesarios para crear y administrar etiquetas de confidencialidad](get-started-with-sensitivity-labels.md#permissions-required-to-create-and-manage-sensitivity-labels).

1. Inicie sesión en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/)y vaya a **soluciones** > **Information Protection**
    
    Si no ve esta opción inmediatamente, primero seleccione **Mostrar todo**. 

2. En la pestaña **etiquetas** , si ve un mensaje para activar la capacidad de procesar contenido en archivos de Office Online, seleccione **Activar ahora**:
    
    ![Activar ahora el botón para habilitar las etiquetas de confidencialidad de Office Online](../media/sensitivity-labels-turn-on-banner.png)
    
    El comando se ejecuta inmediatamente y la próxima vez que se actualiza la página, ya no verá el mensaje o el botón. 

> [!NOTE]
> Si tiene Office 365 multigeográfico, debe usar PowerShell para habilitar estas funcionalidades para todas las ubicaciones geográficas. Para obtener instrucciones, consulte las secciones anteriores.

## <a name="schedule-roll-out-after-you-create-or-change-a-sensitivity-label"></a>Programar la distribución después de crear o cambiar una etiqueta de confidencialidad

Después de crear o cambiar una etiqueta de confidencialidad en el centro de cumplimiento de Microsoft 365, publíquela en fases. Si publica etiquetas que no se han sincronizado completamente, cuando los usuarios aplican las etiquetas a los archivos y los cargan en SharePoint, los archivos no se pueden abrir en las versiones web de las aplicaciones de Office. La búsqueda y la exhibición de documentos electrónicos tampoco funcionan para los archivos.

Le recomendamos que siga estos pasos:

1. Publicar la etiqueta de confidencialidad nueva o modificada solo para una o dos personas.

2. Espere al menos 24 horas después de la publicación inicial. Compruebe que la etiqueta se haya sincronizado completamente.

3. Publique la etiqueta de forma general.

## <a name="disable-the-preview-by-using-microsoft-powershell-opt-out"></a>Deshabilitar la vista previa mediante PowerShell de Microsoft (no participar)

Si deshabilita esta vista previa, los archivos que cargó en la vista previa seguirán protegidos por la etiqueta. La configuración correspondiente se sigue aplicando. Cuando se aplican etiquetas a nuevos archivos después de deshabilitar la vista previa, la búsqueda de texto completo, la exhibición de documentos electrónicos y la coautoría dejarán de funcionar.

Para deshabilitar la vista previa, use el cmdlet Set-SPOTenant:

1. Con una cuenta profesional o educativa que tenga privilegios de administrador global o de administrador de SharePoint, conéctese a SharePoint. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

2. Ejecute el comando siguiente:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $false
    ```

## <a name="next-steps"></a>Siguientes pasos

Ahora que ha habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, considere la posibilidad de etiquetar automáticamente estos archivos mediante directivas de etiquetado automático. Para obtener más información, vea [aplicar una etiqueta de confidencialidad a contenido automáticamente](apply-sensitivity-label-automatically.md).