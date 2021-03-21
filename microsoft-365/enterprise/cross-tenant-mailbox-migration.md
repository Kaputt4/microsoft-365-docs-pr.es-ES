---
title: Migración de buzones de inquilinos cruzados
description: Cómo mover buzones entre inquilinos de Microsoft 365 u Office 365.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 7c3b4f82d94888cfa6c63b25f20130a38f8b4c9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919205"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migración de buzones entre inquilinos (versión preliminar)

Anteriormente, cuando un inquilino de Exchange Online necesitaba mover buzones a otro inquilino en el mismo servicio de Exchange Online, tendría que desasogarlos completamente en el entorno local y, a continuación, incorporarlos a un nuevo inquilino. Con la nueva característica de migración de buzones entre inquilinos, los administradores de inquilinos de los inquilinos de origen y de destino pueden mover buzones entre los inquilinos con dependencias mínimas de infraestructura en sus sistemas locales. Esto quita la necesidad de retirar y incorporar buzones.

Normalmente, durante fusiones o desinstituras, necesita la capacidad de mover usuarios y contenido a un nuevo inquilino. Cuando el administrador de inquilinos de destino ejecuta el movimiento, se denomina movimiento de extracción, similar a las migraciones locales a las migraciones de incorporación en la nube.

Los administradores de inquilinos pueden realizar un autoservicio total de los movimientos de buzones de Exchange entre inquilinos, mediante interfaces conocidas que se pueden incluir en los flujos de trabajo más grandes necesarios para realizar la transición de usuarios a su nueva organización. Los administradores pueden usar el cmdlet, disponible a través del rol de administración Mover buzones, para ejecutar movimientos `New-MigrationBatch` entre inquilinos. El proceso de movimiento incluye comprobaciones de autorización de inquilino durante la sincronización y la finización de buzones. 
 
Los usuarios que migran deben estar presentes en el sistema exchange online de inquilino de destino como MailUsers, marcados con atributos específicos para habilitar los movimientos entre inquilinos. El sistema producirá un error en los movimientos de los usuarios que no estén configurados correctamente en el espacio empresarial de destino.  

Cuando se completan los movimientos, el buzón del sistema de origen se convierte en MailUser y el targetAddress (que se muestra como ExternalEmailAddress en Exchange) se marca con la dirección de enrutamiento al inquilino de destino. Este proceso deja el mailuser heredado en el inquilino de origen y permite un período de coexistencia y enrutamiento de correo. Cuando los procesos empresariales lo permiten, el inquilino de origen puede quitar el mailuser de origen o convertirlo en un contacto de correo. 

Las migraciones de buzones de Exchange entre inquilinos se admiten solo para inquilinos en la nube o híbrida, o cualquier combinación de los dos.

En este artículo se describe el proceso de movimientos de buzones entre inquilinos y se proporcionan instrucciones sobre cómo preparar los inquilinos de origen y de destino para el movimiento de contenido.  

## <a name="preparing-source-and-target-tenants"></a>Preparación de inquilinos de origen y de destino

La característica de migración de buzones de Exchange entre inquilinos requiere autorización y ámbito para las migraciones entre inquilinos. Con la aplicación de Azure Enterprise y las soluciones de almacenamiento de Key Vault, los administradores de inquilinos ahora tienen la capacidad de administrar la autorización y el ámbito de las migraciones de buzones de Exchange Online de un inquilino a otro. Los movimientos de buzones entre inquilinos admiten un modelo de invitación y consentimiento para establecer una aplicación de Azure Active Directory (Azure AD) usada para la autenticación entre un par de inquilinos. También se requieren componentes adicionales, como una relación de organización y un extremo de migración.

Esta sección no incluye los pasos específicos necesarios para preparar los objetos de usuario MailUser en el directorio de destino, ni incluye el comando de ejemplo para enviar un lote de migración. Consulte Prepare [target user objects for migration para](#prepare-target-user-objects-for-migration) obtener esta información.

## <a name="prerequisites"></a>Requisitos previos

La característica de movimiento de buzones entre inquilinos requiere que [Azure Key Vault](/azure/key-vault/basic-concepts) establezca una aplicación de Azure específica del par de inquilinos para almacenar y obtener acceso de forma segura al certificado o secreto usado para autenticar y autorizar la migración de buzones de correo de un inquilino a otro, eliminando los requisitos para compartir certificados o secretos entre inquilinos. 

Antes de empezar, asegúrese de que tiene los permisos necesarios para ejecutar los scripts de implementación con el fin de configurar Azure Key Vault, la aplicación Move Mailbox, exo Migration Endpoint y la relación de organización de EXO. Normalmente, el administrador global tiene permiso para realizar todos los pasos de configuración.

Además, los grupos de seguridad habilitados para correo en el espacio empresarial de origen son necesarios antes de ejecutar la instalación. Estos grupos se usan para establecer el ámbito de la lista de buzones que pueden moverse del espacio empresarial de origen (o a veces denominado recurso) al espacio empresarial de destino. Esto permite al administrador de inquilinos de origen restringir o establecer el ámbito del conjunto específico de buzones que se deben mover, lo que impide que los usuarios no intencionados se migren. No se admiten grupos anidados.

También tendrá que comunicarse con su empresa asociada de confianza (con la que va a mover buzones) para obtener su identificador de inquilino de Microsoft 365. Este identificador de inquilino se usa en el campo Relación de `DomainName` la organización.

Para obtener el identificador de inquilino de una suscripción, inicie sesión en el Centro de administración de Microsoft 365 y vaya a [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Haga clic en el icono de copia de la propiedad Id. de inquilino para copiarla en el Portapapeles.

Este es el funcionamiento del proceso.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparación del espacio empresarial para la migración de buzones de correo.":::

[Vea una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Preparar inquilinos

En un nivel alto, se llevan a cabo las siguientes acciones de configuración al ejecutar los scripts de instalación.

Preparar el inquilino de destino:

1. Si no se proporciona un grupo de recursos de Azure existente, se crea uno nuevo (SCRIPT).
2. Si no se proporciona un almacén de claves existente, se crea uno nuevo (SCRIPT).
3. Se crea una nueva directiva de acceso para la aplicación de migración de buzones de Correo (SCRIPT) de Office 365 Exchange Online.
4. Se crea un nuevo certificado (o uno existente, si se especifica) para mantener el secreto en la aplicación de migración (SCRIPT).
5. Se crea una nueva aplicación de Azure AD (SCRIPT).
6. El certificado o secreto se carga en la aplicación de migración (SCRIPT).
7. Los permisos de migración de buzones de correo se asignan a la aplicación (SCRIPT).
8. El script de implementación se detiene hasta que el administrador de destino da su consentimiento a su propia aplicación (SCRIPT).
9. El administrador de inquilinos de destino consiente los permisos concedidos a la aplicación (MANUAL).
10. Se crea una relación de organización con el inquilino de destino (SCRIPT).
11. Se crea un extremo de migración para extraer buzones al inquilino de destino (SCRIPT).

Preparar el espacio empresarial de origen:

1. El administrador del espacio empresarial de origen acepta el consentimiento para la invitación de la aplicación de migración de buzones desde el inquilino de destino (MANUAL).
2. El administrador de inquilinos de origen crea un grupo de seguridad habilitado para correo en su inquilino para contener la lista de buzones permitidos por la aplicación de migración (MANUAL).
3. Se crea una relación de organización con el inquilino de destino que especifica la aplicación de migración de buzones de correo que debe usarse para la comprobación de OAuth para aceptar la solicitud de movimiento (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Instrucciones paso a paso para el administrador de inquilinos de destino

1. Descargue el script SetupCrossTenantRelationshipForTargetTenant.ps1 para la configuración del inquilino de destino desde el [repositorio de GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 
2. Guarde el script (SetupCrossTenantRelationshipForTargetTenant.ps1) en el equipo desde el que va a ejecutar el script.
3. Cree una conexión remota de PowerShell al inquilino de destino de Exchange Online. De nuevo, asegúrese de que tiene los permisos necesarios para ejecutar los scripts de implementación con el fin de configurar el certificado y el almacenamiento de Azure Key Vault, la aplicación Mover buzón de correo, el extremo de migración exo y la relación de la organización de EXO.
4. Cambie el directorio de la carpeta de archivos a la ubicación del script o compruebe que el script está guardado actualmente en la ubicación que se encuentra actualmente en la sesión remota de PowerShell.
5. Ejecute el script con los siguientes parámetros y valores.

    | Parámetro | Valor | Obligatorio u opcional
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Dominio de inquilino de destino, como fabrikam \. onmicrosoft.com. | Obligatorio |
    | -ResourceTenantDomain                       | Dominio de inquilino de origen, como contoso \. onmicrosoft.com. | Obligatorio |
    | -ResourceTenantAdminEmail                   | Dirección de correo electrónico del administrador del espacio empresarial de origen. Este es el administrador de inquilinos de origen que dará su consentimiento al uso de la aplicación de migración de buzones enviada desde el administrador de destino. Este es el administrador que recibirá la invitación de correo electrónico para la aplicación. | Obligatorio |
    | -ResourceTenantId                           | Identificador de organización de inquilino de origen (GUID). | Obligatorio |
    | -SubscriptionId                             | La suscripción de Azure que se usará para crear recursos. | Obligatorio |
    | -ResourceGroup                              | Nombre del grupo de recursos de Azure que contiene o contendrá el Almacén de claves. | Obligatorio |
    | -KeyVaultName                               | Instancia de Azure Key Vault que almacenará el certificado o secreto de la aplicación de migración de buzones. | Obligatorio |
    | -CertificateName                            | Nombre del certificado al generar o buscar certificado en el almacén de claves. | Obligatorio |
    | -CertificateSubject                         | Nombre de sujeto del certificado de Azure Key Vault, como CN=contoso_fabrikam. | Obligatorio |
    | -ExistingApplicationId                      | Aplicación de migración de correo que se usará si ya se creó una. | Opcional |
    | -AzureAppPermissions                        | Los permisos necesarios para concederse a la aplicación de migración de buzones, como Exchange o MSGraph (Exchange para mover buzones, MSGraph para usar esta aplicación para enviar una invitación de vínculo de consentimiento al inquilino de recursos). | Obligatorio |
    | -UseAppAndCertGeneratedForSendingInvitation | Parámetro para usar la aplicación creada para la migración que se usará para enviar una invitación de vínculo de consentimiento al administrador del espacio empresarial de origen. Si no está presente, se pedirán las credenciales del administrador de destino para conectarse al Administrador de invitaciones de Azure y enviar la invitación como administrador de destino. | Opcional |
    | -KeyVaultAuditStorageAccountName            | Cuenta de almacenamiento donde se almacenarían los registros de auditoría de Key Vault. | Opcional |
    | -KeyVaultAuditStorageResourceGroup          | El grupo de recursos que contiene la cuenta de almacenamiento para almacenar registros de auditoría de Key Vault. | Opcional |
    ||||

    >[!Note]
    > Asegúrese de haber instalado el módulo de PowerShell de Azure AD antes de ejecutar los scripts. Consulte aquí ![ los pasos de ](/powershell/azure/install-az-ps?view=azps-5.1.0) instalación

6. El script se pausará y le pedirá que acepte o acepte la aplicación de migración de buzones de Exchange que se creó durante este proceso. Aquí le mostramos un ejemplo.

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. Se mostrará una dirección URL en la sesión remota de PowerShell. Copie el vínculo proporcionado para el consentimiento del inquilino y péguelo en un explorador web.

8. Inicie sesión con sus credenciales de administrador global. Cuando se presente la siguiente pantalla, seleccione **Aceptar**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Cuadro de diálogo Aceptar permisos":::

9. Vuelva a la sesión remota de PowerShell y presione Entrar para continuar.

10. El script configurará los objetos de instalación restantes. Aquí le mostramos un ejemplo.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

La configuración de administración de destino ya está completa.

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Instrucciones paso a paso para el administrador del espacio empresarial de origen

1.  Inicie sesión en el buzón como -ResourceTenantAdminEmail especificado por el administrador de destino durante su instalación. Busque la invitación de correo electrónico desde el inquilino de destino y, a continuación, seleccione el **botón Introducción.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Cuadro de diálogo invitado":::

2. Seleccione **Aceptar** para aceptar la invitación.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Cuadro de diálogo para aceptar permisos":::

   > [!NOTE]
   > Si no recibe este correo electrónico o no lo encuentra, al administrador de inquilinos de destino se le proporcionó una dirección URL directa que se le puede dar para aceptar la invitación. La dirección URL debe incluirse en la transcripción de la sesión remota de PowerShell del administrador de inquilino de destino.

3. En el Centro de administración de Microsoft 365 o en una sesión de PowerShell remoto, cree uno o varios grupos de seguridad habilitados para correo para controlar la lista de buzones permitidos por el inquilino de destino para extraer (mover) del inquilino de origen al inquilino de destino. No es necesario rellenar este grupo por adelantado, pero se debe proporcionar al menos un grupo para ejecutar los pasos de instalación (script). No se admiten grupos de anidamiento. 

4. Descargue el script SetupCrossTenantRelationshipForResourceTenant.ps1 para la configuración del espacio empresarial de origen desde el repositorio de GitHub aquí: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) . 

5. Cree una conexión remota de PowerShell al espacio empresarial de origen con los permisos de administrador de Exchange. Los permisos de administración global no son necesarios para configurar el inquilino de origen, solo el inquilino de destino debido al proceso de creación de aplicaciones de Azure.

6. Cambie el directorio a la ubicación del script o compruebe que el script está guardado actualmente en la ubicación actualmente en la sesión remota de PowerShell.

7. Ejecute el script con los siguientes parámetros y valores necesarios.

    | Parámetro | Valor |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Grupo de seguridad habilitado para correo creado por el inquilino de origen para las identidades o buzones que están en el ámbito de la migración. |
    | -ResourceTenantDomain | Nombre de dominio del espacio empresarial de origen, como contoso \. onmicrosoft.com. |
    | -ApplicationId | Identificador de aplicación de Azure (GUID) de la aplicación usada para la migración. Id. de aplicación disponible a través de Azure Portal (Azure AD, Aplicaciones empresariales, nombre de la aplicación, id. de aplicación) o incluido en el correo electrónico de invitación.  |
    | -TargetTenantDomain | Nombre de dominio de inquilino de destino, como fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | Identificador de inquilino del inquilino de destino. Por ejemplo, el identificador de inquilino de Azure AD de contoso \. onmicrosoft.com inquilino. |
    |||

    Aquí le mostramos un ejemplo.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

La configuración de administración de origen ya está completa.

### <a name="verify-setup"></a>Comprobar la configuración

Compruebe que las relaciones de la organización en los inquilinos de origen y de destino y el extremo de migración en el destino se crearon correctamente.

#### <a name="target-tenant"></a>Inquilino de destino

**Relación de organización**

Compruebe que el objeto de relación de organización se creó y configuró con este comando.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Aquí le mostramos un ejemplo:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Extremo de migración**

Compruebe que el objeto de extremo de migración se creó y configuró con este comando.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Aquí le mostramos un ejemplo.

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Inquilino de origen

**Relación de organización**

Compruebe que el objeto de relación de organización se creó y configuró con este comando.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

Aquí le mostramos un ejemplo.

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a>Comprobar script de instalación

Si recibe algún error durante la configuración de los inquilinos de origen o de destino, puede ejecutar el script VerifySetup.ps1 ubicado en [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) y revisar el resultado.

Este es un ejemplo de ejecución de VerifySetup.ps1 en el inquilino de destino:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Este es un ejemplo de VerifySetup.ps1 en el inquilino de origen:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Volver a mover buzones al origen original

Si es necesario volver a mover un buzón al espacio empresarial de origen original, deberá ejecutarse el mismo conjunto de pasos y scripts tanto en nuevos inquilinos de origen como en nuevos inquilinos de destino. El objeto Relación de la organización existente se actualizará o anexará, no se volverá a crear.

## <a name="prepare-target-user-objects-for-migration"></a>Preparar objetos de usuario de destino para la migración

Los usuarios que migran deben estar presentes en el inquilino de destino y en el sistema de Exchange Online (como MailUsers) marcados con atributos específicos para habilitar los movimientos entre inquilinos. El sistema producirá un error en los movimientos de los usuarios que no estén configurados correctamente en el espacio empresarial de destino. En la siguiente sección se detallan los requisitos del objeto MailUser para el inquilino de destino.

### <a name="prerequisites"></a>Requisitos previos
  
Debe asegurarse de que los siguientes objetos y atributos se establecen en la organización de destino.  

1. Para cualquier buzón que se mueva desde una organización de origen, debe aprovisionar un objeto MailUser en la organización de destino: 

   - El mailuser de destino debe tener estos atributos del buzón de origen o asignados con el nuevo objeto User:
      - ExchangeGUID (flujo directo de origen a destino): el GUID del buzón debe coincidir. El proceso de movimiento no continuará si no está presente en el objeto de destino. 
      - ArchiveGUID (flujo directo de origen a destino): el GUID de archivo debe coincidir. El proceso de movimiento no continuará si no está presente en el objeto de destino. (Esto solo es necesario si el buzón de origen está habilitado para archivo). 
      - LegacyExchangeDN (flujo como proxyAddress, "x500: ") : LegacyExchangeDN debe estar presente en mailUser de destino como <LegacyExchangeDN> x500: proxyAddress. Los procesos de movimiento no procederán si no está presente en el objeto de destino. 
      - UserPrincipalName: UPN se alineará con la nueva identidad o la compañía de destino del usuario (por ejemplo, user@northwindtraders.onmicrosoft.com). 
      - SMTPAddress principal: la dirección SMTP principal se alineará con la compañía NEW del usuario (por ejemplo, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress: MailUser hará referencia al buzón actual del usuario hospedado en el inquilino de origen (por ejemplo, user@contoso.onmicrosoft.com). Al asignar este valor, compruebe que también ha asignado PrimarySMTPAddress o este valor establecerá primarySMTPAddress, lo que provocará errores de movimiento. 
      - No puede agregar direcciones de proxy smtp heredadas desde el buzón de origen al mailuser de destino. Por ejemplo, no puede mantener contoso.com en el MEU en fabrikam.onmicrosoft.com objetos de inquilino). Los dominios solo están asociados a un inquilino de Azure AD o Exchange Online.
 
     Objeto  MailUser de destino de ejemplo:
 
     | Atributo             | Valor                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | DN de Exchange heredado      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     Objeto **Mailbox de origen** de ejemplo:

     | Atributo             | Valor                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | DN de Exchange heredado      | /o=First Organization/ou=Exchange Administrative Group                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Es posible que ya se incluyan atributos adicionales en la escritura híbrida de Exchange. Si no es así, deben incluirse. 
   - msExchBlockedSendersHash: escribe datos de remitentes seguros y bloqueados de clientes en Active Directory local.
   - msExchSafeRecipientsHash: escribe los datos de remitentes seguros y bloqueados en línea de los clientes en Active Directory local.
   - msExchSafeSendersHash: escribe los datos de remitentes seguros y bloqueados de los clientes en Active Directory local.

2. Si el buzón de origen está en LitigationHold y el tamaño de elementos recuperables del buzón de origen es mayor que el valor predeterminado de nuestra base de datos (30 GB), los movimientos no se realizarán ya que la cuota de destino es menor que el tamaño del buzón de origen. Puede actualizar el objeto MailUser de destino para realizar la transición de las marcas de buzón elC del entorno de origen al destino, lo que desencadena que el sistema de destino expanda la cuota de MailUser a 100 GB, lo que permite el movimiento al destino. Estas instrucciones solo funcionarán para identidad híbrida que ejecute Azure AD Connect, ya que los comandos para marcar las marcas de ELC no se exponen a los administradores de inquilinos.

    >[!Note]
    > EJEMPLO: TAL COMO ESTÁ, SIN GARANTÍA<br/>Este script supone una conexión con el buzón de origen (para obtener los valores de origen) y el Active Directory local de destino (para marcar el objeto ADUser). Si el origen tiene habilitada la recuperación de un solo elemento o litigio, esta opción se establece en la cuenta de destino.  Esto aumentará el tamaño de contenedor de la cuenta de destino a 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Los inquilinos de destino no híbridos pueden modificar la cuota de la carpeta Elementos recuperables de MailUsers antes de la migración ejecutando el siguiente comando para habilitar la retención por juicio en el objeto MailUser y aumentar la cuota a 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Tenga en cuenta que esto no funcionará para los inquilinos en híbrido.

4. Los usuarios de la organización de destino deben tener una licencia con las suscripciones adecuadas de Exchange Online aplicables a la organización. Puede aplicar una licencia antes de un movimiento de buzón, pero SOLO una vez que el mailuser de destino esté configurado correctamente con ExchangeGUID y las direcciones proxy. La aplicación de una licencia antes de que se aplique ExchangeGUID dará como resultado un nuevo buzón aprovisionado en la organización de destino. 

    > [!Note]
    > Al aplicar una licencia en un objeto Mailbox o MailUser, todos los proxyAddresses de tipo SMTP se depuran para garantizar que solo se incluyan dominios comprobados en la matriz EmailAddresses de Exchange. 

5. Debe asegurarse de que mailuser de destino no tiene ExchangeGuid anterior que no coincida con el ExchangeGuid de origen. Esto puede ocurrir si el MEU de destino tenía licencia previa para Exchange Online y aprovisionaba un buzón. Si el mailuser de destino tenía una licencia previa para o tenía un ExchangeGuid que no coincide con el ExchangeGuid de origen, debe realizar una limpieza del MEU en la nube. Para estas MEUs en la nube, puede ejecutar `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .  

    > [!Caution]
    > Este proceso es irreversible. Si el objeto tiene un buzón softDeleted, no se puede restaurar después de este punto. Sin embargo, una vez desactivada, puede sincronizar el ExchangeGuid correcto con el objeto de destino y MRS conectará el buzón de origen al buzón de destino recién creado. (Consulte el blog EHLO sobre el nuevo parámetro).  

    Busque objetos que anteriormente eran buzones de correo mediante este comando.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    Aquí le mostramos un ejemplo. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    Borra el buzón eliminado temporalmente con este comando.

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    Aquí le mostramos un ejemplo.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a>Realizar migraciones de buzones

Las migraciones de buzones de Exchange entre inquilinos se envían como lotes de migración iniciados desde el inquilino de destino. Esto es similar a la forma en que funcionan los lotes de migración al migrar de Exchange local a Microsoft 365. 

### <a name="create-migration-batches"></a>Crear lotes de migración

Este es un cmdlet por lotes de migración de ejemplo para iniciar movimientos.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> La dirección de correo electrónico del archivo CSV debe ser la especificada en el inquilino de destino, no el inquilino de origen.

El envío por lotes de migración también se admite desde el nuevo Centro de administración de Exchange al seleccionar la opción entre inquilinos.

#### <a name="update-on-premises-mailusers"></a>Actualizar MailUsers local

Una vez que el buzón se mueve de origen a destino, debe asegurarse de que los usuarios de correo locales, tanto de origen como de destino, se actualicen con el nuevo targetAddress. En los ejemplos, el targetDeliveryDomain usado en el movimiento es **contoso.onmicrosoft.com**. Actualice los usuarios de correo con este targetAddress.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**¿Es necesario actualizar RemoteMailboxes en el origen local después del movimiento?**

Sí, debe actualizar el targetAddress (RemoteRoutingAddress/ExternalEmailAddress) de los usuarios locales de origen cuando el buzón de inquilino de origen se mueve al inquilino de destino.  Mientras que el enrutamiento de correo puede seguir las referencias entre varios usuarios de correo con diferentes targetAddresses, las búsquedas de disponibilidad para los usuarios de correo DEBEN dirigirse a la ubicación del usuario del buzón. Las búsquedas de disponibilidad no perseguirán varios redireccionamientos. 

**¿El contenido de la carpeta de chat de Teams migra entre inquilinos?**  

No, el contenido de la carpeta de chat de Teams no migra entre inquilinos.  

**¿Cómo puedo ver solo movimientos que son movimientos entre inquilinos, no mis movimientos de incorporación y de salida?**

Use el `-flags` parámetro. Aquí le mostramos un ejemplo.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**¿Puede proporcionar scripts de ejemplo para copiar atributos usados en las pruebas?**

> [!Note]
> EJEMPLO: TAL COMO ESTÁ, SIN GARANTÍA<br/>Este script supone una conexión tanto con el buzón de origen (para obtener valores de origen) como con los servicios de dominio de Active Directory locales de destino (para marcar el objeto ADUser). Si el origen tiene habilitada la recuperación de un solo elemento o litigio, esta opción se establece en la cuenta de destino.  Esto aumentará el tamaño de contenedor de la cuenta de destino a 100 GB.

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**¿Cómo se accede a Outlook el día 1 después de mover el buzón de uso?**

Dado que solo un inquilino puede ser propietario de un dominio, el smtpaddress principal anterior no se asociará al usuario en el inquilino de destino cuando se complete el movimiento del buzón; solo los dominios asociados con el nuevo inquilino. Outlook usa el nuevo UPN de los usuarios para autenticarse en el servicio y el perfil de Outlook espera encontrar el SMTPAddress principal heredado para que coincida con el buzón en el sistema de destino. Dado que la dirección heredada no está en el sistema de destino, el perfil de outlook no se conectará para buscar el buzón recién movido. 

Para esta implementación inicial, los usuarios tendrán que volver a generar su perfil con su nuevo UPN, dirección SMTP principal y volver a sincronizar el contenido OST. 

> [!Note]
> Planee en consecuencia al procesar por lotes a los usuarios para su finalización. Debe tener en cuenta el uso y la capacidad de la red cuando se crean perfiles de cliente de Outlook y los archivos OST y OAB posteriores se descargan en los clientes. 
 
**¿De qué roles RBAC de Exchange necesito ser miembro para configurar o completar un movimiento entre inquilinos?**
 
Hay una matriz de roles basada en la suposición de tareas delegadas al ejecutar un movimiento de buzón. Actualmente, se requieren dos roles:  

- El primer rol es para una tarea de configuración única que establece la autorización para mover contenido dentro o fuera del límite del espacio empresarial o de la organización. Como mover datos fuera del control de la organización es una preocupación crítica para todas las empresas, optamos por el rol más alto asignado de administrador de la organización (OrgAdmin). Este rol debe modificar o configurar un nuevo OrganizationRelationship que defina -MailboxMoveCapability con la organización remota. Solo OrgAdmin puede modificar la configuración MailboxMoveCapability, mientras que el administrador de uso compartido federado puede administrar otros atributos de OrganizationRelationhip. 
 
- El rol de ejecutar los comandos de movimiento reales se puede delegar en una función de nivel inferior. Al rol de Mover buzones se le asigna la capacidad de mover buzones de correo dentro o fuera de la organización mediante el `-RemoteTenant` parámetro.  

**¿Cómo se selecciona la dirección SMTP seleccionada para targetAddress (TargetDeliveryDomain) en el buzón convertido (en conversión MailUser)?**
 
El buzón de Exchange se mueve mediante MRS craft el targetAddress en el buzón de origen original al convertir a un mailuser al hacer coincidir una dirección de correo electrónico (proxyAddress) en el objeto de destino. El proceso toma el valor -TargetDeliveryDomain pasado al comando move y, a continuación, comprueba si hay un proxy que coincida con ese dominio en el lado de destino. Cuando se encuentra una coincidencia, se usa el proxyAddress correspondiente para establecer externalEmailAddress (targetAddress) en el objeto de buzón convertido (ahora MailUser).
 
**¿Cómo se hacen las transiciones de permisos de buzón de correo?**

Los permisos de buzón incluyen Enviar en nombre de y Acceso de buzones: 

- Enviar en nombre de (AD:publicDelegates) almacena el DN de los destinatarios con acceso al buzón de un usuario como delegado. Este valor se almacena en Active Directory y actualmente no se mueve como parte de la transición del buzón. Si el buzón de origen tiene publicDelegates establecido, tendrá que cambiar el tamaño de los publicDelegates en el buzón de destino una vez completada la conversión de MEU a buzón de correo en el entorno de destino ejecutando `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` . 
 
- Los permisos de buzón que se almacenan en el buzón se moverán con el buzón cuando la entidad de seguridad y el delegado se muevan al sistema de destino. Por ejemplo, al usuario TestUser_7 se le concede FullAccess al buzón TestUser_8 en el espacio empresarial SourceCompany.onmicrosoft.com. Una vez completado el movimiento del buzón TargetCompany.onmicrosoft.com, se establecen los mismos permisos en el directorio de destino. A continuación se muestran ejemplos que usan *Get-MailboxPermission* TestUser_7 en los inquilinos de origen y de destino. Los cmdlets de Exchange tienen el prefijo source y target en consecuencia. 
 
Este es un ejemplo de la salida del permiso de buzón antes de un movimiento. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Este es un ejemplo de la salida del permiso de buzón después del movimiento. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> No se admiten los permisos de buzón de correo y calendario entre inquilinos. Debe organizar entidades de seguridad y delegados en lotes de movimiento consolidados para que estos buzones conectados se transiciónn al mismo tiempo desde el espacio empresarial de origen. 

**¿Qué proxy X500 se debe agregar a las direcciones proxy mailuser de destino para habilitar la migración?**  

La migración de buzones entre inquilinos requiere que el valor LegacyExchangeDN del objeto de buzón de origen se estampe como una dirección de correo electrónico x500 en el objeto MailUser de destino.  

Ejemplo:  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> Además de este proxy X500, deberá copiar todos los servidores proxy X500 del buzón del buzón de correo en el buzón de correo del destino.  

**¿Dónde puedo empezar a solucionar problemas si los movimientos no funcionan?**  

Empiece por ejecutar el script VerifySetup.ps1 en [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) y revise el resultado.

Este es un ejemplo de ejecución de VerifySetup.ps1 en el inquilino de destino:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Este es un eExample de ejecución de VerifySetup.ps1 en el inquilino de origen:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**¿El inquilino de origen y de destino puede usar el mismo nombre de dominio?**  

No. Los nombres de dominio de inquilino de origen y de destino deben ser únicos. Por ejemplo, un dominio de origen de contoso.com el dominio de destino de fourthcoffee.com.

**¿Los buzones compartidos se moverán y seguirán funcionando?**

Sí, pero solo guardamos los permisos de almacén como se describe en estos artículos:

- [Microsoft Docs | Administrar permisos para destinatarios en Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Soporte técnico de Microsoft | Cómo conceder permisos de buzón de Exchange y Outlook en Office 365 dedicado](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**¿Es necesario Azure Key Vault y cuándo se realizan las transacciones?**  

Sí, se requiere una suscripción de Azure para usar Key Vault para almacenar el certificado para autorizar la migración. A diferencia de las migraciones de incorporación que usan nombre de usuario & contraseña para autenticarse en el origen, las migraciones de buzones entre inquilinos usan OAuth y este certificado como secreto/credencial. El acceso al almacén de claves debe mantenerse en todas las migraciones de buzones, ya que se tiene acceso a él una vez al principio y al final de la migración, así como una vez cada 24 horas durante los tiempos de sincronización incremental. Puede revisar los detalles del costo de AKV [aquí]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).  

**¿Tiene alguna recomendación para lotes?**  

No supere los 2000 buzones por lote. Recomendamos encarecidamente enviar lotes dos semanas antes de la fecha de corte, ya que no hay ningún impacto para los usuarios finales durante la sincronización. Si necesita instrucciones sobre las cantidades de buzones de correo que supere los 50 000, puede comunicarse con la Lista de distribución de comentarios de ingeniería en crosstenantmigrationpreview@service.microsoft.com.

**¿Qué ocurre si uso el cifrado de servicio con clave de cliente?**

El buzón se descifrará antes de moverlo. Asegúrese de que la clave de cliente está configurada en el espacio empresarial de destino si aún es necesaria. Vea [aquí](../compliance/customer-key-overview.md) para obtener más información.  

**¿Cuál es el tiempo estimado de migración?**

Para ayudarle a planear la [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) migración, la tabla que se muestra aquí muestra las directrices sobre cuándo esperar que se completen las migraciones masivas de buzones de correo o las migraciones individuales. Estas estimaciones se basan en un análisis de datos de migraciones de clientes anteriores. Dado que cada entorno es único, la velocidad exacta de migración puede variar.  

Recuerde que esta característica está actualmente en versión preliminar y el SLA y los niveles de servicio aplicables no se aplican a ningún problema de rendimiento o disponibilidad durante el estado de vista previa de esta característica.

## <a name="known-issues"></a>Problemas conocidos  

-  **Problema: no se pueden migrar los archivos expandido automáticamente.** La característica de migración entre inquilinos admite las migraciones del buzón principal y del buzón de archivo para un usuario específico. Sin embargo, si el usuario del origen tiene un archivo expandido automáticamente, lo que significa más de un buzón de archivo, la característica no puede migrar los archivos adicionales y debería producir un error.

- **Problema: Los usuarios de correo en la nube con proxy smtp no propietarioSombre de dirección de dirección se mueve en segundo plano.** Al crear objetos MailUser de inquilino de destino, debe asegurarse de que todas las direcciones proxy SMTP pertenecen a la organización de inquilino de destino. Si existe un proxy SMTPAddress en el usuario de correo de destino que no pertenece al inquilino local, se impide la conversión de MailUser a Mailbox. Esto se debe a nuestra seguridad de que los objetos de buzón solo pueden enviar correo desde dominios para los que el inquilino es autoritativo (dominios reclamados por el inquilino): 

   - Cuando sincroniza usuarios locales con Azure AD Connect, aprovisiona objetos MailUser locales con ExternalEmailAddress que apuntan al espacio empresarial de origen donde existe el buzón (laran@contoso.onmicrosoft.com) y se marca PrimarySMTPAddress como un dominio que reside en el inquilino de destino (Lara.Newton@northwind.com). Estos valores se sincronizan con el inquilino y se aprovisiona un usuario de correo adecuado y listo para la migración. Aquí se muestra un objeto de ejemplo.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > La *contoso.onmicrosoft.com* no *está presente* en la matriz EmailAddresses/proxyAddresses.

- **Problema: Los objetos MailUser con direcciones SMTP principales "externas" se modifican o restablecen a dominios "internos" reclamados por la compañía**

   Los objetos MailUser son punteros a buzones no locales. En el caso de las migraciones de buzones entre inquilinos, se usan objetos MailUser para representar el buzón de origen (desde la perspectiva de la organización de destino) o el buzón de destino (desde la perspectiva de la organización de origen). Los MailUsers tendrán una dirección ExternalEmailAddress (targetAddress) que apunta a la dirección smtp del buzón real (ProxyTest@fabrikam.onmicrosoft.com) y la dirección primarySMTP que representa la dirección SMTP mostrada del usuario del buzón en el directorio. Algunas organizaciones deciden mostrar la dirección SMTP principal como una dirección SMTP externa, no como una dirección propiedad o comprobada por el inquilino local (como fabrikam.com en lugar de como contoso.com).  Sin embargo, una vez que se aplica un objeto de plan de servicio de Exchange al MailUser mediante operaciones de licencia, la dirección SMTP principal se modifica para mostrarse como un dominio comprobado por la organización local (contoso.com). Existen dos posibles motivos:
   
   - Cuando se aplica cualquier plan de servicio de Exchange a un MailUser, el proceso de Azure AD comienza a aplicar el uso de la depuración de proxy para garantizar que la organización local no pueda enviar correo, suplantación de suplantación o correo de otro inquilino. Cualquier dirección SMTP de un objeto de destinatario con estos planes de servicio se quitará si la organización local no comprueba la dirección. Como en el ejemplo, el inquilino de Fabikam.com no comprueba el dominio contoso.onmicrosoft.com, por lo que la depuración quita fabrikam.com dominio. Si desea conservar estos dominios externos en MailUser, ya sea antes de la migración o después de la migración, debe modificar los procesos de migración para quitar licencias una vez completado el movimiento o antes del movimiento para asegurarse de que los usuarios tienen aplicada la personalización de marca externa esperada. Deberá asegurarse de que el objeto de buzón tenga una licencia adecuada para no afectar al servicio de correo.<br/><br/>Aquí se muestra un script de ejemplo para quitar los planes de servicio de un mailuser en el Contoso.onmicrosoft.com inquilino.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Los resultados en el conjunto de ServicePlans asignados se muestran aquí.

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       El primarySMTPAddress del usuario ya no se limpia. El fabrikam.com no es propiedad del inquilino contoso.onmicrosoft.com y persistirá como la dirección SMTP principal que se muestra en el directorio.

       Aquí le mostramos un ejemplo.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Cuando msExchRemoteRecipientType se establece en 8 (DeprovisionMailbox), para los MailUser locales que se migran al inquilino de destino, la lógica de depuración de proxy en Azure quitará los dominios no conocidos y restablecerá el primarySMTP a un dominio de propiedad. Al borrar msExchRemoteRecipientType en el mailuser local, la lógica de depuración de proxy ya no se aplica. <br/><br>A continuación se muestra el conjunto completo de posibles planes de servicio que incluyen Exchange Online.

   | Nombre                                              |
   |---------------------------------------------------|
   | Almacenamiento de exhibición de documentos electrónicos avanzado (500 GB)               |
   | Caja de seguridad del cliente                                  |
   | Prevención de pérdida de datos                              |
   | Servicios CAL de Exchange Enterprise (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (plan 1)                          |
   | Exchange Online (plan 2)                          |
   | Archivado de Exchange Online para Exchange Online     |
   | Archivado de Exchange Online para Exchange Server     |
   | Complemento de usuario inactivo de Exchange Online              |
   | Quiosco de Exchange Online                             |
   | Exchange Online Multi-Geo                         |
   | Plan 1 de Exchange Online                            |
   | POP de Exchange Online                               |
   | Exchange Online Protection                        |
   | Barreras de información                              |
   | Information Protection para Office 365 - Premium   |
   | Information Protection para Office 365 - Estándar  |
   | Insights de MyAnalytics                           |
   | Auditoría avanzada de Microsoft 365                   |
   | Microsoft Bookings                                |
   | Centro de negocios de Microsoft                         |
   | Microsoft MyAnalytics (Completo)                      |
   | eDiscovery avanzado de Office 365                    |
   | Microsoft Defender para Office 365 (Plan 1)    |
   | Microsoft Defender para Office 365 (Plan 2)    |
   | Office 365 Privileged Access Management           |
   | Cifrado premium en Office 365                  |
