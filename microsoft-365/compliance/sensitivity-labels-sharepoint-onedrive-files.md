---
title: Habilitación de etiquetas de confidencialidad para archivos de Office
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- purview-compliance
- tier1
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Los administradores pueden habilitar la compatibilidad con etiquetas de confidencialidad para archivos de Word, Excel y PowerPoint en SharePoint y OneDrive.
ms.openlocfilehash: 6d3f18556a075cc6ee79481117c863b0cd107564
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68728805"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Habilite el etiquetado integrado para [los archivos de Office admitidos](sensitivity-labels-office-apps.md#office-file-types-supported) en SharePoint y OneDrive para que los usuarios puedan aplicar [las etiquetas de confidencialidad](sensitivity-labels.md) en Office para la Web. Cuando esta característica está habilitada, los usuarios verán el botón **Confidencialidad** en la cinta de opciones para que puedan aplicar etiquetas y ver cualquier nombre de etiqueta aplicado en la barra de estado.

La habilitación de esta característica también hace que SharePoint y OneDrive puedan procesar el contenido de los archivos de Office que se han cifrado mediante una etiqueta de confidencialidad. La etiqueta se puede aplicar en Office para la Web o en aplicaciones de escritorio de Office y cargarse o guardarse en SharePoint y OneDrive. Hasta que no habilite esta característica, estos servicios no podrán procesar archivos cifrados, lo que significa que la coautoría, eDiscovery, la prevención de pérdida de datos de Microsoft Purview, la búsqueda y otras características de colaboración no funcionarán para estos archivos.

Después de habilitar etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, para los archivos nuevos y modificados que tienen una etiqueta de confidencialidad que aplica el cifrado con una clave basada en la nube (y no usa [el cifrado de clave doble](double-key-encryption.md):

- Para los archivos de Word, Excel y PowerPoint, SharePoint y OneDrive reconocen la etiqueta y ahora pueden procesar el contenido del archivo cifrado.

- Cuando los usuarios descargan o acceden a estos archivos desde SharePoint o OneDrive, la etiqueta de confidencialidad y cualquier configuración de cifrado de la etiqueta se aplican y permanecen con el archivo, dondequiera que se almacene. Asegúrese de proporcionar instrucciones al usuario para usar solo etiquetas para proteger documentos. Para obtener más información, consulte [Opciones de Information Rights Management (IRM) y etiquetas de confidencialidad](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Cuando los usuarios cargan archivos etiquetados y cifrados en SharePoint o OneDrive, deben tener al menos derechos de vista para esos archivos. Por ejemplo, pueden abrir los archivos fuera de SharePoint. Si no tienen este derecho de uso mínimo, la carga se realiza correctamente, pero el servicio no reconoce la etiqueta y no puede procesar el contenido del archivo.

- Use Office para la Web (Word, Excel, PowerPoint) para abrir y editar archivos de Office que tengan etiquetas de confidencialidad que apliquen cifrado. Se aplican los permisos asignados con el cifrado. También puede usar [el etiquetado automático](apply-sensitivity-label-automatically.md) para estos documentos.

- Los usuarios externos pueden acceder a documentos etiquetados con cifrado mediante cuentas de invitado. Para obtener más información, consulte [Compatibilidad con usuarios externos y contenido etiquetado](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content).

- Office 365 eDiscovery admite la búsqueda de texto completo para estos archivos y las directivas de prevención de pérdida de datos (DLP) admiten contenido en estos archivos.

> [!NOTE]
> Si el cifrado se ha aplicado con una clave local (una topología de administración de claves a menudo denominada "mantener su propia clave" o HYOK), o mediante el [uso del cifrado de clave doble](double-key-encryption.md), el comportamiento del servicio para procesar el contenido del archivo no cambia. Por lo tanto, para estos archivos, la coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda y otras características de colaboración no funcionarán.
>
> El comportamiento de SharePoint y OneDrive tampoco cambia para los archivos existentes en estas ubicaciones que están etiquetados con cifrado mediante una sola clave basada en Azure. Para que estos archivos se beneficien de las nuevas funcionalidades después de habilitar etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, los archivos deben descargarse y cargarse de nuevo o editarse.

Después de habilitar etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, hay tres nuevos [eventos de auditoría](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) disponibles para supervisar las etiquetas de confidencialidad que se aplican a los documentos de SharePoint y OneDrive:

- **Etiqueta de confidencialidad aplicada al archivo**
- **Se ha cambiado la etiqueta de confidencialidad aplicada al archivo**
- **Etiqueta de confidencialidad eliminada del sitio**

Vea el siguiente vídeo (sin audio) para ver las nuevas funcionalidades en acción:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Siempre tiene la opción de deshabilitar etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive ([no participar](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)) en cualquier momento.

Si actualmente está protegiendo documentos en SharePoint mediante SharePoint Information Rights Management (IRM), asegúrese de comprobar la sección [SharePoint Information Rights Management (IRM) y las etiquetas de confidencialidad](#sharepoint-information-rights-management-irm-and-sensitivity-labels) de esta página.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="requirements"></a>Requisitos

Estas nuevas funcionalidades solo funcionan con [etiquetas de confidencialidad](sensitivity-labels.md) . Si actualmente tiene etiquetas de Azure Information Protection, migrelas primero a etiquetas de confidencialidad para que pueda habilitar estas características para los nuevos archivos que cargue. Para obtener más información acerca de este proceso, consulte [Cómo migrar las etiquetas de Azure Information Protection a etiquetas de confidencialidad unificadas](/azure/information-protection/configure-policy-migrate-labels)

Use la versión 19.002.0121.0008 o posterior de la aplicación Sincronización de OneDrive en Windows y la versión 19.002.0107.0008 o posterior en Mac. Ambas versiones se publicaron el 28 de enero de 2019 y actualmente se publican en todos los anillos. Para obtener más información, consulte las notas de la [versión de OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Después de habilitar las etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, se pedirá a los usuarios que ejecuten una versión anterior de la aplicación de sincronización que la actualicen.

## <a name="supported-file-types"></a>Tipos de archivo compatibles

Después de habilitar las etiquetas de confidencialidad para SharePoint y OneDrive, se admiten los siguientes tipos de archivo para escenarios de etiquetado de confidencialidad.

Aplicar una etiqueta de confidencialidad en Office en la Web o en SharePoint:

- **Palabra**: .docx, .docm
- **Excel**: .xlsx, .xlsm, .xlsb
- **PowerPoint**: .pptx, .ppsx

Carga de un documento etiquetado y, a continuación, extracción y visualización de esa etiqueta de confidencialidad:

- **Word**: doc, .docx, .docm, .dot, .dotx, .dotm
- **Excel**: .xls, .xlt, .xla, .xlc, .xlm, .xlw, .xlsx, .xltx, .xlsm, .xltm, .xlam, .xlsb
- **PowerPoint**: .ppt, .pot, .pps, .ppa, .pptx, .ppsx, .ppsxm, .potx, .ppam, .pptm, .potm, .ppsm

## <a name="limitations"></a>Limitaciones

- SharePoint y OneDrive no pueden procesar algunos archivos etiquetados y cifrados desde aplicaciones de escritorio de Office cuando estos archivos contienen datos de PowerQuery, datos almacenados por complementos personalizados o elementos XML personalizados, como propiedades de página de portada, esquemas de tipo de contenido, panel de información de documento personalizado y XSN personalizado. Esta limitación también se aplica a los archivos que incluyen una [bibliografía](https://support.microsoft.com/en-us/office/create-a-bibliography-citations-and-references-17686589-4824-4940-9c69-342c289fa2a5) y a los archivos que tienen un [identificador de documento](https://support.microsoft.com/office/enable-and-configure-unique-document-ids-ea7fee86-bd6f-4cc8-9365-8086e794c984) agregado cuando se cargan.

    Para estos archivos, aplique una etiqueta sin cifrado para que se puedan abrir más adelante en Office en la Web o indique a los usuarios que abran los archivos en sus aplicaciones de escritorio. Los archivos etiquetados y cifrados solo en Office en la Web no se ven afectados.

- SharePoint y OneDrive no aplican automáticamente etiquetas de confidencialidad a los archivos existentes que ya ha cifrado mediante etiquetas de Azure Information Protection. En su lugar, para que las características funcionen después de habilitar etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, complete estas tareas:

    1. Asegúrese de que ha [migrado las etiquetas de Azure Information Protection a etiquetas](/azure/information-protection/configure-policy-migrate-labels) de confidencialidad y [las ha publicado](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) desde el portal de cumplimiento Microsoft Purview.
    2. Descargue los archivos etiquetados y cárguelos en su ubicación original en SharePoint o OneDrive.

- SharePoint y OneDrive no pueden procesar archivos cifrados cuando la etiqueta que aplicó el cifrado tiene cualquiera de las [siguientes configuraciones para el cifrado](encryption-sensitivity-labels.md#configure-encryption-settings):
  - **Permitir que los usuarios asignen permisos cuando apliquen la etiqueta** y la casilla **En Word, PowerPoint y Excel, pedir a los usuarios que especifiquen permisos** seleccionada. A veces, esta configuración se conoce como "permisos definidos por el usuario".
  - **El acceso del usuario al contenido expira** establecido en un valor distinto de **Nunca**.
  - **Cifrado de clave doble** seleccionado.

    En el caso de las etiquetas con cualquiera de estas configuraciones de cifrado, las etiquetas no se muestran a los usuarios en Office para la Web. Además, las nuevas funcionalidades no se pueden usar con documentos etiquetados que ya tienen esta configuración de cifrado. Por ejemplo, estos documentos no se devolverán en los resultados de búsqueda, aunque se actualicen.

- Por motivos de rendimiento, al cargar o guardar un documento en SharePoint y la etiqueta del archivo no aplica el cifrado, la columna **Confidencialidad** de la biblioteca de documentos puede tardar un tiempo en mostrar el nombre de la etiqueta. Tenga en cuenta este retraso si usa scripts o automatización que dependen del nombre de etiqueta de esta columna.

- Si un documento está etiquetado mientras está [desprotegido en SharePoint](https://support.microsoft.com/office/check-out-check-in-or-discard-changes-to-files-in-a-library-7e2c12a9-a874-4393-9511-1378a700f6de), la columna **Confidencialidad** de la biblioteca de documentos no mostrará el nombre de la etiqueta hasta que el documento esté protegido y se abra a continuación en SharePoint.

- Si una aplicación o servicio que usa un nombre de entidad de seguridad de servicio descarga un documento etiquetado y cifrado desde SharePoint o OneDrive y, a continuación, se carga de nuevo con una etiqueta que aplica una configuración de cifrado diferente, se producirá un error en la carga. Un escenario de ejemplo es Microsoft Defender for Cloud Apps cambia una etiqueta de confidencialidad en un archivo de **Confidencial** a **Extremadamente confidencial** o de **Confidencial** a **General**.

    No se produce un error en la carga si la aplicación o el servicio ejecuta primero el cmdlet [Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) , como se explica en la sección [Quitar cifrado para un documento etiquetado](#remove-encryption-for-a-labeled-document) . O bien, antes de la carga, se elimina el archivo original o se cambia el nombre del archivo.

- Es posible que los usuarios experimenten retrasos al poder abrir documentos cifrados en el siguiente escenario guardar como: Con una versión de escritorio de Office, un usuario elige Guardar como para un documento que tiene una etiqueta de confidencialidad que aplica el cifrado. El usuario selecciona SharePoint o OneDrive para la ubicación y, a continuación, intenta abrir inmediatamente ese documento en Office para la Web. Si el servicio sigue procesando el cifrado, el usuario ve un mensaje que indica que el documento debe abrirse en su aplicación de escritorio. Si lo intentan de nuevo en un par de minutos, el documento se abre correctamente en Office para la Web.

- En el caso de los documentos cifrados, la impresión no se admite en Office para la Web.

- En el caso de los documentos cifrados en Office para la Web, [no se impiden las capturas de pantalla](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures). Hasta hace poco, no se impedía la copia en el Portapapeles para estos documentos. Ahora, cuando los documentos se etiquetan y cifran, y no se **concede el** [derecho de uso](/azure/information-protection/configure-usage-rights) de copia, Office en la Web impide la copia en el Portapapeles de la misma manera que las aplicaciones de escritorio impiden esta acción. Actualmente hay algunas excepciones para volver a etiquetar escenarios hasta que se actualiza el explorador, se inicia otra sesión o se vuelve a abrir el documento:
    - A mitad de sesión, el documento cambia de sin cifrar a cifrado.
    - A mitad de sesión, el documento cambia de cifrado y se concede el derecho de uso de copia a cifrado, pero no se concede el derecho de uso de copia.

- De forma predeterminada, las aplicaciones de escritorio y las aplicaciones móviles de Office no admiten la coautoría de archivos etiquetados con cifrado. Estas aplicaciones continúan abriendo archivos etiquetados y cifrados en modo de edición exclusivo.

    > [!NOTE]
    > La coautoría ahora es compatible con Windows y macOS, y en versión preliminar para iOS y Android. Para obtener más información, consulte [Habilitación de la coautoría para archivos cifrados con etiquetas de confidencialidad](sensitivity-labels-coauthoring.md).

- Si un administrador cambia la configuración de una etiqueta publicada que ya se ha aplicado a los archivos descargados en el cliente de sincronización de los usuarios, es posible que los usuarios no puedan guardar los cambios que realicen en el archivo en su carpeta De sincronización de OneDrive. Este escenario se aplica a los archivos etiquetados con cifrado y también cuando el cambio de etiqueta es de una etiqueta que no aplicó el cifrado a una etiqueta que aplica el cifrado. Los usuarios ven un [círculo rojo con un error de icono de cruz blanca](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3) y se les pide que guarden los cambios nuevos como una copia independiente. En su lugar, pueden cerrar y volver a abrir el archivo o usar Office para la Web.

- Los usuarios pueden experimentar problemas de ahorro después de desconectarse o en modo de suspensión cuando, en lugar de usar Office para la Web, usan las aplicaciones de escritorio y móviles para Word, Excel o PowerPoint. Para estos usuarios, cuando reanudan la sesión de la aplicación de Office e intentan guardar los cambios, ven un mensaje de error de carga con una opción para guardar una copia en lugar de guardar el archivo original.

- Los documentos cifrados de las siguientes maneras no se pueden abrir en Office para la Web:
  - Cifrado que usa una clave local ("mantenga su propia clave" o HYOK)
  - Cifrado que se aplicó mediante [el cifrado de doble clave](double-key-encryption.md)
  - Cifrado que se aplicó independientemente de una etiqueta, por ejemplo, aplicando directamente una plantilla de protección de Rights Management.

- Las etiquetas configuradas para [otros idiomas](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-powershell) no se admiten y solo muestran el idioma original.

- Si elimina una etiqueta que se ha aplicado a un documento en SharePoint o OneDrive, en lugar de quitar la etiqueta de la directiva de etiquetas aplicable, el documento cuando se descargue no se etiquetará ni cifrará. En comparación, si el documento etiquetado se almacena fuera de SharePoint o OneDrive, el documento permanece cifrado si se elimina la etiqueta. Tenga en cuenta que, aunque puede eliminar etiquetas durante una fase de prueba, es muy raro eliminar una etiqueta en un entorno de producción.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Habilitación de etiquetas de confidencialidad para SharePoint y OneDrive (participación)

Puede habilitar las nuevas funcionalidades mediante el portal de cumplimiento Microsoft Purview o mediante PowerShell. Consulte las secciones siguientes para obtener instrucciones.

Al igual que con todos los cambios de configuración de nivel de inquilino para SharePoint y OneDrive, el cambio tarda aproximadamente 15 minutos en surtir efecto.

### <a name="use-the-microsoft-purview-compliance-portal-to-enable-support-for-sensitivity-labels"></a>Uso de la portal de cumplimiento Microsoft Purview para habilitar la compatibilidad con etiquetas de confidencialidad

Esta opción es la manera más sencilla de habilitar etiquetas de confidencialidad para SharePoint y OneDrive, pero debe iniciar sesión como administrador global para el inquilino.

1. Inicie sesión en el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/) como administrador global y vaya a **Etiquetas** de protección  >  de **la información** de **soluciones** > 

2. Si ve un mensaje para activar la capacidad de procesar contenido en archivos en línea de Office, seleccione **Activar ahora**:

    ![Active el botón ahora para habilitar las etiquetas de confidencialidad para Office Online.](../media/sensitivity-labels-turn-on-banner.png)

    El comando se ejecuta inmediatamente y, cuando la página se actualiza a continuación, ya no verá el mensaje o el botón.

> [!NOTE]
> Si tiene Microsoft 365 Multi-Geo, debe usar PowerShell para habilitar estas funcionalidades para todas las ubicaciones geográficas. Consulte la siguiente sección para obtener detalles.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Uso de PowerShell para habilitar la compatibilidad con etiquetas de confidencialidad

Como alternativa al uso de la portal de cumplimiento Microsoft Purview, puede habilitar la compatibilidad con etiquetas de confidencialidad mediante el cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) de SharePoint Online PowerShell.

Si tiene Microsoft 365 Multi-Geo, debe usar PowerShell para habilitar esta compatibilidad con todas las ubicaciones geográficas.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Preparación del Shell de administración de SharePoint Online

Antes de ejecutar el comando de PowerShell para habilitar etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, asegúrese de que ejecuta la versión 16.0.19418.12000 o posterior del Shell de administración de SharePoint Online. Si ya tiene la versión más reciente, puede ir al [siguiente procedimiento](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) para ejecutar el comando de PowerShell.

1. Si tiene instalada una versión anterior de Shell de SharePoint Online Management de la galería de PowerShell, puede actualizar el módulo ejecutando el siguiente cmdlet.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, si ha instalado una versión anterior del Shell de administración de SharePoint Online desde el Centro de descarga de Microsoft, también puede ir a **Agregar o quitar programas** y desinstalar el Shell de administración de SharePoint Online.

3. En un explorador web, vaya a la página del centro de descargas y [Descargue el Shell más reciente de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Seleccione el idioma y, a continuación, haga clic en **Descargar**.

5. Elija entre el archivo .msi x64 y x86. Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si ejecuta la versión de 32 bits. Si no lo sabe, consulte [¿Qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Después de descargar el archivo, ejecute el archivo y siga los pasos descritos en el Asistente para la instalación.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Ejecute el comando de PowerShell para habilitar la compatibilidad con etiquetas de confidencialidad.

Para habilitar las nuevas funcionalidades, use el cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) con el parámetro *EnableAIPIntegration* :

1. Con una cuenta profesional o educativa que tenga privilegios de administrador global o administrador de SharePoint en Microsoft 365, conéctese a SharePoint. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

    > [!NOTE]
    > Si tiene Microsoft 365 Multi-Geo, use el parámetro -Url con [Connect-SPOService](/powershell/module/sharepoint-online/connect-sposervice) y especifique la dirección URL del sitio del Centro de administración de SharePoint Online para una de las ubicaciones geográficas.

2. Ejecute el siguiente comando y presione **Y** para confirmar:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Para Microsoft 365 Multi-Geo: repita los pasos 1 y 2 para cada una de las ubicaciones geográficas restantes.

## <a name="publishing-and-changing-sensitivity-labels"></a>Publicación y cambio de etiquetas de confidencialidad

Cuando use etiquetas de confidencialidad con SharePoint y OneDrive, tenga en cuenta que debe permitir el tiempo de replicación al publicar nuevas etiquetas de confidencialidad o actualizar las etiquetas de confidencialidad existentes. Esto es especialmente importante para las etiquetas nuevas que aplican el cifrado.

Por ejemplo: crea y publica una nueva etiqueta de confidencialidad que aplica el cifrado y aparece muy rápidamente en la aplicación de escritorio de un usuario. El usuario aplica esta etiqueta a un documento y, a continuación, la carga en SharePoint o OneDrive. Si la replicación de etiquetas no se ha completado para el servicio, las nuevas funcionalidades no se aplicarán a ese documento durante la carga. Como resultado, el documento no se devolverá en la búsqueda o en eDiscovery y el documento no se puede abrir en Office para la Web.

Para obtener más información sobre el plazo de las etiquetas, consulte [Cuándo esperar que las nuevas etiquetas y los cambios entren en vigor](create-sensitivity-labels.md#when-to-expect-new-labels-and-changes-to-take-effect).

Como medida de seguridad, se recomienda publicar etiquetas nuevas para algunos usuarios de prueba primero, esperar al menos una hora y, a continuación, comprobar el comportamiento de las etiquetas en SharePoint y OneDrive. Espere al menos un día antes de poner la etiqueta a disposición de más usuarios agregando más usuarios a la directiva de etiqueta existente o agregando la etiqueta a una directiva de etiqueta existente para los usuarios estándar. Cuando los usuarios estándar ven la etiqueta, ya se ha sincronizado con SharePoint y OneDrive.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) y etiquetas de confidencialidad

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) es una tecnología anterior para proteger los archivos en el nivel de lista y biblioteca mediante la aplicación de cifrado y restricciones cuando se descargan los archivos. Esta tecnología de protección anterior está diseñada para evitar que los usuarios no autorizados abran el archivo mientras está fuera de SharePoint.

En comparación, las etiquetas de confidencialidad proporcionan la configuración de protección de marcas visuales (encabezados, pies de página, marcas de agua) además del cifrado. La configuración de cifrado admite toda la gama de [derechos de uso](/azure/information-protection/configure-usage-rights) para restringir lo que los usuarios pueden hacer con el contenido y se admiten las mismas etiquetas de confidencialidad en [muchos escenarios](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels). El uso del mismo método de protección con una configuración coherente entre cargas de trabajo y aplicaciones da como resultado una estrategia de protección coherente.

Sin embargo, puede usar ambas soluciones de protección juntos y el comportamiento es el siguiente:

- Si carga un archivo con una etiqueta de confidencialidad que aplica el cifrado, SharePoint no puede procesar el contenido de estos archivos, por lo que la coautoría, la exhibición de documentos electrónicos, dlp y la búsqueda no se admiten para estos archivos.

- Si etiqueta un archivo con Office para la Web, se aplicará cualquier configuración de cifrado de la etiqueta. Para estos archivos, se admiten la coautoría, eDiscovery, DLP y la búsqueda.

- Si descarga un archivo etiquetado mediante Office para la Web, la etiqueta se conservará y se aplicará cualquier configuración de cifrado de la etiqueta en lugar de la configuración de restricción de IRM.

- Si descarga un archivo Office o PDF que no está cifrado con una etiqueta de confidencialidad, se aplica la configuración de IRM.

- Si ha habilitado cualquiera de las opciones de configuración de biblioteca de IRM adicionales, que incluyen impedir que los usuarios carguen documentos que no admiten IRM, se aplican estas opciones.

Con este comportamiento, puede estar seguro de que todos los archivos de Office y PDF están protegidos contra el acceso no autorizado si se descargan, incluso si no están etiquetados. Sin embargo, los archivos etiquetados que se cargan no se beneficiarán de las nuevas funcionalidades.

## <a name="search-for-documents-by-sensitivity-label"></a>Búsqueda de documentos por etiqueta de confidencialidad

Use la propiedad administrada **InformationProtectionLabelId** para buscar todos los documentos de SharePoint o OneDrive que tengan una etiqueta de confidencialidad específica. Use la sintaxis siguiente: `InformationProtectionLabelId:<GUID>`

Por ejemplo, para buscar todos los documentos etiquetados como "Confidencial", y esa etiqueta tiene un GUID de "8faca7b8-8d20-48a3-8ea2-0f96310a848e", en el cuadro de búsqueda, escriba:

```
InformationProtectionLabelId:8faca7b8-8d20-48a3-8ea2-0f96310a848e
```

La búsqueda no encontrará documentos etiquetados en un archivo comprimido, como un archivo .zip.

Para obtener los GUID de las etiquetas de confidencialidad, use el cmdlet [Get-Label](/powershell/module/exchange/get-label) :

1. En primer lugar, [conéctese a Office 365 Security & Compliance PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

    Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:

2. A continuación, ejecute el siguiente comando:

    ```powershell
    Get-Label |ft Name, Guid
    ```

Para obtener más información sobre el uso de propiedades administradas, vea [Administrar el esquema de búsqueda en SharePoint](/sharepoint/manage-search-schema).

## <a name="remove-encryption-for-a-labeled-document"></a>Eliminación del cifrado de un documento etiquetado

Puede haber raras ocasiones en las que un administrador de SharePoint necesita quitar el cifrado de un documento almacenado en SharePoint. Cualquier usuario que tenga asignado el [derecho de uso de Rights Management](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) de Exportación o Control total para ese documento puede quitar el cifrado que aplicó el servicio Azure Rights Management de Azure Information Protection. Por ejemplo, los usuarios con cualquiera de estos derechos de uso pueden reemplazar una etiqueta que aplica el cifrado por una etiqueta sin cifrado. Un [superusuario](/azure/information-protection/configure-super-users) también podría descargar el archivo y guardar una copia local sin el cifrado.

Como alternativa, un administrador global o [administrador de SharePoint](/sharepoint/sharepoint-admin-role) puede ejecutar el cmdlet [Unlock-SPOSensitivityLabelEncryptedFile](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) , que quita la etiqueta de confidencialidad y el cifrado. Este cmdlet se ejecuta incluso si el administrador no tiene permisos de acceso al sitio o al archivo, o si el servicio de Azure Rights Management no está disponible.

Por ejemplo:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Requisitos:

- Shell de administración de SharePoint Online versión 16.0.20616.12000 o posterior.

- El cifrado se ha aplicado mediante una etiqueta de confidencialidad con la configuración de cifrado definida por el administrador (la configuración [Asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now) etiqueta). No se admite el [cifrado de doble clave](encryption-sensitivity-labels.md#double-key-encryption) para este cmdlet.

El texto de justificación se agrega al [evento de auditoría](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) de **La etiqueta de confidencialidad eliminada del archivo** y la acción de descifrado también se registra en el [registro de uso de protección para Azure Information Protection](/azure/information-protection/log-analyze-usage).

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Cómo deshabilitar etiquetas de confidencialidad para SharePoint y OneDrive (no participar)

Si deshabilita estas nuevas funcionalidades, los archivos que cargó después de habilitar las etiquetas de confidencialidad para SharePoint y OneDrive seguirán estando protegidos por la etiqueta porque la configuración de la etiqueta se sigue aplicando. Al aplicar etiquetas de confidencialidad a nuevos archivos después de deshabilitar estas nuevas funcionalidades, la búsqueda de texto completo, la exhibición de documentos electrónicos y la coautoría ya no funcionarán.

Para deshabilitar estas nuevas funcionalidades, debe usar PowerShell. Con el Shell de administración de SharePoint Online y el cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) , especifique el mismo parámetro *EnableAIPIntegration* como se describe en la sección [Uso de PowerShell para habilitar la compatibilidad con etiquetas de confidencialidad](#use-powershell-to-enable-support-for-sensitivity-labels) . Pero esta vez, establezca el valor del parámetro en false y presione **Y** para confirmar:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Si tiene Microsoft 365 Multi-Geo, debe ejecutar este comando para cada una de las ubicaciones geográficas.

## <a name="next-steps"></a>Pasos siguientes

Después de habilitar las etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, considere la posibilidad de etiquetar automáticamente los archivos mediante cualquiera de los métodos de etiquetado siguientes o ambos:

- Aplicar una etiqueta de confidencialidad predeterminada para bibliotecas de documentos, para archivos nuevos y editados en SharePoint. Para obtener más información, vea [Configurar una etiqueta de confidencialidad predeterminada para una biblioteca de documentos de SharePoint](sensitivity-labels-sharepoint-default-label.md).
- Directivas de etiquetado automático que usan la inspección de contenido para archivos en SharePoint y OneDrive. Para más información, consulte [Aplicar automáticamente una etiqueta de confidencialidad al contenido](apply-sensitivity-label-automatically.md).

¿Necesita compartir los documentos etiquetados y cifrados con personas fuera de su organización?  Consulte [Compartir documentos cifrados con usuarios externos](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).
