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
description: Los administradores pueden habilitar la compatibilidad con etiquetas de confidencialidad para archivos de Word, Excel y PowerPoint en SharePoint y OneDrive.
ms.openlocfilehash: 656c8c12194119aa83d9b6b6897a7c43fede08df
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326587"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Hay un problema actual que provoca que algunos archivos etiquetados y cifrados no se abran en Office en la web:
>
> Aunque investigamos un problema relacionado con propiedades de documento específicas, no podrá abrir muchos archivos en Office en la web. Para estos archivos, puede seguir abrirlos y editarlos en las aplicaciones de Office móviles y de escritorio. O bien, haga lo siguiente:
>
> 1. Abra el archivo en la aplicación de escritorio de Office.
> 2. Quite la etiqueta que aplica el cifrado.
> 3. Guarde el archivo en la ubicación original (SharePoint o OneDrive) y cierre la aplicación de escritorio.
> 4. Abra el archivo en Office en la web y vuelva a aplicar la etiqueta original que aplica el cifrado.
> 
> Los archivos etiquetados solo en Office en la web no se ven afectados.

Habilite las etiquetas de confidencialidad para los archivos [](sensitivity-labels.md) de Office en SharePoint y OneDrive para que los usuarios puedan aplicar las etiquetas de confidencialidad en Office para la web. Cuando esta característica está habilitada,  los usuarios verán el botón Confidencialidad en la cinta de opciones para que puedan aplicar etiquetas y ver cualquier nombre de etiqueta aplicado en la barra de estado.

Al habilitar esta característica también se consigue que SharePoint y OneDrive puedan procesar el contenido de los archivos cifrados mediante una etiqueta de confidencialidad. La etiqueta se puede aplicar en Office para la web o en aplicaciones de escritorio de Office y cargarse o guardarse en SharePoint y OneDrive. Hasta que habilite esta característica, estos servicios no podrán procesar archivos cifrados, lo que significa que la coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda y otras características de colaboración no funcionarán para estos archivos.

Después de habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, para los archivos nuevos y modificados que tienen una etiqueta de confidencialidad que aplica cifrado con una clave basada en la nube (y no usa cifrado de doble [clave):](double-key-encryption.md)

- Para los archivos de Word, Excel y PowerPoint, SharePoint y OneDrive reconocen la etiqueta y ahora pueden procesar el contenido del archivo cifrado.

- Cuando los usuarios descargan o acceden a estos archivos desde SharePoint o OneDrive, la etiqueta de confidencialidad y cualquier configuración de cifrado de la etiqueta se aplican y permanecen en el archivo, dondequiera que se almacene. Asegúrese de proporcionar instrucciones al usuario para usar solo etiquetas para proteger documentos. Para obtener más información, vea [Information Rights Management (IRM) options and sensitivity labels](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Cuando los usuarios cargan archivos etiquetados y cifrados en SharePoint o OneDrive, deben tener al menos derechos de vista en esos archivos. Por ejemplo, pueden abrir los archivos fuera de SharePoint. Si no tienen este derecho de uso mínimo, la carga se realiza correctamente, pero el servicio no reconoce la etiqueta y no puede procesar el contenido del archivo.

- Use Office para la web (Word, Excel, PowerPoint) para abrir y editar archivos de Office que tienen etiquetas de confidencialidad que aplican cifrado. Se aplican los permisos asignados con el cifrado. También puede usar el [etiquetado automático](apply-sensitivity-label-automatically.md) para estos documentos.

- Los usuarios externos pueden tener acceso a documentos etiquetados con cifrado mediante cuentas invitadas. Para obtener más información, vea [Support for external users and labeled content](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content). 

- La exhibición de documentos electrónicos de Office 365 admite la búsqueda de texto completo para estos archivos y las directivas de prevención de pérdida de datos (DLP) admiten contenido en estos archivos.

> [!NOTE]
> Si el cifrado se ha aplicado con una clave local (una topología de administración de claves a menudo denominada "mantener su propia clave" o HYOK) o mediante cifrado de doble [clave,](double-key-encryption.md)el comportamiento del servicio para procesar el contenido del archivo no cambia. Por lo tanto, para estos archivos, la coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda y otras características de colaboración no funcionarán.
>
> El comportamiento de SharePoint y OneDrive tampoco cambia para los archivos existentes en estas ubicaciones que están etiquetados con cifrado mediante una sola clave basada en Azure. Para que estos archivos se beneficien de las nuevas funcionalidades después de habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, los archivos deben descargarse y cargarse de nuevo o editarse.

Después de habilitar etiquetas de confidencialidad para archivos [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) de Office en SharePoint y OneDrive, hay tres nuevos eventos de auditoría disponibles para supervisar etiquetas de confidencialidad que se aplican a documentos en SharePoint y OneDrive:
- **Etiqueta de confidencialidad aplicada al archivo**
- **Se ha cambiado la etiqueta de confidencialidad aplicada al archivo**
- **Etiqueta de confidencialidad eliminada del sitio**

Vea el siguiente vídeo (sin audio) para ver las nuevas funcionalidades en acción:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Siempre tiene la opción de deshabilitar las etiquetas de confidencialidad de los archivos de Office en SharePoint y OneDrive[(no](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)participar) en cualquier momento.

Si actualmente está protegiendo documentos en SharePoint mediante SharePoint Information Rights Management (IRM), asegúrese de comprobar la sección Administración de derechos de información [(IRM)](#sharepoint-information-rights-management-irm-and-sensitivity-labels) de SharePoint y etiquetas de confidencialidad en esta página. 

## <a name="requirements"></a>Requisitos

Estas nuevas funcionalidades solo funcionan con [etiquetas de](sensitivity-labels.md) confidencialidad. Si actualmente tiene etiquetas de Azure Information Protection, migre primero a etiquetas de confidencialidad para que pueda habilitar estas características para los nuevos archivos que cargue. Para obtener más información acerca de este proceso, consulte [Cómo migrar las etiquetas de Azure Information Protection a etiquetas de confidencialidad unificadas](/azure/information-protection/configure-policy-migrate-labels)

Usa la versión 19.002.0121.0008 o posterior de la aplicación de sincronización de OneDrive en Windows y la versión 19.002.0107.0008 o posterior en Mac. Ambas versiones se lanzaron el 28 de enero de 2019 y actualmente se lanzan a todos los anillos. Para obtener más información, vea las [notas de la versión de OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Después de habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, se pedirá a los usuarios que ejecuten una versión anterior de la aplicación de sincronización que la actualicen.

## <a name="limitations"></a>Limitaciones

- SharePoint y OneDrive no aplican automáticamente etiquetas de confidencialidad a archivos existentes que ya haya cifrado con etiquetas de Azure Information Protection. En su lugar, para que las características funcionen después de habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, complete estas tareas:
    
    1. Asegúrese de haber migrado las etiquetas de [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) [Azure Information Protection](/azure/information-protection/configure-policy-migrate-labels) a etiquetas de confidencialidad y publicarlas desde el Centro de cumplimiento de Microsoft 365 o el Centro de administración de etiquetado equivalente.
    2. Descargue los archivos y, a continuación, cárbalos en SharePoint.

- SharePoint y OneDrive no pueden procesar archivos cifrados cuando la etiqueta que aplicó el cifrado tiene cualquiera de las siguientes [configuraciones para el cifrado:](encryption-sensitivity-labels.md#configure-encryption-settings)
    - **Permitir que los usuarios asignen permisos cuando apliquen la etiqueta** y la casilla **En Word, PowerPoint y Excel, pedir a los usuarios que especifiquen permisos** seleccionada. Esta configuración a veces se conoce como "permisos definidos por el usuario".
    - **El acceso del usuario al contenido expira** establecido en un valor distinto de **Nunca**.
    - **Cifrado de clave doble** seleccionado.
    
    Para las etiquetas con cualquiera de estas configuraciones de cifrado, las etiquetas no se muestran a los usuarios de Office para la web. Además, las nuevas funcionalidades no se pueden usar con documentos etiquetados que ya tienen esta configuración de cifrado. Por ejemplo, estos documentos no se devolverán en los resultados de búsqueda, incluso si se actualizan.

- Los usuarios pueden experimentar retrasos al poder abrir documentos cifrados en el siguiente escenario guardar como: con una versión de escritorio de Office, un usuario elige Guardar como para un documento que tiene una etiqueta de confidencialidad que aplica cifrado. El usuario selecciona SharePoint o OneDrive para la ubicación y, a continuación, intenta abrir inmediatamente ese documento en Office para la web. Si el servicio sigue procesando el cifrado, el usuario ve un mensaje que indica que el documento debe abrirse en su aplicación de escritorio. Si lo intentan de nuevo en un par de minutos, el documento se abre correctamente en Office para la web. 

- Para documentos cifrados, no se admite la impresión.

- Para un documento cifrado que concede permisos de edición a un usuario, la copia no se puede bloquear en las versiones web de las aplicaciones de Office.

- De forma predeterminada, las aplicaciones de escritorio de Office y las aplicaciones móviles no admiten la co-autoría de archivos etiquetados con cifrado. Estas aplicaciones siguen abierto archivos etiquetados y cifrados en modo de edición exclusiva.
    
    > [!NOTE]
    > La co-autoría ahora se admite en versión preliminar. Para obtener más información, vea [Enable co-authoring for files encrypted with sensitivity labels](sensitivity-labels-coauthoring.md).

- Si un administrador cambia la configuración de una etiqueta publicada que ya se ha aplicado a los archivos descargados en el cliente de sincronización de los usuarios, es posible que los usuarios no puedan guardar los cambios que realicen en el archivo en su carpeta de Sincronización de OneDrive. Este escenario se aplica a los archivos etiquetados con cifrado y también cuando el cambio de etiqueta es de una etiqueta que no apliquen cifrado a una etiqueta que aplique cifrado. Los usuarios ven [un círculo rojo con un error de](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)icono de cruz blanca y se les pide que guarden nuevos cambios como una copia independiente. En su lugar, pueden cerrar y volver a abrir el archivo o usar Office para la web.

- Si un documento con etiqueta se carga en SharePoint o OneDrive y la etiqueta aplica cifrado mediante una cuenta de un nombre de entidad de seguridad de servicio, el documento no se puede abrir en Office para la web. Entre los escenarios de ejemplo se incluyen Microsoft Cloud App Security y un archivo enviado a Teams por correo electrónico.

- Los usuarios pueden experimentar problemas de guardado después de desconectarse o en modo de suspensión cuando, en lugar de usar Office para la web, usan las aplicaciones de escritorio y móviles para Word, Excel o PowerPoint. Para estos usuarios, cuando reanudan la sesión de la aplicación de Office e intentan guardar los cambios, ven un mensaje de error de carga con una opción para guardar una copia en lugar de guardar el archivo original. 

- Los documentos cifrados de las siguientes maneras no se pueden abrir en Office para la web:
    - Cifrado que usa una clave local ("mantener su propia clave" o HYOK)
    - Cifrado que se aplicó mediante [el cifrado de doble clave](double-key-encryption.md)
    - Cifrado que se aplicó independientemente de una etiqueta, por ejemplo, aplicando directamente una plantilla de protección de Rights Management.

- Las [etiquetas configuradas para otros idiomas](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-center-powershell) no son compatibles y solo muestran el idioma original.

- Las capturas de pantalla no se pueden evitar para documentos cifrados. Para obtener más información, vea [Can Rights Management prevent screen captures?](/azure/information-protection/faqs-rms#can-rights-management-prevent-screen-captures)

- Si elimina una etiqueta que se ha aplicado a un documento en SharePoint o OneDrive, en lugar de quitar la etiqueta de la directiva de etiqueta aplicable, el documento cuando se descargue no se etiquetará ni se cifrará. En comparación, si el documento etiquetado se almacena fuera de SharePoint o OneDrive, el documento permanece cifrado si se elimina la etiqueta. Tenga en cuenta que aunque puede eliminar etiquetas durante una fase de prueba, es muy raro eliminar una etiqueta en un entorno de producción.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Cómo habilitar etiquetas de confidencialidad para SharePoint y OneDrive (participación)

Puede habilitar las nuevas funcionalidades con el Centro de cumplimiento de Microsoft 365 o con PowerShell. Al igual que con todos los cambios de configuración de inquilino para SharePoint y OneDrive, el cambio tarda unos 15 minutos en tener efecto.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Usar el Centro de cumplimiento para habilitar la compatibilidad con etiquetas de confidencialidad

Esta opción es la forma más sencilla de habilitar etiquetas de confidencialidad para SharePoint y OneDrive, pero debe iniciar sesión como administrador global para el inquilino.

1. Inicie sesión en el Centro [de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) como administrador global y vaya a Protección de información **de**  >  **soluciones**
    
    Si no ve esta opción inmediatamente, primero seleccione **Mostrar todo**. 

2. Si ve un mensaje para activar la capacidad de procesar contenido en archivos en línea de Office, **seleccione Activar ahora**:
    
    ![Botón Activar ahora para habilitar etiquetas de confidencialidad para Office Online](../media/sensitivity-labels-turn-on-banner.png)
    
    El comando se ejecuta inmediatamente y cuando se actualiza la página, ya no verá el mensaje ni el botón.

> [!NOTE]
> Si tiene Microsoft 365 Multi-Geo, debe usar PowerShell para habilitar estas funcionalidades para todas las ubicaciones geográficas. Consulte la siguiente sección para obtener detalles.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Usar PowerShell para habilitar la compatibilidad con etiquetas de confidencialidad

Como alternativa al uso del centro de cumplimiento, puede habilitar la compatibilidad con etiquetas de confidencialidad mediante el cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) de PowerShell de SharePoint Online. 

Si tiene Microsoft 365 Multi-Geo, debe usar PowerShell para habilitar esta compatibilidad para todas las ubicaciones geográficas.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Preparar el Shell de administración de SharePoint Online

Antes de ejecutar el comando de PowerShell para habilitar etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, asegúrese de que está ejecutando El Shell de administración de SharePoint Online versión 16.0.19418.12000 o posterior. Si ya tiene la versión más reciente, puede pasar al [siguiente procedimiento](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) para ejecutar el comando de PowerShell.

1. Si tiene instalada una versión anterior de Shell de SharePoint Online Management de la galería de PowerShell, puede actualizar el módulo ejecutando el siguiente cmdlet.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, si ha instalado una versión anterior del Shell de administración de SharePoint  Online desde el Centro de descarga de Microsoft, también puede ir a Agregar o quitar programas y desinstalar el Shell de administración de SharePoint Online.

3. En un explorador web, vaya a la página del centro de descargas y [Descargue el Shell más reciente de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Seleccione el idioma y, a continuación, haga clic en **Descargar**.

5. Elija entre el archivo .msi x64 y x86. Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si ejecuta la versión de 32 bits. Si no lo sabes, consulta ¿Qué versión del sistema operativo [Windows ejecuto?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Después de descargar el archivo, ejecute el archivo y siga los pasos del Asistente para la instalación.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Ejecute el comando de PowerShell para habilitar la compatibilidad con etiquetas de confidencialidad

Para habilitar las nuevas funcionalidades, use el cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) con el *parámetro EnableAIPIntegration:*

1. Con una cuenta profesional o educativa que tenga privilegios de administrador global o administrador de SharePoint en Microsoft 365, conéctese a SharePoint. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    Nota: Si tiene Microsoft 365 Multi-Geo, use el parámetro -Url con [Connect-SPOService](/powershell/module/sharepoint-online/connect-sposervice)y especifique la dirección URL del sitio del Centro de administración de SharePoint Online para una de las ubicaciones geográficas.

2. Ejecute el siguiente comando y presione **Y** para confirmar:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Para Microsoft 365 Multi-Geo: repita los pasos 1 y 2 para cada una de las ubicaciones geográficas restantes.

## <a name="publishing-and-changing-sensitivity-labels"></a>Publicación y cambio de etiquetas de confidencialidad

Cuando use etiquetas de confidencialidad con SharePoint y OneDrive, tenga en cuenta que debe permitir el tiempo de replicación al publicar nuevas etiquetas de confidencialidad o actualizar las etiquetas de confidencialidad existentes. Esto es especialmente importante para las nuevas etiquetas que aplican cifrado.

Por ejemplo: creas y publicas una nueva etiqueta de confidencialidad que aplica cifrado y aparece muy rápidamente en la aplicación de escritorio de un usuario. El usuario aplica esta etiqueta a un documento y, a continuación, la carga en SharePoint o OneDrive. Si la replicación de etiquetas no se ha completado para el servicio, las nuevas funcionalidades no se aplicarán a ese documento al cargarse. Como resultado, el documento no se devolverá en la búsqueda ni en la exhibición de documentos electrónicos y el documento no se puede abrir en Office para la web.  

Los siguientes cambios se replican en una hora: etiquetas de confidencialidad nuevas y eliminadas, y configuración de directiva de etiquetas de confidencialidad que incluyen qué etiquetas están en la directiva.

Los siguientes cambios se replican en 24 horas: cambios en la configuración de etiquetas de confidencialidad de las etiquetas existentes.

Dado que el retraso de replicación es de solo una hora para las nuevas etiquetas de confidencialidad, es poco probable que se ejecute en el escenario del ejemplo. Pero, como medida de seguridad, se recomienda publicar nuevas etiquetas en unos pocos usuarios de prueba primero, esperar una hora y, a continuación, comprobar el comportamiento de la etiqueta en SharePoint y OneDrive. Como paso final, haz que la etiqueta esté disponible para más usuarios agregando más usuarios a la directiva de etiqueta existente o agrega la etiqueta a una directiva de etiqueta existente para los usuarios estándar. En el momento en que los usuarios estándar ven la etiqueta, ya se ha sincronizado con SharePoint y OneDrive.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) y etiquetas de confidencialidad

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) es una tecnología anterior para proteger los archivos en el nivel de lista y biblioteca mediante la aplicación de cifrado y restricciones cuando se descargan archivos. Esta tecnología de protección anterior está diseñada para impedir que los usuarios no autorizados abran el archivo mientras están fuera de SharePoint.

En comparación, las etiquetas de confidencialidad proporcionan la configuración de protección de los marcados visuales (encabezados, pies de página, marcas de agua) además del cifrado. La configuración de cifrado [](/azure/information-protection/configure-usage-rights) admite toda la gama de derechos de uso para restringir lo que los usuarios pueden hacer con el contenido y se admiten las mismas etiquetas de confidencialidad para [muchos escenarios.](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels) El uso del mismo método de protección con una configuración coherente entre cargas de trabajo y aplicaciones da como resultado una estrategia de protección coherente.

Sin embargo, puede usar ambas soluciones de protección juntos y el comportamiento es el siguiente: 

- Si carga un archivo con una etiqueta de confidencialidad que aplica cifrado, SharePoint no puede procesar el contenido de estos archivos por lo que la coautoría, la exhibición de documentos electrónicos, DLP y la búsqueda no son compatibles con estos archivos.

- Si etiqueta un archivo con Office para la web, se aplicará cualquier configuración de cifrado de la etiqueta. Para estos archivos, se admite la coautoría, la exhibición de documentos electrónicos, DLP y la búsqueda.

- Si descarga un archivo etiquetado mediante Office para la web, la etiqueta se conserva y se aplica cualquier configuración de cifrado de la etiqueta en lugar de la configuración de restricción de IRM.

- Si descarga un archivo de Office o PDF que no está cifrado con una etiqueta de confidencialidad, se aplica la configuración de IRM.

- Si ha habilitado alguna de las opciones adicionales de la biblioteca IRM, que incluyen impedir que los usuarios carguen documentos que no sean compatibles con IRM, se aplicará esta configuración.

Con este comportamiento, puede estar seguro de que todos los archivos Office y PDF están protegidos contra el acceso no autorizado si se descargan, incluso si no están etiquetados. Sin embargo, los archivos etiquetados que se cargan no se beneficiarán de las nuevas funcionalidades.


## <a name="search-for-documents-by-sensitivity-label"></a>Buscar documentos por etiqueta de confidencialidad

Use la propiedad administrada **InformationProtectionLabelId** para buscar todos los documentos de SharePoint o OneDrive que tengan una etiqueta de confidencialidad específica. Use la siguiente sintaxis: `InformationProtectionLabelId:<GUID>`

Por ejemplo, para buscar todos los documentos etiquetados como "Confidencial" y esa etiqueta tiene un GUID de "8faca7b8-8d20-48a3-8ea2-0f96310a848e", en el cuadro de búsqueda, escriba:

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`    

Para obtener los GUID de las etiquetas de confidencialidad, use el cmdlet [Get-Label:](/powershell/module/exchange/get-label)    

1. En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento de Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
   
    Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:    

2. A continuación, ejecute el siguiente comando:  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

Para obtener más información acerca del uso de propiedades administradas, vea [Manage the search schema in SharePoint](/sharepoint/manage-search-schema).

## <a name="remove-encryption-for-a-labeled-document"></a>Quitar el cifrado de un documento etiquetado

Es posible que haya raras ocasiones en las que un administrador de SharePoint necesite quitar el cifrado de un documento almacenado en SharePoint. Cualquier usuario que tenga asignado el derecho de uso de [Rights Management](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) de Exportar o Control total para ese documento puede quitar el cifrado aplicado por el servicio Azure Rights Management de Azure Information Protection. Por ejemplo, los usuarios con cualquiera de estos derechos de uso pueden reemplazar una etiqueta que aplica cifrado con una etiqueta sin cifrado. Como alternativa, un [superusual](/azure/information-protection/configure-super-users) podría descargar el archivo y guardar una copia local sin el cifrado.

Como alternativa, un administrador global o un administrador de [SharePoint](/sharepoint/sharepoint-admin-role) pueden ejecutar el cmdlet [Unlock-SPOSensitivityLabelEncryptedFile,](/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) que quita tanto la etiqueta de confidencialidad como el cifrado. Este cmdlet se ejecuta incluso si el administrador no tiene permisos de acceso al sitio o archivo, o si el servicio Azure Rights Management no está disponible. 

Por ejemplo:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Requisitos:

- Shell de administración de SharePoint Online versión 16.0.20616.12000 o posterior.

- El cifrado se ha aplicado mediante una etiqueta de confidencialidad con la configuración de cifrado definida por el administrador (la configuración de etiqueta [Asignar permisos ahora).](encryption-sensitivity-labels.md#assign-permissions-now) [El cifrado de clave](encryption-sensitivity-labels.md#double-key-encryption) doble no es compatible con este cmdlet.

El texto de justificación [](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) se agrega al evento de auditoría de **la** etiqueta de confidencialidad Quitado del archivo y la acción de descifrado también se registra en el registro de uso de protección de [Azure Information Protection](/azure/information-protection/log-analyze-usage).

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Cómo deshabilitar etiquetas de confidencialidad para SharePoint y OneDrive (no participar)

Si deshabilita estas nuevas funcionalidades, los archivos que cargó después de habilitar las etiquetas de confidencialidad para SharePoint y OneDrive seguirán estando protegidos por la etiqueta porque la configuración de etiquetas se sigue aplicando. Al aplicar etiquetas de confidencialidad a los nuevos archivos después de deshabilitar estas nuevas funcionalidades, la búsqueda de texto completo, la exhibición de documentos electrónicos y la coautoría ya no funcionarán.

Para deshabilitar estas nuevas funcionalidades, debe usar PowerShell. Mediante el Shell de administración de SharePoint Online y el cmdlet [Set-SPOTenant,](/powershell/module/sharepoint-online/set-spotenant) especifique el mismo parámetro *EnableAIPIntegration* como se describe en la sección [Usar PowerShell](#use-powershell-to-enable-support-for-sensitivity-labels) para habilitar la compatibilidad con etiquetas de confidencialidad. Pero esta vez, establece el valor del parámetro en false y presiona **Y** para confirmar:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Si tiene Microsoft 365 Multi-Geo, debe ejecutar este comando para cada una de las ubicaciones geográficas.

## <a name="next-steps"></a>Siguientes pasos

Después de habilitar etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive, considere la posibilidad de etiquetar automáticamente estos archivos mediante directivas de etiquetado automático. Para obtener más información, vea [Apply a sensitivity label to content automatically](apply-sensitivity-label-automatically.md).

¿Necesita compartir los documentos etiquetados y cifrados con personas fuera de su organización?  Consulte [Compartir documentos cifrados con usuarios externos](sensitivity-labels-office-apps.md#sharing-encrypted-documents-with-external-users).