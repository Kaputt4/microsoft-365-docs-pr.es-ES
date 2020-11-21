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
ms.openlocfilehash: 0feb98c6a0040ad67b4607062abdf0be5b5fbdb8
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376333"
---
# <a name="enable-sensitivity-labels-for-office-files-in-sharepoint-and-onedrive"></a>Habilitar etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Antes de habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, no puede aplicar las [etiquetas de confidencialidad](sensitivity-labels.md) en Office en la Web. No ve el botón de **confidencialidad** en la cinta o el nombre de etiqueta aplicado en la barra de estado. Además, si usa aplicaciones de escritorio para etiquetar los archivos y guardarlos en SharePoint o en OneDrive, el servicio no puede procesar el contenido de estos archivos si la etiqueta aplicó el cifrado. La coautoría, la exhibición de documentos electrónicos, la prevención de pérdida de datos, la búsqueda y otras características de colaboración no funcionarán en estas circunstancias.

Al habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, todas estas funcionalidades están habilitadas. Además de mostrar las etiquetas de confidencialidad a los usuarios, para los archivos nuevos y modificados que tengan una etiqueta de sensibilidad aplicada que incluya cifrado con una clave basada en la nube (y que no use el [cifrado de doble clave](double-key-encryption.md)):

- Para los archivos de Word, Excel y PowerPoint, SharePoint y OneDrive reconocen la etiqueta y ahora pueden procesar el contenido del archivo cifrado.

- Al descargar o tener acceso a estos archivos desde SharePoint o OneDrive, la etiqueta de confidencialidad y la configuración de cifrado de la etiqueta se aplican y permanecen en el archivo, dondequiera que se almacenen. Asegúrese de proporcionar a los usuarios las instrucciones para que solo usen etiquetas para proteger documentos. Para obtener más información, consulte [Opciones de Information Rights Management (IRM) y las etiquetas de confidencialidad](sensitivity-labels-office-apps.md#information-rights-management-irm-options-and-sensitivity-labels).

- Cuando los usuarios cargan archivos cifrados y etiquetados en SharePoint o OneDrive, deben tener, como mínimo, derechos de visualización en estos archivos. Por ejemplo, pueden abrir los archivos fuera de SharePoint. Si no tienen este derecho de uso mínimo, la carga es correcta pero el servicio no reconoce la etiqueta y no puede procesar el contenido del archivo.

- Use Office en la web (Word, Excel y PowerPoint) para abrir y editar archivos de Office con etiquetas de distinción que aplican el cifrado. Se aplican los permisos asignados al cifrado. Con Word en la web, también puede usar la etiqueta automática cuando edita estos documentos.

- Los usuarios externos pueden tener acceso a los documentos etiquetados con el cifrado mediante cuentas de invitado. Para obtener más información, consulte [compatibilidad con usuarios externos y con la etiqueta contenido](sensitivity-labels-office-apps.md#support-for-external-users-and-labeled-content). 

- Office 365 eDiscovery admite la búsqueda de texto completo para estos archivos y las directivas de prevención de pérdida de datos (DLP) admiten contenido en estos archivos.

> [!NOTE]
> Si el cifrado se ha aplicado con una clave local (una topología de administración de claves a menudo denominada "mantener su propia clave" o HYOK) o mediante el [cifrado de doble clave](double-key-encryption.md), el comportamiento de SharePoint para procesar el contenido del archivo no cambia.
>
> El comportamiento de SharePoint y OneDrive tampoco cambia para los archivos existentes en estas ubicaciones que se etiquetan con cifrado usando una sola clave basada en Azure. Para que estos archivos se beneficien de las nuevas funciones después de habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, los archivos deben descargarse y cargarse de nuevo, o bien editarse. Por ejemplo, se devolverán en los resultados de búsqueda y exhibición de documentos electrónicos.

Después de habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, hay disponibles tres nuevos [eventos de auditoría](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) para supervisar las etiquetas de confidencialidad que se aplican a los documentos en SharePoint y onedrive:
- **Etiqueta de confidencialidad aplicada al archivo**
- **Se ha cambiado la etiqueta de confidencialidad aplicada al archivo**
- **Etiqueta de confidencialidad eliminada del sitio**

Vea el siguiente vídeo (sin audio) para ver las nuevas capacidades en acción:

> [!VIDEO https://www.microsoft.com/videoplayer/embed//RE4ornZ]

Siempre tiene la opción de deshabilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive (no[participar](#how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out)) en cualquier momento.

Si actualmente está protegiendo documentos en SharePoint con SharePoint Information Rights Management (IRM), asegúrese de comprobar la sección [SharePoint Information Rights Management (IRM) y las etiquetas de confidencialidad](#sharepoint-information-rights-management-irm-and-sensitivity-labels) en esta página. 

## <a name="requirements"></a>Requirements

Estas nuevas funciones funcionan sólo con las [etiquetas de confidencialidad](sensitivity-labels.md) . Si tiene etiquetas de Azure Information Protection, primero deberá migrarlas a las etiquetas de confidencialidad para que pueda habilitarlas para los nuevos archivos que cargue. Para obtener instrucciones, consulte [Cómo migrar las etiquetas de Azure Information Protection a las etiquetas de confidencialidad unificadas](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels).

Use la versión 19.002.0121.0008 o posterior de la aplicación de sincronización de OneDrive en Windows y la versión 19.002.0107.0008 o posterior en Mac. Ambas versiones se han lanzado el 28 de enero de 2019 y actualmente están publicadas para todos los anillos. Para obtener más información, vea las notas de la [versión de OneDrive](https://support.office.com/article/845dcf18-f921-435e-bf28-4e24b95e5fc0). Después de habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, se pedirá a los usuarios que ejecuten una versión anterior de la aplicación de sincronización que la actualicen.

## <a name="limitations"></a>Limitaciones

- SharePoint y OneDrive no aplican automáticamente las etiquetas de confidencialidad a los archivos existentes que ya ha cifrado con las etiquetas de Azure Information Protection. En su lugar, para que las características funcionen después de habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, complete estas tareas:
    
    1. Asegúrese de que ha [migrado las etiquetas de Azure Information Protection a las](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) etiquetas de confidencialidad y las ha [publicado](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) en el centro de cumplimiento de Microsoft 365, o bien en el centro de administración de etiquetas equivalente.
    
    2. Descargue los archivos y, a continuación, cárguelos en SharePoint.

- SharePoint y OneDrive no pueden procesar archivos cifrados cuando la etiqueta que ha aplicado el cifrado tiene alguna de las siguientes [configuraciones para el cifrado](encryption-sensitivity-labels.md#configure-encryption-settings):
    - **Permitir que los usuarios asignen permisos cuando apliquen la etiqueta** y la casilla **en Word, PowerPoint y Excel, pedir a los usuarios que especifiquen permisos** está seleccionada. Esta configuración se denomina a veces "permisos definidos por el usuario".
    - El **acceso del usuario a las expiraciones de contenido** se establece en un valor que no es **nunca**.
    - Se selecciona el **cifrado doble de clave** .
    
    Para las etiquetas con cualquiera de estas configuraciones de cifrado, las etiquetas no se muestran a los usuarios en Office en la Web. Además, las nuevas funciones no se pueden usar con documentos etiquetados que ya tienen esta configuración de cifrado. Por ejemplo, estos documentos no se devolverán en los resultados de la búsqueda, aunque se actualicen.

- En el caso de un documento cifrado que concede permisos de edición a un usuario, no se puede bloquear la copia en las versiones web de las aplicaciones de Office.

- No se admite el sitio de seguimiento de documentos de Azure Information Protection.

- Las aplicaciones de escritorio y las aplicaciones móviles de Office no admiten la coautoría para los archivos etiquetados con cifrado. Estas aplicaciones continúan a la vez que los archivos identificados y cifrados se abren en el modo de edición exclusivo.

- Si un administrador cambia la configuración de una etiqueta publicada que ya se ha aplicado a los archivos descargados en el cliente de sincronización de los usuarios, es posible que los usuarios no puedan guardar los cambios que realicen en el archivo en su carpeta de sincronización de OneDrive. Este escenario se aplica a los archivos etiquetados con cifrado, y también cuando el cambio de la etiqueta es de una etiqueta que no ha aplicado el cifrado a una etiqueta que aplica el cifrado. Los usuarios ven un [círculo rojo con un error de icono en forma de cruz blanca](https://support.office.com/article/what-do-the-onedrive-icons-mean-11143026-8000-44f8-aaa9-67c985aa49b3)y se les pide que guarden los cambios nuevos como una copia independiente. En su lugar, pueden cerrar y volver a abrir el archivo, o usar Office en la Web.

- Si se carga un documento con etiquetas en SharePoint o en OneDrive y la etiqueta aplicó el cifrado mediante una cuenta desde un nombre principal de servicio, el documento no se puede abrir en Office en la Web. Los escenarios de ejemplo incluyen Microsoft Cloud App Security y un archivo enviado a Teams por correo electrónico.

- Los usuarios pueden experimentar problemas de guardado después de pasarse sin conexión o a un modo de suspensión en lugar de usar Office para la web, usan las aplicaciones móviles y de escritorio de Word, Excel o PowerPoint. Para estos usuarios, cuando reanudan la sesión de la aplicación de Office y intentan guardar los cambios, ven un mensaje de error de carga con una opción para guardar una copia en lugar de guardar el archivo original. 

- Los documentos que se han cifrado de las maneras siguientes no se pueden abrir en Office en la web:
    - Cifrado que usa una clave local ("conserve su propia clave" o HYOK)
    - Cifrado que se aplicó mediante el [cifrado de doble clave](double-key-encryption.md)
    - Cifrado que se aplicó de forma independiente de una etiqueta, por ejemplo, aplicando directamente una plantilla de protección de administración de derechos.

- Si elimina una etiqueta que se ha aplicado a un documento en SharePoint o en OneDrive, en lugar de quitar la etiqueta de la Directiva de etiqueta aplicable, el documento no se etiquetará ni cifrará en el documento cuando se descargue. En comparación, si el documento etiquetado se almacena fuera de SharePoint o de OneDrive, el documento permanece cifrado si se elimina la etiqueta. Tenga en cuenta que, aunque puede eliminar etiquetas durante una fase de pruebas, es muy raro eliminar una etiqueta en un entorno de producción.

## <a name="how-to-enable-sensitivity-labels-for-sharepoint-and-onedrive-opt-in"></a>Cómo habilitar las etiquetas de confidencialidad para SharePoint y OneDrive (participar)

Puede habilitar las nuevas funciones con el centro de cumplimiento de Microsoft 365 o con PowerShell. Al igual que con todos los cambios de configuración a nivel de inquilino para SharePoint y OneDrive, los cambios tardan unos 15 minutos en surtir efecto.

### <a name="use-the-compliance-center-to-enable-support-for-sensitivity-labels"></a>Usar el centro de cumplimiento para habilitar la compatibilidad con las etiquetas de confidencialidad

Esta opción es la forma más sencilla de habilitar las etiquetas de confidencialidad para SharePoint y OneDrive, pero debe iniciar sesión como administrador global de su espacio empresarial.

1. Inicie sesión en el [centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/) como administrador global y vaya a **soluciones**  >  **Information Protection**
    
    Si no ve esta opción inmediatamente, primero seleccione **Mostrar todo**. 

2. Si ve un mensaje para activar la capacidad de procesar contenido en archivos de Office Online, seleccione **Activar ahora**:
    
    ![Activar ahora el botón para habilitar las etiquetas de confidencialidad de Office Online](../media/sensitivity-labels-turn-on-banner.png)
    
    El comando se ejecuta inmediatamente y la próxima vez que se actualiza la página, ya no verá el mensaje o el botón.

> [!NOTE]
> Si tiene Microsoft 365 multigeográfico, debe usar PowerShell para habilitar estas funcionalidades para todas las ubicaciones geográficas. Consulte la siguiente sección para obtener detalles.

### <a name="use-powershell-to-enable-support-for-sensitivity-labels"></a>Usar PowerShell para habilitar la compatibilidad con las etiquetas de confidencialidad

Como alternativa al uso del centro de cumplimiento, puede habilitar la compatibilidad con las etiquetas de confidencialidad mediante el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) de PowerShell de SharePoint Online. 

Si tiene Microsoft 365 multigeográfico, debe usar PowerShell para habilitar esta compatibilidad para todas las ubicaciones geográficas.

#### <a name="prepare-the-sharepoint-online-management-shell"></a>Preparar el shell de administración de SharePoint Online

Antes de ejecutar el comando de PowerShell para habilitar las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, asegúrese de que está ejecutando la versión 16.0.19418.12000 o posterior del shell de administración de SharePoint Online. Si ya tiene la versión más reciente, puede pasar al [siguiente procedimiento](#run-the-powershell-command-to-enable-support-for-sensitivity-labels) para ejecutar el comando de PowerShell.

1. Si tiene instalada una versión anterior de Shell de SharePoint Online Management de la galería de PowerShell, puede actualizar el módulo ejecutando el siguiente cmdlet.

    ```PowerShell
    Update-Module -Name Microsoft.Online.SharePoint.PowerShell
    ```

2. Como alternativa, si ha instalado una versión anterior del shell de administración de SharePoint Online desde el centro de descarga de Microsoft, también puede ir a **Agregar o quitar programas** y desinstalar el shell de administración de SharePoint Online.

3. En un explorador web, vaya a la página del centro de descargas y [Descargue el Shell más reciente de administración de SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

4. Seleccione el idioma y, a continuación, haga clic en **Descargar**.

5. Elija entre el archivo .msi x64 y x86. Descargue el archivo x64 si ejecuta la versión de 64 bits de Windows o el archivo x86 si ejecuta la versión de 32 bits. Si no lo sabe, consulte ¿ [qué versión del sistema operativo Windows estoy ejecutando?](https://support.microsoft.com/help/13443/windows-which-operating-system)

6. Una vez que haya descargado el archivo, ejecute el archivo y siga los pasos del Asistente para la instalación.

#### <a name="run-the-powershell-command-to-enable-support-for-sensitivity-labels"></a>Ejecutar el comando de PowerShell para habilitar la compatibilidad con las etiquetas de confidencialidad

Para habilitar las nuevas funciones, use el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) con el parámetro *EnableAIPIntegration* :

1. Con una cuenta profesional o educativa que tenga privilegios de administrador global o de administrador de SharePoint en Microsoft 365, conéctese a SharePoint. Para saber cómo hacerlo, consulte [Introducción al Shell de administración de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
    
    Nota: Si tiene Microsoft 365 multigeográfico, use el parámetro-URL con [Connect-SPOService](https://docs.microsoft.com/powershell/module/sharepoint-online/connect-sposervice)y especifique la dirección URL del sitio del centro de administración de SharePoint Online para una de las ubicaciones geográficas.

2. Ejecute el siguiente comando y presione **y** para confirmar:

    ```PowerShell
    Set-SPOTenant -EnableAIPIntegration $true
    ```
3. Para Microsoft 365 multi-geo: Repita los pasos 1 y 2 para cada una de las ubicaciones geográficas restantes.

## <a name="publishing-and-changing-sensitivity-labels"></a>Publicar y cambiar las etiquetas de confidencialidad

Cuando use etiquetas de confidencialidad con SharePoint y OneDrive, tenga en cuenta que debe permitir el tiempo de replicación cuando publique nuevas etiquetas de confidencialidad o actualice las etiquetas de confidencialidad existentes. Esto es especialmente importante para las etiquetas nuevas que aplican el cifrado.

Por ejemplo: cree y publique una nueva etiqueta de confidencialidad que aplique el cifrado y aparezca muy rápido en la aplicación de escritorio de un usuario. El usuario aplica esta etiqueta a un documento y, a continuación, lo carga en SharePoint o en OneDrive. Si no se ha completado la replicación de la etiqueta para el servicio, las nuevas funciones no se aplicarán a ese documento al cargarlo. Como resultado, el documento no se devolverá en la búsqueda ni en la exhibición de documentos electrónicos y el documento no se puede abrir en Office para la Web.  

Los cambios siguientes se replican en una hora: las etiquetas de sensibilidad nuevas y eliminadas y la configuración de la Directiva de la etiqueta de confidencialidad, que incluye las etiquetas que se encuentran en la Directiva.

Los siguientes cambios se replican en 24 horas: cambia la configuración de la etiqueta de confidencialidad de las etiquetas existentes.

Debido a que el retraso de replicación es sólo una hora para las nuevas etiquetas de confidencialidad, es poco probable que ejecute el escenario en el ejemplo. Pero, como medida de seguridad, se recomienda publicar etiquetas nuevas en solo unos pocos usuarios de prueba, esperar una hora y, a continuación, comprobar el comportamiento de la etiqueta en SharePoint y OneDrive. Como último paso, ponga la etiqueta a disposición de más usuarios agregando más usuarios a la Directiva de etiqueta existente o agregue la etiqueta a una directiva de etiqueta existente para los usuarios estándar. En el momento en que los usuarios estándar ven la etiqueta, ya se ha sincronizado con SharePoint y OneDrive.

## <a name="sharepoint-information-rights-management-irm-and-sensitivity-labels"></a>SharePoint Information Rights Management (IRM) y las etiquetas de confidencialidad

[SharePoint Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md) es una tecnología más antigua para proteger los archivos en el nivel de lista y biblioteca mediante la aplicación de cifrado y restricciones cuando se descargan los archivos. Esta tecnología de protección anterior está diseñada para impedir que los usuarios no autorizados abran el archivo mientras está fuera de SharePoint.

En comparación, las etiquetas de confidencialidad proporcionan la configuración de protección de los marcados visuales (encabezados, pies de página y marcas de agua), además del cifrado. La configuración de cifrado admite toda la gama de [derechos de uso](https://docs.microsoft.com/azure/information-protection/configure-usage-rights) para restringir lo que los usuarios pueden hacer con el contenido, y se admiten las mismas etiquetas de confidencialidad en [muchos escenarios](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels). Usar el mismo método de protección con una configuración coherente en todas las cargas de trabajo y aplicaciones da como resultado una estrategia de protección coherente.

Sin embargo, puede usar ambas soluciones de protección de forma conjunta y el comportamiento es el siguiente: 

- Si carga un archivo con una etiqueta de confidencialidad que aplica el cifrado, SharePoint no puede procesar el contenido de estos archivos para que estos archivos no admitan la coautoría, la exhibición de documentos electrónicos, la DLP y la búsqueda.

- Si etiqueta un archivo mediante Office en la web, se aplicará la configuración de cifrado de la etiqueta. Para estos archivos, se admite la coautoría, la exhibición de documentos electrónicos, la DLP y la búsqueda.

- Si descarga un archivo que se ha etiquetado con Office en la web, la etiqueta se conservará y se aplicará la configuración de cifrado de la etiqueta en lugar de la configuración de restricción de IRM.

- Si descarga un archivo de Office o PDF que no está cifrado con una etiqueta de confidencialidad, se aplica la configuración de IRM.

- Si ha habilitado cualquiera de las opciones de configuración adicionales de la biblioteca de IRM, lo que incluye evitar que los usuarios carguen documentos que no son compatibles con IRM, esta configuración se aplica.

Con este comportamiento, puede tener la certeza de que todos los archivos de Office y PDF están protegidos contra el acceso no autorizado si se descargan, aunque no estén etiquetados. Sin embargo, los archivos etiquetados que se cargan no se beneficiarán de las nuevas funciones.


## <a name="search-for-documents-by-sensitivity-label"></a>Buscar documentos por etiqueta de confidencialidad    

Use la propiedad administrada **InformationProtectionLabelId** para buscar todos los documentos en SharePoint o OneDrive que tienen una etiqueta de confidencialidad específica. Use la sintaxis siguiente: `InformationProtectionLabelId:<GUID>`

Por ejemplo, para buscar todos los documentos que se han etiquetado como "confidenciales", y esa etiqueta tiene un GUID de "8faca7b8-8d20-48a3-8ea2-0f96310a848e", en el cuadro de búsqueda, escriba:

`InformationProtectionLabelId: 8faca7b8-8d20-48a3-8ea2-0f96310a848e`    

Para obtener los GUID de las etiquetas de confidencialidad, use el cmdlet [Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label) :  

1. En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento de Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
   
    Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:    

2. A continuación, ejecute el siguiente comando:  

    ```powershell   
    Get-Label |ft Name, Guid    
    ``` 

Para obtener más información sobre el uso de propiedades administradas, vea [administrar el esquema de búsqueda en SharePoint](https://docs.microsoft.com/sharepoint/manage-search-schema).

## <a name="remove-encryption-for-a-labeled-document"></a>Quitar el cifrado de un documento con etiquetas

Puede haber ocasiones en las que un administrador de SharePoint necesite quitar el cifrado de un documento almacenado en SharePoint. Cualquier usuario que tenga el [derecho de uso](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) de la administración de derechos de exportación o control total asignado a ellos para ese documento puede quitar el cifrado que el servicio Azure Rights Management ha aplicado desde Azure Information Protection. Por ejemplo, los usuarios con cualquiera de estos derechos de uso pueden reemplazar una etiqueta que aplique cifrado con una etiqueta sin cifrado. Como alternativa, un [superusuario](https://docs.microsoft.com/azure/information-protection/configure-super-users) podría descargar el archivo y guardar una copia local sin cifrar.

Como alternativa, un administrador global o un [Administrador de SharePoint](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) puede ejecutar el cmdlet [Unlock-SPOSensitivityLabelEncryptedFile](https://docs.microsoft.com/powershell/module/sharepoint-online/unlock-sposensitivitylabelencryptedFile) , que quita tanto la etiqueta de confidencialidad como el cifrado. Este cmdlet se ejecuta incluso si el administrador no tiene permisos de acceso al sitio o archivo, o si el servicio Azure Rights Management no está disponible. 

Por ejemplo:

```powershell
Unlock-SPOSensitivityLabelEncryptedFile -FileUrl "https://contoso.com/sites/Marketing/Shared Documents/Doc1.docx" -JustificationText "Need to decrypt this file"
```

Requisitos:

- Shell de administración de SharePoint Online versión 16.0.20616.12000 o posterior.

- El cifrado se aplica mediante una etiqueta de confidencialidad con la configuración de cifrado definida por el administrador (la configuración de la etiqueta [asignar permisos ahora](encryption-sensitivity-labels.md#assign-permissions-now) ). El [cifrado de doble clave](encryption-sensitivity-labels.md#double-key-encryption) no es compatible con este cmdlet.

El texto de justificación se agrega al [evento de auditoría](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) de la etiqueta de **confidencialidad eliminada del archivo** y la acción de descifrado también se registra en el [registro de uso de protección de Azure Information Protection](https://docs.microsoft.com/azure/information-protection/log-analyze-usage).

## <a name="how-to-disable-sensitivity-labels-for-sharepoint-and-onedrive-opt-out"></a>Cómo deshabilitar las etiquetas de confidencialidad para SharePoint y OneDrive (no participar)

Si deshabilita estas nuevas capacidades, los archivos que cargó después de habilitar las etiquetas de confidencialidad para SharePoint y OneDrive seguirán protegidos por la etiqueta porque la configuración de la etiqueta se sigue aplicando. Al aplicar las etiquetas de confidencialidad a los archivos nuevos después de deshabilitar estas nuevas funciones, la búsqueda de texto completo, la exhibición de documentos electrónicos y la coautoría dejarán de funcionar.

Para deshabilitar estas nuevas funciones, debe usar PowerShell. Mediante el shell de administración de SharePoint Online y el cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenant) , especifique el mismo parámetro *EnableAIPIntegration* tal y como se describe en la sección [usar PowerShell para habilitar la compatibilidad con las etiquetas de confidencialidad](#use-powershell-to-enable-support-for-sensitivity-labels) . Pero esta vez, establezca el valor del parámetro en false y presione **y** para confirmar:

```PowerShell
Set-SPOTenant -EnableAIPIntegration $false
```

Si tiene Microsoft 365 multigeográfico, debe ejecutar este comando para cada una de las ubicaciones geográficas.

## <a name="next-steps"></a>Siguientes pasos

Una vez que haya habilitado las etiquetas de confidencialidad para los archivos de Office en SharePoint y OneDrive, considere la posibilidad de etiquetar automáticamente estos archivos mediante directivas de etiquetado automático. Para obtener más información, vea [aplicar una etiqueta de confidencialidad a contenido automáticamente](apply-sensitivity-label-automatically.md).
