---
title: Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom: admindeeplinkSPO
search.appverid:
- MOE150
- MET150
description: Usar etiquetas de confidencialidad para proteger el contenido en los sitios de SharePoint y Microsoft Teams, y los grupos de Microsoft 365.
ms.openlocfilehash: 39caee37f8bf8b2f885824bbdd12ca7b5b372e69
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320513"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Además de usar [etiquetas de confidencialidad](sensitivity-labels.md) para clasificar y proteger documentos y mensajes de correo electrónico, también puede usarlas para proteger el contenido en los siguientes contenedores: sitios de Microsoft Teams, grupos de Microsoft 365 ([anteriormente grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), y sitios de SharePoint. Para esta clasificación y protección de etiquetas, use la siguiente configuración de etiquetas:

- Privacidad (pública o privada) de los sitios de equipos y Grupos de Microsoft 365
- Acceso de usuarios externos
- Uso compartido externo desde sitios de SharePoint 
- Acceso desde dispositivos no administrados
- Contextos de autenticación (en versión preliminar)
- Vínculo de uso compartido predeterminado para un sitio de SharePoint (configuración solo de PowerShell)

> [!IMPORTANT]
> La configuración para dispositivos no administrados y contextos de autenticación funciona junto con el acceso condicional de Azure Active Directory. Debe configurar esta característica dependiente si desea usar una etiqueta de confidencialidad para esta configuración. Se incluye información adicional en las instrucciones siguientes.

Cuando aplica esta etiqueta de confidencialidad a un contenedor compatible, la etiqueta aplica automáticamente la clasificación y la configuración de protección establecida al sitio o al grupo.

Sin embargo, el contenido de estos contenedores no hereda las etiquetas para la clasificación y configuración de archivos y mensajes de correo electrónico, como las marcas visuales y el cifrado. Para que los usuarios puedan etiquetar sus documentos en los sitios de SharePoint o de grupos, asegúrese de [habilitar las etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

> [!NOTE]
> Las etiquetas de sensibilidad para contenedores no son compatibles con las Redes de entrega de contenido (CDNs) de Office 365.

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>Uso de etiquetas de confidencialidad para Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint

Antes de habilitar etiquetas de confidencialidad para contenedores y establecerlas para la nueva configuración, los usuarios pueden ver y aplicar etiquetas de confidencialidad en sus aplicaciones. Por ejemplo, en Word:

![Una etiqueta de sensibilidad que se muestra en la aplicación de escritorio de Word.](../media/sensitivity-label-word.png)

Después de habilitar y configurar las etiquetas de confidencialidad para los contenedores, los usuarios también pueden ver y aplicar etiquetas de confidencialidad a los sitios de grupo de Microsoft, los grupos de Microsoft 365 y los sitios de SharePoint. Por ejemplo, cuando crea un nuevo sitio de grupo desde SharePoint:

![Una etiqueta de sensibilidad al crear un sitio de equipo desde SharePoint.](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a>Cómo habilitar etiquetas de confidencialidad para contenedores y sincronizarlas

Si aún no ha habilitado etiquetas de confidencialidad para contenedores, siga estos pasos como un procedimiento de un solo uso:

1. Dado que esta característica usa la funcionalidad de Azure AD, siga las instrucciones de la documentación de Azure AD para habilitar la compatibilidad con etiquetas de confidencialidad: [Asignar etiquetas de confidencialidad a grupos de Microsoft 365 en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).

2. Ahora tiene que sincronizar sus etiquetas de confidencialidad en Azure AD. En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

   Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:

3. Después, ejecute el siguiente comando para asegurarse de que sus etiquetas de confidencialidad se pueden usar con los grupos de Microsoft 365:

    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-groups-and-site-settings"></a>Cómo configurar los grupos y las opciones de configuración del sitio

Una vez habilitadas las etiquetas de confidencialidad para los contenedores como se describe en la sección anterior, puede configurar los ajustes de protección para grupos y sitios en la configuración de las etiquetas de confidencialidad. Hasta que se habiliten las etiquetas de confidencialidad para contenedores, la configuración está visible, pero no puede configurarse.

1. Siga las instrucciones generales para [crear o editar una etiqueta de confidencialidad](create-sensitivity-labels.md#create-and-configure-sensitivity-labels) y asegúrese de que **Archivos y sitios** está seleccionada para el ámbito de la etiqueta: 
    
    ![Opciones de ámbito de etiquetas de confidencialidad para archivos y mensajes de correo electrónico.](../media/groupsandsites-scope-options-sensitivity-label.png)
    
    Cuando solo este ámbito para la etiqueta esté seleccionado, la etiqueta no se mostrará en las aplicaciones de Office que admiten etiquetas de confidencialidad y no se podrá aplicar a archivos y mensajes de correo electrónico. Tener esta separación de etiquetas puede ser útil tanto para los usuarios como para los administradores, pero también puede aumentar la complejidad de la implementación de la etiqueta.
    
    Por ejemplo, necesita revisar atentamente la [clasificación de etiquetas](sensitivity-labels.md#label-priority-order-matters), ya que SharePoint detecta cuándo se carga un documento con etiqueta en un sitio etiquetado. En este escenario, se generan automáticamente un evento de auditoría y un correo electrónico cuando el documento tiene una etiqueta de confidencialidad con mayor prioridad que la etiqueta del sitio. Para obtener más información, vea la sección [Auditoría de actividades de etiquetas de confidencialidad](#auditing-sensitivity-label-activities) en esta página. 

2. A continuación, en la página **Definir configuración de protección para grupos y sitios**, seleccione una o ambas opciones disponibles:
    
    - **Configuración de privacidad y acceso de usuarios externos** para establecer las opciones de configuración de **Privacidad** y **Acceso de usuarios externos**. 
    - **Configuración de uso compartido externo y acceso condicional** para controlar las configuraciones de **Controlar el uso compartido externo de los sitios de SharePoint etiquetados** y **Usar el acceso condicional de Azure AD para proteger los sitios de SharePoint etiquetados**.

3. Si seleccionó **Configuración de privacidad y acceso de usuarios externos**, configure las siguientes opciones:
    
    - **Privacidad**: mantenga la opción predeterminada **Público** si quiere que cualquier persona de su organización tenga acceso al sitio de grupo o al grupo al que se aplica esta etiqueta.
        
        Seleccione **Privado** si quiere que el acceso esté restringido solo a miembros aprobados de su organización.
        
        Seleccione **Ninguno** cuando desee proteger el contenido del contenedor mediante el uso de la etiqueta de confidencialidad, pero permita que los usuarios establezcan la configuración de privacidad ellos mismos.
        
        Las opciones **Pública** o **Privada** para establecen y bloquean la configuración de privacidad cuando aplica esta etiqueta al contenedor. La configuración elegida reemplaza cualquier configuración de privacidad anterior establecida para el equipo o grupo, y bloquea el valor de privacidad para que solo se pueda cambiar quitando primero la etiqueta de confidencialidad del contenedor. Después de quitar la etiqueta de confidencialidad, la configuración de privacidad de la etiqueta permanece y los usuarios ya pueden cambiarla de nuevo.
    
    - **Acceso de usuarios externos**: controla si el propietario del grupo puede [agregar invitados al grupo](/office365/admin/create-groups/manage-guest-access-in-groups).

4. Si seleccionó **configuración de uso compartido externo y acceso condicional**, ahora configure las siguientes opciones:
    
    - **Controlar el uso compartido externo desde sitios de SharePoint etiquetados**: seleccione esta opción para seleccionar el uso compartido externo para cualquier usuario, invitados nuevos y existentes, invitados existentes o solo para los usuarios de su organización. Para más información sobre esta configuración y opciones, consulte la documentación de SharePoint [Activar o desactivar el uso compartido externo de un sitio](/sharepoint/change-external-sharing-site).
    
    - **Usar el acceso condicional de Azure AD para proteger los sitios de SharePoint etiquetados**: seleccione esta opción solo si su organización la tiene configurada y está usando el [Acceso condicional de Azure Active Directory](/azure/active-directory/conditional-access/overview). A continuación, seleccione una de las siguientes opciones: 
    
        - **Determinar si los usuarios pueden acceder a los sitios de SharePoint desde dispositivos no administrados**: esta opción emplea la característica de SharePoint que usa el acceso condicional de Azure AD para bloquear o limitar el acceso a contenido de SharePoint y OneDrive desde dispositivos no administrados. Para obtener más información, consulte [Controlar el acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices) en la documentación de SharePoint. La opción que especifique para esta configuración de etiqueta constituye el equivalente a ejecutar un comando de PowerShell para un sitio, tal y como se describe en los pasos 3-5 en la sección de instrucciones de SharePoint [Bloquear o limitar el acceso a un sitio específico de SharePoint o a OneDrive](/sharepoint/control-access-from-unmanaged-devices#block-or-limit-access-to-a-specific-sharepoint-site-or-onedrive).
            
            Para obtener más información sobre la configuración, vea la opción [Más información sobre las dependencias para los dispositivos no administrados](#more-information-about-the-dependencies-for-the-unmanaged-devices-option) al final de esta sección.
            
        - **Elegir un contexto de autenticación existente**: actualmente en versión preliminar, esta opción le permite exigir condiciones de acceso más estrictas cuando los usuarios acceden a sitios de SharePoint que tienen esta etiqueta aplicada. Estas condiciones se aplican al seleccionar un contexto de autenticación existente que se ha creado y publicado para la implementación de acceso condicional de su organización. Si los usuarios no cumplen las condiciones configuradas o usan aplicaciones que no admiten contextos de autenticación, se les denegará el acceso.
            
            Para obtener más información de configuración, consulte [Más información sobre las dependencias de la opción de contexto de autenticación](#more-information-about-the-dependencies-for-the-authentication-context-option) al final de esta sección.
            
            Ejemplos de esta configuración de etiquetas:
            
             - Elija un contexto de autenticación que esté configurado para requerir la [autenticación multifactor (MFA)](/azure/active-directory/conditional-access/untrusted-networks). Después, esta etiqueta se aplica a un sitio de SharePoint que contiene elementos altamente confidenciales. Como resultado, cuando los usuarios de una red que no son de confianza intentan acceder a un documento de este sitio, ven la solicitud de MFA que deben completar para poder acceder al documento.
             
             - Elija un contexto de autenticación que esté configurado para las [directivas de condiciones de uso](/azure/active-directory/conditional-access/terms-of-use). Después, esta etiqueta se aplica a un sitio de SharePoint que contiene elementos que requieren la aceptación de términos de uso por motivos legales o de cumplimiento. Como resultado, cuando los usuarios intentan acceder a un documento de este sitio, ven un documento de términos de uso que deben aceptar para poder acceder al documento original.

> [!IMPORTANT]
> La configuración de sitio y grupo solo surte efecto al aplicar la etiqueta a un equipo, grupo o sitio. Si el [ámbito de la etiqueta](sensitivity-labels.md#label-scopes) incluye archivos y mensajes de correo electrónico, otras opciones de configuración de etiqueta, como el cifrado y la marcación de contenido, no se aplicarán a todo el contenido del equipo, grupo o sitio.

Si la etiqueta de confidencialidad aún no se ha publicado, publíquela [agregándola a una directiva de etiqueta de confidencialidad](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy). Los usuarios que tienen asignada una directiva de etiqueta de confidencialidad que incluye esta etiqueta podrán seleccionarla para sitios y grupos.

##### <a name="more-information-about-the-dependencies-for-the-unmanaged-devices-option"></a>Más información sobre la opción de dependencias para los dispositivos no administrados

Si no configura la directiva de acceso condicional dependiente para SharePoint tal y como se describe en [Utilizar las restricciones que exige la aplicación](/sharepoint/app-enforced-restrictions), la opción que especifique aquí no tendrá ningún efecto. Además, no tendrá ningún efecto si es menos restrictiva que una configuración establecida en el nivel de inquilino. Si ha configurado una opción de configuración a nivel de toda la organización para dispositivos no administrados, elija una configuración de etiqueta que sea igual o más restrictiva.

Por ejemplo, si la cuenta empresarial está configurada para **Permitir tan solo el acceso web limitado**, el valor de la etiqueta que permite el acceso total no tendrá ningún efecto, ya que es menos restrictivo. Para esta configuración a nivel de la cuenta empresarial, elija el valor de la etiqueta que permita bloquear el acceso (más restrictivo) o el valor de la etiqueta para acceso limitado (igual que la configuración de la cuenta empresarial).

Dado que puede configurar las opciones de configuración de SharePoint independientemente de la configuración de etiqueta, no hay ninguna comprobación en el asistente de etiquetas de confidencialidad que incluya las dependencias. Estas dependencias pueden configurarse después de crear y publicar la etiqueta, e incluso después de aplicarla. Sin embargo, si la etiqueta ya se ha aplicado, la configuración no tendrá efecto hasta que el usuario vuelva a autenticarse.

##### <a name="more-information-about-the-dependencies-for-the-authentication-context-option"></a>Más información sobre las dependencias de la opción de contexto de autenticación

Para que aparezca en la lista desplegable para seleccionar, es necesario crear, configurar y publicar contextos de autenticación como parte de la configuración de acceso a condiciones de Azure Active Directory. Para obtener más información e instrucciones, vea la sección [Configurar los contextos de autenticación](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#configure-authentication-contexts) en de la documentación de acceso condicional de Azure AD.

No todas las aplicaciones admiten contextos de autenticación. Si un usuario con una aplicación no compatible se conecta al sitio que está configurado para un contexto de autenticación, verá un mensaje de acceso denegado o se le pedirá que se autentique, pero se le rechazará. Las aplicaciones que admiten contextos de autenticación actualmente:

- Office para la Web, que incluye Outlook para la Web

- Microsoft Teams para Windows y macOS (excluye la aplicación web de Teams)

- Microsoft Planner

- Aplicaciones de Microsoft 365 para Word, Excel y PowerPoint; versiones mínimas:
    - Windows: 2103
    - macOS: 16.45.1202
    - iOS: 2.48.303
    - Android: 16.0.13924.10000

- Aplicaciones de Microsoft 365 para Outlook; versiones mínimas:
    - Windows: 2103
    - macOS: 16.45.1202
    - iOS: 4.2109.0
    - Android: 4.2025.1

- Aplicación de Sincronización de OneDrive, versiones mínimas:
    - Windows: 21.002
    - macOS: 21.002
    - iOS: Rolling out in 12.30
    - Android: aún no compatible

Limitaciones conocidas de esta versión preliminar:

- Para la aplicación de Sincronización de OneDrive, solo es compatible con OneDrive y no con otros sitios.

- Es posible que las siguientes características y aplicaciones no sean compatibles con los contextos de autenticación, por lo que le recomendamos que compruebe que siguen funcionando cuando un usuario accede correctamente a un sitio mediante un contexto de autenticación:
    
    - Flujos de trabajo que usan PowerApps o Power Automate
    - Aplicaciones de terceros

### <a name="configure-settings-for-the-default-sharing-link-type-for-a-site-by-using-powershell-advanced-settings"></a>Configuración de las opciones del tipo de vínculo de uso compartido predeterminado para un sitio mediante la configuración avanzada de PowerShell

Además de la configuración de etiquetas para sitios y grupos que puede configurar desde el centro de cumplimiento, también puede configurar el tipo de vínculo de uso compartido predeterminado para un sitio. Las etiquetas de confidencialidad de los documentos también se pueden configurar para un tipo de vínculo de uso compartido predeterminado. Esta configuración, que ayuda a evitar el uso compartido excesivo, se selecciona automáticamente cuando los usuarios seleccionan el botón **Compartir** en sus aplicaciones de Office. 

Para obtener más información e instrucciones, vea [Uso de las etiquetas de confidencialidad para configurar el tipo de vínculo de uso compartido predeterminado para sitios y documentos en SharePoint y OneDrive](sensitivity-labels-default-sharing-link.md).

## <a name="sensitivity-label-management"></a>Administración de etiquetas de confidencialidad

Use las siguientes instrucciones para crear, modificar o eliminar las etiquetas de confidencialidad configuradas para sitios y grupos.

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a>Crear y publicar etiquetas configuradas para sitios y grupos

Cuando se crea y se publica una nueva etiqueta de confidencialidad, los usuarios en los equipos, grupos y sitios pueden verla en un plazo de una hora. Sin embargo, si modifica una etiqueta existente, permita que pasen hasta 24 horas. Use las siguientes instrucciones para publicar una etiqueta para los usuarios establecida para la configuración de sitio y grupo:

1. Después de crear y configurar la etiqueta de confidencialidad, agréguela a una directiva de etiqueta que solo se aplique a algunos usuarios de prueba.

2. Espere a que se replique el cambio:

   - Nueva etiqueta: espere una hora.
   - Etiqueta existente: espere 24 horas.

3. Después de este período, utilice una de las cuentas de usuario de prueba para crear un equipo, un grupo de Microsoft 365 o un sitio de SharePoint con la etiqueta creada en el paso 1.

4. Si no se producen errores durante el proceso de creación, significa que es seguro publicar la etiqueta en todos los usuarios de su inquilino.

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a>Modificar las etiquetas publicadas que están configuradas para sitios y grupos

Como práctica recomendada, no cambie la configuración de sitio y grupo para una etiqueta de confidencialidad cuando se haya aplicado a equipos, grupos o sitios. Si lo hace, espere hasta 24 horas para que los cambios se repliquen en todos los contenedores que tienen la etiqueta aplicada.

Además, si los cambios incluyen la configuración **Acceso de usuarios externos**:

- La nueva configuración se aplica a los nuevos usuarios, pero no a los existentes. Por ejemplo, si esta configuración se seleccionó anteriormente y, como resultado, los usuarios invitados accedieron al sitio, estos usuarios invitados aún pueden acceder al sitio después de que esta configuración se borre en la configuración de la etiqueta.

- La configuración de privacidad de las propiedades de grupo hiddenMembership y roleEnabled no se actualiza.

### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a>Eliminar etiquetas publicadas que están configuradas para sitios y grupos

Si elimina una etiqueta de confidencialidad que tiene habilitada la configuración del sitio y del grupo, y esa etiqueta está incluida en una o más políticas de etiquetas, esta acción puede provocar fallas en la creación de nuevos equipos, grupos y sitios. Para evitar esta situación, utilice la siguiente guía:

1. Elimine la etiqueta de confidencialidad de todas las directivas de etiqueta que la incluyan.

2. Espere una hora.

3. Después de este período, pruebe a crear un equipo, grupo o sitio y compruebe que la etiqueta ya no es visible.

4. Si la etiqueta de confidencialidad no es visible, ya puede eliminarla de forma segura.

## <a name="how-to-apply-sensitivity-labels-to-containers"></a>Cómo aplicar etiquetas de confidencialidad a contenedores

Ya está listo para aplicar la etiqueta o las etiquetas de confidencialidad a los siguientes contenedores:

- [Grupo de Microsoft 365 en Azure AD](#apply-sensitivity-labels-to-microsoft-365-groups)
- [Sitio de grupo de Microsoft Teams](#apply-a-sensitivity-label-to-a-new-team)
- [Grupo de Microsoft 365 en Outlook en la Web](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [Sitio de SharePoint](#apply-a-sensitivity-label-to-a-new-site)

Puede usar PowerShell si necesita [aplicar una etiqueta de sensibilidad a varios sitios](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a>Aplicar etiquetas de confidencialidad a grupos de Microsoft 365

Ya está listo para aplicar la etiqueta o las etiquetas de confidencialidad a los grupos de Microsoft 365. Regrese a la documentación de Azure AD para obtener instrucciones:

- [Asignar una etiqueta a un grupo nuevo en Azure Portal](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

- [Asignar una etiqueta a un grupo existente en Azure Portal](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

- [Quitar una etiqueta a un grupo existente en Azure Portal](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)

### <a name="apply-a-sensitivity-label-to-a-new-team"></a>Aplicar una etiqueta de confidencialidad a un nuevo equipo

Los usuarios pueden seleccionar etiquetas de confidencialidad al crear nuevos equipos en Microsoft Teams. Al seleccionar la etiqueta en la lista desplegable **confidencialidad**, es posible que la configuración de privacidad cambie para reflejar la configuración de la etiqueta. En función de la configuración de acceso de usuarios externos que haya seleccionado para la etiqueta, los usuarios pueden o no, agregar al equipo personas de fuera de la organización.

[Más información sobre las etiquetas de confidencialidad para Teams](/microsoftteams/sensitivity-labels)

![La configuración de privacidad al crear un nuevo equipo.](../media/privacy-setting-new-team.png)

Después de crear el equipo, se muestra la etiqueta de confidencialidad en la esquina superior derecha de todos los canales.

![La etiqueta de confidencialidad se muestra en el equipo.](../media/privacy-setting-teams.png)

El servicio aplica automáticamente la misma etiqueta de confidencialidad al grupo de Microsoft 365 y al sitio de grupo de SharePoint conectado.

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a>Aplicar una etiqueta de confidencialidad a un nuevo grupo en Outlook en la Web

En Outlook en la Web, al crear un grupo, puede seleccionar o cambiar la opción **confidencialidad** para las etiquetas publicadas:

![Crear un grupo y seleccionar una opción en Confidencialidad.](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a>Aplicar una etiqueta de confidencialidad a un nuevo sitio

Los administradores y los usuarios finales pueden seleccionar las etiquetas de confidencialidad cuando [crean sitios de grupo y de comunicación modernos](/sharepoint/create-site-collection) y expandir la **configuración avanzada**:

![Crear un sitio y seleccionar una opción en Confidencialidad.](../media/sensitivity-label-new-communication-site.png)

En el cuadro desplegable se mostrarán los nombres de etiqueta de la selección, y en el icono de ayuda se mostrarán todos los nombres de etiqueta con la información sobre herramientas, que puede ayudar a los usuarios a determinar la etiqueta correcta que debe aplicar.

Cuando los usuarios exploren el sitio, podrán ver el nombre de la etiqueta y las directivas aplicadas. Por ejemplo, este sitio se ha etiquetado como **confidencial** y la configuración de privacidad se ha establecido en **privada**:

![Un sitio en el que se ha aplicado una etiqueta de confidencialidad.](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a>Usar PowerShell para aplicar una etiqueta de confidencialidad a varios sitios

Puede usar los cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) y [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant) con el parámetro *SensitivityLabel* desde el [Shell de SharePoint Online Management](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) actual para aplicar una etiqueta de confidencialidad a muchos sitios. Los sitios pueden ser cualquier colección de sitios de SharePoint o un sitio de OneDrive.

Asegúrese de que tiene la versión 16.0.19418.12000 o posterior del Shell de administración de SharePoint Online.

1. Abra una sesión de PowerShell con la opción **Ejecutar como administrador**.

2. Si no conoce el GUID de la etiqueta, vaya a: [Conectarse al PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/connect-to-scc-powershell) y obtenga la lista de etiquetas de confidencialidad y sus GUID.

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. Ahora, [conéctese a SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) y almacene su GUID de etiqueta como una variable. Por ejemplo:

   ```powershell
   $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
   ```

4. Cree una nueva variable que identifique varios sitios que tienen una cadena de identificación en común en su URL. Por ejemplo:

   ```powershell
   $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents"
   ```

5. Ejecute el siguiente comando para aplicar la etiqueta a estos sitios. Usando nuestros ejemplos:

   ```powershell
   $sites | ForEach-Object {Set-SPOTenant $_.url -SensitivityLabel $Id}
   ```

Esta serie de comandos le permite etiquetar varios sitios en el espacio empresarial con la misma etiqueta de confidencialidad y, por este motivo, puede usar el cmdlet Set-SPOTenant, en lugar del cmdlet Set-SPOSite que se usa para la configuración por sitio. Pero use el cmdlet Set-SPOSite cuando necesite aplicar una etiqueta diferente a sitios específicos repitiendo el comando siguiente en cada uno de estos sitios: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Ver y administrar etiquetas de confidencialidad en el centro de administración de SharePoint

Para ver, ordenar y buscar las etiquetas de confidencialidad aplicadas, use la página <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a> en el nuevo Centro de administración de SharePoint. Es posible que primero necesite agregar la columna **Confidencialidad:**

![La columna Confidencialidad en la página Sitios activos.](../media/manage-site-sensitivity-labels.png)

Para obtener más información sobre la administración de sitios desde la página Sitios activos, incluido cómo agregar una columna, vea [Administrar sitios en el nuevo centro de administración de SharePoint](/sharepoint/manage-sites-in-new-admin-center).

También puede cambiar y aplicar una etiqueta desde esta página:

1. Seleccione el nombre del sitio para abrir el panel de detalles.

2. Seleccione la pestaña **Directivas** y después, elija **Editar** para la configuración **Confidencialidad**.

3. En el panel **Editar configuración de confidencialidad** seleccione la etiqueta de confidencialidad que desea aplicar al sitio. A diferencia de las aplicaciones de usuario, donde las etiquetas de confidencialidad se pueden asignar a usuarios específicos, el Centro de administración muestra todas las etiquetas de confidencialidad para el espacio empresarial. Después de elegir una etiqueta, seleccione **Guardar**.

## <a name="support-for-sensitivity-labels"></a>Compatibilidad con etiquetas de confidencialidad.

Cuando use centros de administración que admitan etiquetas de confidencialidad, verá todas las etiquetas de confidencialidad del espacio empresarial. En comparación, las aplicaciones y servicios de usuario que filtran etiquetas de confidencialidad según las directivas de publicación pueden provocar que veas un subconjunto de esas etiquetas.

Las siguientes aplicaciones y servicios son compatibles con etiquetas de confidencialidad establecidas para la configuración de sitio y grupo:

- Centros de administración:

  - Centro de administración de SharePoint
  - Centro de administración de Teams
  - Portal de Azure Active Directory
  - Centro de administración de Microsoft 365
  - Centro de cumplimiento de Microsoft 365

- Servicios y aplicaciones de usuario:

  - SharePoint
  - Teams
  - Outlook en la Web y para Windows, macOS, iOS y Android
  - Forms
  - Stream
  - Planner 

Las siguientes aplicaciones y servicios actualmente no son compatibles con las etiquetas de confidencialidad establecidas para la configuración de sitios y grupos:

- Centros de administración:

  - Centro de administración de Exchange

- Servicios y aplicaciones de usuario:

  - Dynamics 365
  - Yammer
  - Project
  - Power BI

## <a name="classic-azure-ad-group-classification"></a>Clasificación de grupos de Azure AD clásica

Después de habilitar las etiquetas de confidencialidad para contenedores, las clasificaciones de grupo de Azure AD ya no son compatibles con Microsoft 365 y no se mostrarán en los sitios que admiten etiquetas de confidencialidad. Sin embargo, puede convertir las clasificaciones antiguas en etiquetas de confidencialidad.

Como ejemplo de cómo podría haber utilizado la antigua clasificación de grupos para SharePoint, consulte [Clasificación de sitios "modernos" de SharePoint](/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Estas clasificaciones se configuraron con Azure AD PowerShell o la biblioteca principal de PnP y definiendo valores para la configuración de `ClassificationList`. Si su espacio empresarial tiene valores de clasificación definidos, se muestran al ejecutar el siguiente comando desde el módulo de [PowerShell de AzureADPreview](https://www.powershellgallery.com/packages/AzureADPreview):

```powershell
($setting["ClassificationList"])
```

Para convertir las clasificaciones antiguas en etiquetas de confidencialidad, siga uno de estos procedimientos:

- Usar etiquetas existentes: especifique la configuración de la etiqueta que desee para los sitios y grupos al editar las etiquetas de confidencialidad existentes que ya están publicadas.

- Crear etiquetas nuevas: especifique la configuración de la etiqueta que desee para los sitios y grupos creando y publicando nuevas etiquetas de confidencialidad que tengan los mismos nombres que las de las clasificaciones existentes.

Luego:

1. Use PowerShell para aplicar las etiquetas de confidencialidad a los grupos de Microsoft 365 y a los sitios de SharePoint mediante la asignación de nombres.

2. Quitar las clasificaciones antiguas de los grupos y sitios existentes.

Aunque no se puede impedir que los usuarios creen grupos nuevos en aplicaciones y servicios que aún no admiten las etiquetas de confidencialidad, puede ejecutar un script de PowerShell periódico para buscar grupos nuevos que los usuarios han creado con las clasificaciones anteriores y convertirlos para usar etiquetas de confidencialidad.

Para ayudarle a administrar la coexistencia de etiquetas de confidencialidad y clasificaciones de Azure AD para sitios y grupos, consulte [Clasificación y etiquetas de confidencialidad de Azure Active Directory para grupos de Microsoft 365](migrate-aad-classification-sensitivity-labels.md).

### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a>Usar PowerShell para convertir clasificaciones de grupos de Microsoft 365 a etiquetas de confidencialidad

1. En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

   Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:

2. Consiga la lista de etiquetas de sensibilidad y sus GUIDs usando el cmdlet[Get-Label](/powershell/module/exchange/get-label):

   ```powershell
   Get-Label |ft Name, Guid
   ```

3. Tome nota de los GUID para las etiquetas de confidencialidad que quiere aplicar a los grupos de Microsoft 365.

4. Ahora [conéctese a PowerShell en línea de Exchange](/powershell/exchange/connect-to-exchange-online-powershell) en una ventana independiente de Windows PowerShell.

5. Use el comando siguiente como ejemplo para obtener la lista de grupos que actualmente tienen la clasificación de "general":

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Para cada grupo, agregue la nueva etiqueta de confidencialidad GUID. Por ejemplo:

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. Repita los pasos 5 y 6 para el resto de sus clasificaciones de grupo.

## <a name="auditing-sensitivity-label-activities"></a>Auditar actividades de etiqueta de confidencialidad

> [!IMPORTANT]
> Si usa la separación de etiquetas seleccionando solo el ámbito **Grupos y sitios** para las etiquetas que protegen los contenedores: debido al evento de auditoría y correo electrónico **Desfase detectado de la confidencialidad del documento** descrito en esta sección, considere [ordenar las etiquetas](sensitivity-labels.md#label-priority-order-matters) antes de que tengan un ámbito para **Archivos y mensajes de correo electrónico**. 

Si alguien carga un documento en un sitio protegido con una etiqueta de confidencialidad y el documento tiene una etiqueta de confidencialidad de [mayor prioridad](sensitivity-labels.md#label-priority-order-matters) que la etiqueta de confidencialidad que se aplica al sitio, esta acción no está bloqueada. Por ejemplo, aplicó la etiqueta **general** a un sitio de SharePoint y alguien carga en este sitio un documento etiquetado como **confidencial**. Debido a que una etiqueta de confidencialidad con mayor prioridad identifica el contenido que es más confidencial que el contenido que tiene un orden de menor prioridad, esta situación podría ser un problema de seguridad.

Aunque la acción no está bloqueada, se audita y, de forma predeterminada, genera un correo electrónico para la persona que cargó el documento y el administrador del sitio. Como resultado, tanto el usuario como los administradores pueden identificar los documentos que no están alineados con la prioridad de las etiquetas y tomar las medidas necesarias. Por ejemplo, eliminar o mover el documento cargado del sitio.

No sería un problema de seguridad si el documento tiene una etiqueta de confidencialidad de menor prioridad que la etiqueta de confidencialidad aplicada al sitio. Por ejemplo, un documento con la etiqueta **general** se carga en un sitio con la etiqueta **confidencial**. En este escenario, no se generarán ni un evento de auditoría, ni un correo electrónico.

> [!NOTE]
> Al igual que para la opción de directiva que requiere que los usuarios proporcionen una justificación para cambiar una etiqueta a una clasificación inferior, todas las subetiquetas de la misma etiqueta primaria se consideran que tienen la misma prioridad.

Para buscar el registro de auditoría para este evento, busque **Desfase detectado de la confidencialidad del documento** en la categoría de las **actividades de archivos y páginas**.

El correo electrónico generado automáticamente tiene el asunto **Etiqueta de confidencialidad no compatible detectado** y el mensaje de correo electrónico explica que la etiqueta no coincide con un vínculo al documento cargado y al sitio. También contiene un vínculo a la documentación en el que se explica cómo los usuarios pueden cambiar la etiqueta de confidencialidad. Estos correos electrónicos automatizados no se pueden personalizar, pero puede impedir que se envíen al usar el siguiente comando de PowerShell desde [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant):

```PowerShell
Set-SPOTenant -BlockSendLabelMismatchEmail $True
```

Cuando alguien agrega o quita una etiqueta de confidencialidad a un sitio o grupo, estas actividades también se auditan, pero sin generar un correo electrónico automáticamente.

Todos estos eventos de auditoría se pueden encontrar en la categoría [Actividades de etiqueta de confidencialidad](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities). Para obtener instrucciones sobre cómo buscar el registro de auditoría, vea [buscar el registro de auditoría en el Centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md).

## <a name="how-to-disable-sensitivity-labels-for-containers"></a>Cómo deshabilitar etiquetas de confidencialidad para contenedores

Puede desactivar las etiquetas de confidencialidad para Microsoft Teams, Grupos de Microsoft 365 y sitios de SharePoint siguiendo las mismas instrucciones que se indican en [Habilitar compatibilidad con las etiquetas de confidencialidad en PowerShell](/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell). Sin embargo, para deshabilitar esta característica, especifique `$setting["EnableMIPLabels"] = "False"` en el Paso 5.

Además de hacer que todas las opciones de configuración para grupos y sitios no estén disponibles cuando cree o edite etiquetas de confidencialidad, esta acción revierte la propiedad que usan los contenedores para su configuración. Al habilitar las etiquetas de confidencialidad para Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint se cambia la propiedad **Clasificación** (usada para la [clasificación de grupos de Azure AD](#classic-azure-ad-group-classification)) a **Confidencialidad**. Cuando deshabilita las etiquetas de confidencialidad para contenedores, estos ignoran la propiedad Confidencialidad y vuelven a usar la propiedad Clasificación.

Esto quiere decir que no se exigirá la configuración de etiquetas para sitios y grupos que se aplicó previamente a los contenedores, y los contenedores ya no mostrarán las etiquetas.

Si dichos contenedores tienen valores de clasificación de Azure AD aplicados, estos volverán a usar las clasificaciones. Tenga en cuenta que cualquier nuevo sitio o grupo creado después de habilitar la característica no mostrará una etiqueta ni tendrá una clasificación. Ahora puede aplicar valores de clasificación tanto a estos como a los nuevos contenedores. Para obtener más información, consulte [Clasificación de sitios "moderna" de SharePoint](/sharepoint/dev/solution-guidance/modern-experience-site-classification) y [Crear clasificaciones para grupos de Office en su organización](../enterprise/manage-microsoft-365-groups-with-powershell.md).

## <a name="additional-resources"></a>Recursos adicionales

Consulte la grabación y las preguntas contestadas sobre el [Uso de etiquetas de sensibilidad con Microsoft Teams, grupos de O365 y sitios de SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).

Este seminario web se grabó cuando la característica aún estaba en la versión preliminar, por lo que es posible que observe algunas discrepancias en la interfaz de usuario. Aún así, la información de esta característica es precisa, con las nuevas funciones que se documentan en esta página.

Para obtener más información sobre la administración de sitios conectados de Teams y sitios de canales, vea [Administrar sitios conectados de Teams y sitios de canales](/SharePoint/teams-connected-sites).
