---
title: Migración de buzones de inquilinos cruzados
description: Cómo mover buzones entre los inquilinos de Microsoft 365 o de Office 365.
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
ms.openlocfilehash: a9f983cebfbed1482fca7e44b77c200cbd9574ac
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847123"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migración de buzones de correo entre espacios empresariales (versión preliminar)

Anteriormente, cuando un inquilino de Exchange Online necesitaba mover buzones de correo a otro inquilino en el mismo servicio de Exchange Online, tendría que desincorporarlas por completo y luego incorporarlas a un nuevo inquilino. Con la nueva característica de migración de buzones de correo entre inquilinos, los administradores de espacios empresariales de los inquilinos de origen y de destino pueden mover buzones de correo entre los inquilinos con las dependencias de infraestructura mínimas en sus sistemas locales. Esto elimina la necesidad de desincorpora e incorporar buzones de correo.

Por lo general, durante fusiones o desinversiones, es necesario poder mover usuarios y contenido a un nuevo inquilino. Cuando el administrador del espacio empresarial de destino ejecuta el movimiento, se denomina movimiento de extracción, similar a las migraciones locales a la incorporación de la nube.

Los administradores de espacios empresariales administran completamente los movimientos de buzones de Exchange entre inquilinos, usando interfaces bien conocidas que se pueden incluir en scripts en los flujos de trabajo más grandes necesarios para realizar la transición de los usuarios a la nueva organización. Los administradores pueden usar el `New-MigrationBatch` cmdlet, que está disponible a través del rol de administración mover buzones, para ejecutar movimientos entre inquilinos. El proceso de traslado incluye las comprobaciones de autorización del inquilino durante la sincronización y finalización del buzón. 
 
Los usuarios que migren deben estar presentes en el sistema Exchange online del inquilino de destino como MailUsers, marcados con atributos específicos para habilitar los movimientos entre inquilinos. Se producirá un error en el sistema para los usuarios que no se hayan configurado correctamente en el espacio empresarial de destino. 

Cuando se completan los movimientos, el buzón del sistema de origen se convierte en MailUser y el targetAddress (que se muestra como ExternalEmailAddress en Exchange) se marca con la dirección de enrutamiento para el inquilino de destino. Este proceso abandona el MailUser heredado en el espacio empresarial de origen y permite un período de coexistencia y enrutamiento de correo. Cuando los procesos de negocio lo permiten, el inquilino de origen puede quitar el MailUser de origen o convertirlos en un contacto de correo. 

Las migraciones de buzones de correo de Exchange entre inquilinos son compatibles para los inquilinos de solo híbrida o de nube, o cualquier combinación de los dos.

En este artículo se describe el proceso para los movimientos entre inquilinos de buzones y se proporcionan instrucciones sobre cómo preparar los inquilinos de origen y de destino para el movimiento de contenido. 

## <a name="preparing-source-and-target-tenants"></a>Preparar los inquilinos de origen y de destino

La característica de migración de buzones de correo de Exchange entre inquilinos requiere autorización y ámbito para las migraciones entre inquilinos. Mediante el uso de las soluciones de almacenamiento de la aplicación empresarial de Azure y de Key Vault, los administradores de espacios empresariales ahora están autorizados para administrar la autorización y el alcance de las migraciones de buzones de Exchange online de un inquilino a otro. Los movimientos entre inquilinos de buzones admiten un modelo de invitación y consentimiento para establecer una aplicación de Azure Active Directory (Azure AD) que se usa para la autenticación entre un par de inquilinos. También se requieren componentes adicionales, como una relación de organización y un extremo de migración.

Esta sección no incluye los pasos específicos necesarios para preparar los objetos de usuario de MailUser en el directorio de destino, ni incluye el comando de ejemplo para enviar un lote de migración. Para obtener más información, vea [preparar objetos de usuario de destino para la migración](#prepare-target-user-objects-for-migration) .

## <a name="prerequisites"></a>Requisitos previos

La característica de movimiento de buzones entre inquilinos requiere que [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) establezca una aplicación de Azure específica para el par de inquilinos para almacenar de forma segura y tener acceso al certificado o secreto usado para autenticar y autorizar la migración de buzones de un inquilino a otro, quitando los requisitos para compartir certificados y secretos entre los inquilinos. 

Antes de empezar, asegúrese de que dispone de los permisos necesarios para ejecutar los scripts de implementación con el fin de configurar Azure Key Vault, Move Mailbox Application, el extremo de migración de EXO y la relación de organización EXO. Normalmente, el administrador global tiene permiso para realizar todos los pasos de configuración.

Además, los grupos de seguridad habilitados para correo electrónico en el espacio empresarial de origen son necesarios antes de ejecutar el programa de instalación. Estos grupos se usan para definir el ámbito de la lista de buzones de correo que pueden moverse del inquilino de origen (o, en ocasiones, denominado recurso) al inquilino de destino. Esto permite que el administrador del espacio empresarial de origen restrinja o alcance el conjunto específico de buzones que se deben mover, evitando que se migren los usuarios no deseados. No se admiten los grupos anidados.

También tendrá que comunicarse con la empresa de asociados de confianza (con la que va a mover buzones) para obtener su identificador de inquilino de 365 de Microsoft. Este identificador de inquilino se usa en el campo relación de la organización `DomainName` .

Para obtener el identificador de inquilino de una suscripción, inicie sesión en el centro de administración de Microsoft 365 y vaya a [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Haga clic en el icono de copia de la propiedad de ID de inquilino para copiarla en el portapapeles.

Este es el funcionamiento del proceso.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparación del espacio empresarial para la migración de buzones.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).
--> 

### <a name="prepare-tenants"></a>Preparar inquilinos

En un nivel superior, se producen las siguientes acciones de configuración cuando se ejecutan los scripts de instalación.

Preparar el inquilino de destino:

1. Si no se proporciona un grupo de recursos de Azure existente, se crea uno nuevo (SCRIPT).
2. Si no se proporciona un almacén de claves existente, se creará uno nuevo (SCRIPT).
3. Se crea una nueva Directiva de acceso para la aplicación de migración de buzones de correo de Exchange Online (SCRIPT) de Office 365.
4. Se crea un nuevo certificado (o uno existente, si se especifica) para contener el secreto de la aplicación de migración (SCRIPT).
5. Se crea una nueva aplicación de Azure AD (secuencia de comandos).
6. El certificado/secreto se carga en la aplicación de migración (secuencia de comandos).
7. Los permisos de migración de buzones de correo se asignan a la aplicación (secuencia de comandos).
8. El script de implementación se pausa hasta que el administrador de destino haya dado su consentimiento a su propia aplicación (SCRIPT).
9. El administrador del espacio empresarial de destino se remitirá a los permisos asignados a la aplicación (MANUAL).
10. Se crea una relación de organización con el espacio empresarial de destino (SCRIPT).
11. Se crea un extremo de migración para extraer buzones al inquilino de destino (SCRIPT).

Prepare el inquilino de origen:

1. El administrador del espacio empresarial de origen acepta el consentimiento para la invitación de la aplicación de migración del buzón de correo del espacio empresarial de destino (MANUAL).
2. El administrador del espacio empresarial de origen crea un grupo de seguridad habilitado para correo en su inquilino para incluir la lista de buzones que la aplicación de migración puede mover (MANUAL).
3. Se crea una relación de organización con el inquilino de destino que especifica la aplicación de migración de buzones de correo que se debe usar para la comprobación de OAuth para aceptar la solicitud de movimiento (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Instrucciones paso a paso para el administrador del espacio empresarial de destino

1. Descargue el script de SetupCrossTenantRelationshipForTargetTenant.ps1 para la configuración del inquilino de destino desde el [repositorio de github](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 
2. Guarde el script (SetupCrossTenantRelationshipForTargetTenant.ps1) en el equipo desde el que va a ejecutar el script.
3. Cree una conexión de PowerShell remota con el inquilino de destino de Exchange Online. De nuevo, asegúrese de que tiene los permisos necesarios para ejecutar los scripts de implementación con el fin de configurar el certificado y el almacenamiento de la clave de Azure para la aplicación mover buzones, el extremo de migración de EXO y la relación de organización EXO.
4. Cambie el directorio de la carpeta de archivos a la ubicación del script o Compruebe que el script se haya guardado actualmente en la ubicación actual de la sesión de PowerShell remoto.
5. Ejecute el script con los siguientes parámetros y valores.

    | Parámetro | Valor | Obligatorio u opcional
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | Dominio de inquilino de origen, como Fabrikam \. onmicrosoft.com. | Necesario |
    | -ResourceTenantAdminEmail                   | Dirección de correo electrónico del administrador del inquilino de origen. Este es el administrador de inquilinos de origen que contratará el uso de la aplicación de migración de buzones de correo enviada desde el administrador de destino. Este es el administrador que recibirá la invitación por correo electrónico para la aplicación. | Necesario |
    | -TargetTenantDomain                         | Dominio de inquilino de destino, como contoso \. onmicrosoft.com. | Necesario |
    | -ResourceTenantId                           | IDENTIFICADOR de la organización del espacio empresarial de origen (GUID). | Necesario |
    | -SubscriptionId                             | La suscripción de Azure que se va a usar para crear recursos. | Necesario |
    | -ResourceGroup                              | Nombre del grupo de recursos de Azure que contiene o contendrá el almacén de claves. | Necesario |
    | -KeyVaultName                               | Instancia de Azure Key Vault que almacenará el secreto o certificado de la aplicación de migración de buzones. | Necesario |
    | -CertificateName                            | Nombre del certificado al generar o buscar un certificado en el almacén de claves. | Necesario |
    | -CertificateSubject                         | Nombre del firmante del certificado de Azure Key Vault, como CN = contoso_fabrikam. | Necesario |
    | -ExistingApplicationId                      | Aplicación de migración de correo para usar si ya se creó una. | Opcional |
    | -AzureAppPermissions                        | Los permisos que se deben dar a la aplicación de migración de buzones de correo, como Exchange o MSGraph (Exchange para mover buzones de correo, MSGraph para usar esta aplicación para enviar una invitación de vínculo de consentimiento al espacio empresarial de recursos). | Necesario |
    | -UseAppAndCertGeneratedForSendingInvitation | Parámetro de uso de la aplicación creada para la migración que se va a usar para enviar la invitación del vínculo de consentimiento al administrador del espacio empresarial de origen. Si no está presente, se le pedirá a las credenciales del administrador de destino que se conecten al administrador de invitaciones de Azure y que envíen la invitación como administrador de destino. | Opcional |
    | -KeyVaultAuditStorageAccountName            | La cuenta de almacenamiento en la que se almacenarán los registros de auditoría del almacén clave. | Opcional |
    | -KeyVaultAuditStorageResourceGroup          | El grupo de recursos que contiene la cuenta de almacenamiento para almacenar los registros de auditoría de bóveda clave. | Opcional |
    ||||

6. La secuencia de comandos se pausará y le pedirá que acepte o dé su consentimiento a la aplicación de migración de buzones de Exchange que se creó durante este proceso. Aquí le mostramos un ejemplo.

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. Se mostrará una dirección URL en la sesión de PowerShell remoto. Copie el vínculo proporcionado para el consentimiento del espacio empresarial y péguelo en un explorador Web.

8. Inicie sesión con sus credenciales de administrador global. Cuando aparezca la siguiente pantalla, seleccione **Aceptar**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Cuadro de diálogo aceptar permisos":::
    
9. Vuelva a la sesión remota de PowerShell y presione Entrar para continuar.

10. El script configurará los restantes objetos de instalación. Aquí le mostramos un ejemplo.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

Se ha completado la configuración de administración de destino.

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Instrucciones paso a paso para el administrador del espacio empresarial de origen

1.  Inicie sesión en su buzón de correo como el-ResourceTenantAdminEmail especificado por el administrador de destino durante la instalación. Busque la invitación por correo electrónico del inquilino de destino y, después, seleccione el botón **Introducción** .

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Se ha invitado (cuadro de diálogo)":::

2. Seleccione **Aceptar** para aceptar la invitación.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Cuadro de diálogo para aceptar permisos":::

   > [!NOTE]
   > Si no obtiene este correo electrónico o no lo encuentra, el administrador del espacio empresarial de destino le proporcionó una dirección URL directa que puede darle para aceptar la invitación. La dirección URL debe encontrarse en la transcripción de la sesión de PowerShell remoto del administrador de inquilinos de destino.

3. En el centro de administración de Microsoft 365 o en una sesión remota de PowerShell, cree uno o varios grupos de seguridad habilitados para correo para controlar la lista de buzones que permite el inquilino de destino extraer (mover) del inquilino de origen al inquilino de destino. No es necesario rellenar este grupo por adelantado, pero se debe proporcionar al menos un grupo para ejecutar los pasos de configuración (Script). No se admiten los grupos anidados. 

4. Descargue [aquí](https://github.com/microsoft/cross-tenant/releases/tag/Preview)el script de SetupCrossTenantRelationshipForTargetResource.ps1 para la configuración del inquilino de origen del repositorio de github. 

5. Cree una conexión de PowerShell remota con los permisos de administrador de Exchange en el inquilino de origen. No se necesitan permisos de administrador global para configurar el inquilino de origen, solo el inquilino de destino a causa del proceso de creación de la aplicación de Azure.

6. Cambie el directorio a la ubicación del script o Compruebe que el script esté guardado actualmente en la ubicación actual de la sesión de PowerShell remoto.

7. Ejecute el script con los siguientes valores y parámetros necesarios.

    | Parámetro | Valor |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Grupo de seguridad habilitado para correo electrónico creado por el inquilino de origen para las identidades y los buzones que están en el ámbito de la migración. |
    | -ResourceTenantDomain | Nombre de dominio del inquilino de origen, como Fabrikam \. onmicrosoft.com. |
    | -TargetTenantDomain | Nombre de dominio del inquilino de destino, como contoso \. onmicrosoft.com. |
    | -ApplicationId | IDENTIFICADOR de la aplicación de Azure (GUID) de la aplicación usada para la migración. IDENTIFICADOR de la aplicación disponible a través de Azure portal (Azure AD, aplicaciones empresariales, nombre de la aplicación, identificador de la aplicación) o incluido en el correo electrónico de invitación.  |
    | -TargetTenantId | IDENTIFICADOR de inquilino del inquilino de destino. Por ejemplo, el identificador de inquilino de Azure AD de Contoso \. onmicrosoft.com tenant. |
    |||
    
    Aquí le mostramos un ejemplo.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

Se ha completado la configuración del administrador de origen.

### <a name="verify-setup"></a>Comprobar la configuración

Compruebe que la relación de la organización en los inquilinos de origen y de destino y el extremo de migración en el destino se hayan creado correctamente.

#### <a name="target-tenant"></a>Inquilino de destino

**Relación de organización**

Compruebe que el objeto de relación de organización se haya creado y configurado con este comando.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Aquí le mostramos un ejemplo:

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Extremo de migración**

Compruebe que el objeto de extremo de migración se haya creado y configurado con este comando.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Aquí le mostramos un ejemplo.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Inquilino de origen

**Relación de organización**

Compruebe que el objeto de relación de organización se haya creado y configurado con este comando.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
Aquí le mostramos un ejemplo.

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Mover buzones de nuevo al origen inicial

Si es necesario volver a mover un buzón de correo al inquilino de origen inicial, se debe ejecutar el mismo conjunto de pasos y scripts en los nuevos inquilinos de origen y de destino. El objeto de relación de organización existente se actualizará o se anexará, no se volverá a crear.

## <a name="prepare-target-user-objects-for-migration"></a>Preparar objetos de usuario de destino para la migración

Los usuarios que migren deben estar presentes en el inquilino de destino y en el sistema de Exchange Online (como MailUsers) marcado con atributos específicos para habilitar los movimientos entre inquilinos. Se producirá un error en el sistema para los usuarios que no se hayan configurado correctamente en el espacio empresarial de destino. En la siguiente sección se detallan los requisitos de objetos MailUser para el inquilino de destino.

### <a name="prerequisites"></a>Requisitos previos
  
Debe asegurarse de que los siguientes objetos y atributos se establecen en la organización de destino.  

1. Para los buzones que se mueven de una organización de origen, debe aprovisionar un objeto MailUser en la organización de destino: 
   - El MailUser de destino debe tener estos atributos del buzón de origen o asignarse con el nuevo objeto de usuario:
      - ExchangeGUID (flujo directo desde el origen hasta el destino): el GUID del buzón debe coincidir. El proceso de traslado no continuará si no está presente en el objeto de destino. 
      - ArchiveGUID (flujo directo desde el origen hasta el destino): el GUID de archivo debe coincidir. El proceso de traslado no continuará si no está presente en el objeto de destino. (Solo es necesario si el buzón de origen está habilitado para el archivo). 
      - LegacyExchangeDN (flujo como proxyAddress, "x500: <LegacyExchangeDN> ") – el legacyExchangeDN debe estar presente en el MailUser de destino como x500: proxyAddress. Los procesos de movimiento no continuarán si no está presente en el objeto de destino. 
      - UserPrincipalName – UPN se alineará con la nueva identidad o compañía de destino del usuario (por ejemplo, user@northwindtraders.onmicrosoft.com). 
      - SMTPAddress principal: la dirección SMTP principal se alineará con la nueva empresa del usuario (por ejemplo, user@northwind.com). 
      - TargetAddress/ExternalEmailAddress – MailUser hará referencia al buzón actual del usuario hospedado en el inquilino de origen (por ejemplo, user@contoso.onmicrosoft.com). Al asignar este valor, compruebe que también está asignando PrimarySMTPAddress o que este valor establecerá PrimarySMTPAddress, lo que provocará errores de movimiento. 
      - No puede agregar direcciones proxy SMTP heredadas desde el buzón de origen al usuario MailUser. Por ejemplo, no puede mantener contoso.com en la unidad MEU en los objetos de inquilino de fabrikam.onmicrosoft.com). Los dominios están asociados solo a un inquilino de Azure AD o Exchange Online.
 
    Ejemplo de objeto de MailUser de **destino** :
 
    | Atributo             | Valor                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | Alias                 | LaraN                                                                                                                    |
    | RecipientType         | MailUser                                                                                                                 |
    | RecipientTypeDetails  | MailUser                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders \. onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara \. Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP: LaraN@contoso \. onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = First Organization/ou = grupo administrativo de Exchange                                                                   |
    |                       | (FYDIBOHF23SPDLT)/CN = Recipients/CN = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | x500:/o = primera organización o unidad organizativa = grupo administrativo de Exchange (FYDIBOHF23SPDLT)/CN = destinatarios/CN = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | SMTP: LaraN@northwindtraders \. onmicrosoft.com                                                                              |
    |                       | SMTP: Lara \. Newton@northwind.com                                                                                           |
    |||

   Ejemplo de objeto de buzón de **origen** :

   | Atributo             | Valor                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | Alias                 | LaraN                                                                    |
   | RecipientType         | UserMailbox                                                              |
   | RecipientTypeDetails  | UserMailbox                                                              |
   | UserPrincipalName     | LaraN@contoso \. onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara \. Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = First Organization/ou = grupo administrativo de Exchange                   |
   |                       | (FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | SMTP: LaraN@contoso \. onmicrosoft.com 
   |                       | SMTP: Lara \. Newton@contoso.com          |
   |||

   - Es posible que ya se incluyan atributos adicionales en Exchange Hybrid Writer back. Si no es así, se deben incluir. 
   - msExchBlockedSendersHash – escribe datos de remitentes seguros y bloqueados en línea de los clientes en una implementación local de Active Directory.
   - msExchSafeRecipientsHash – escribe datos de remitentes seguros y bloqueados en línea de los clientes en una implementación local de Active Directory.
   - msExchSafeSendersHash – escribe datos de remitentes seguros y bloqueados en línea de los clientes en una implementación local de Active Directory.

2. Si el buzón de origen está en LitigationHold y el tamaño de los elementos recuperables del buzón de origen es mayor que el valor predeterminado de la base de datos (30 GB), el movimiento no continuará porque la cuota de destino sea menor que el tamaño del buzón de origen. Puede actualizar el objeto MailUser de destino para realizar la transición de las marcas de buzón ELC del entorno de origen al destino, lo que activa el sistema de destino para expandir la cuota del MailUser a 100 GB, lo que permite mover al destino. Estas instrucciones funcionarán solo para la identidad híbrida que ejecuta Azure AD Connect, ya que los comandos para marcar las marcas ELC no se exponen a los administradores de espacios empresariales.

    >[!Note]
    > MUESTRA: COMO ES, SIN GARANTÍA<br/>Esta secuencia de comandos presupone la conexión con el buzón de origen (para obtener los valores de origen) y el destino local de Active Directory (para marcar el objeto ADUser). Si el origen tiene habilitada una recuperación por juicio o un elemento único, establézcalo en la cuenta de destino.  Esto aumentará el tamaño de la papelera de la cuenta de destino a 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. Los inquilinos no híbridos de destino pueden modificar la cuota de la carpeta elementos recuperables para la MailUsers antes de la migración, mediante la ejecución del siguiente comando para habilitar la retención por juicio en el objeto MailUser y aumentar la cuota a 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Nota Esto no funcionará para los inquilinos en entornos híbridos.

4. Es necesario que los usuarios de la organización de destino tengan una licencia con las suscripciones de Exchange Online adecuadas para la organización. Puede aplicar una licencia por anticipado a un movimiento de buzón de correo, pero solo una vez que el MailUser de destino esté correctamente configurado con ExchangeGUID y direcciones de proxy. La aplicación de una licencia antes de aplicar el ExchangeGUID dará como resultado un nuevo buzón aprovisionado en la organización de destino. 

    > [!Note]
    > Cuando se aplica una licencia en un objeto Mailbox o MailUser, todos los tipos de SMTP proxyAddresses se borran para garantizar que solo los dominios comprobados se incluyen en la matriz de EmailAddresses de Exchange. 

5. Debe asegurarse de que el MailUser de destino no tiene un ExchangeGuid anterior que no coincide con el ExchangeGuid de origen. Esto puede ocurrir si la MEU de destino fue previamente autorizada para Exchange Online y ha aprovisionado un buzón de correo. Si el MailUser de destino ha sido previamente autorizado para o tenía un ExchangeGuid que no coincide con el ExchangeGuid de origen, debe realizar una limpieza de la unidad MEU de la nube. Para estos MEU en la nube, puede ejecutar el `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` comando. 

    > [!Caution]
    > Este proceso es irreversible. Si el objeto tiene un buzón de softDeleted, no se podrá restaurar después de este punto. Sin embargo, una vez desactivada, puede sincronizar el ExchangeGuid correcto con el objeto de destino y MRS conectará el buzón de origen al buzón de destino recién creado. (Consulte el blog de EHLO de referencia en el nuevo parámetro). 
 
    Buscar objetos que eran buzones anteriores mediante este comando.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    Aquí le mostramos un ejemplo. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    Borre el buzón de correo eliminado temporalmente con este comando.

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    Aquí le mostramos un ejemplo.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a>Realizar migraciones de buzones de correo

Las migraciones de buzones de correo de Exchange entre inquilinos se envían como lotes de migración iniciados desde el inquilino de destino. Esto es similar a la forma en que funcionan los lotes de migración de la incorporación al migrar de Exchange local a Microsoft 365. 

### <a name="create-migration-batches"></a>Crear lotes de migración

Este es un cmdlet de lote de migración de ejemplo para iniciar los movimientos.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> La dirección de correo electrónico del archivo CSV debe ser la especificada en el inquilino de destino, no el inquilino de origen.

El envío por lotes de migración también se admite desde el nuevo centro de administración de Exchange cuando se selecciona la opción Cross-tenant.
 
#### <a name="update-on-premises-mailusers"></a>Actualizar MailUsers local

Una vez que el buzón de correo se mueve del origen al destino, debe asegurarse de que los usuarios de correo locales, tanto de origen como de destino, se actualizan con el nuevo targetAddress. En los ejemplos, el targetDeliveryDomain usado en la transferencia es **contoso \. onmicrosoft.com**. Actualice los usuarios de correo con este targetAddress.
 
## <a name="frequently-asked-questions"></a>Preguntas más frecuentes
 
**¿Es necesario actualizar RemoteMailboxes en el origen local después del traslado?**
 
Sí, debe actualizar el targetAddress (RemoteRoutingAddress/ExternalEmailAddress) de los usuarios locales de origen cuando el buzón de origen del espacio empresarial se mueva al inquilino de destino.  Mientras que el enrutamiento de correo puede seguir las referencias entre varios usuarios de correo con diferentes targetAddresses, las búsquedas de disponibilidad para los usuarios de correo deben dirigirse a la ubicación del usuario del buzón. Las búsquedas de disponibilidad no realizarán varias redirecciones. 
 
**¿El contenido de la carpeta de chat de Teams migra entre los inquilinos?** 

No, el contenido de la carpeta de chats de Microsoft Teams no migra el inquilino cruzado. 
 
**¿Cómo puedo ver solo movimientos que son movimientos entre inquilinos, no mis movimientos de incorporación y retirada?**

Use el `-flags` parámetro. Aquí le mostramos un ejemplo.

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
**¿Puede proporcionar scripts de ejemplo para copiar atributos usados en las pruebas?**

> [!Note]
> MUESTRA: COMO ES, SIN GARANTÍA<br/>Esta secuencia de comandos presupone una conexión al buzón de origen (para obtener los valores de origen) y a los servicios de dominio de Active Directory locales de destino (para marcar el objeto ADUser). Si el origen tiene habilitada una recuperación por juicio o un elemento único, establézcalo en la cuenta de destino.  Esto aumentará el tamaño de la papelera de la cuenta de destino a 100 GB.

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
**¿Cómo se obtiene acceso a Outlook el día 1 después de que se mueva el buzón de uso?**

Dado que solo un inquilino puede poseer un dominio, la anterior SMTPAddress primaria no se asociará al usuario en el inquilino de destino cuando se complete el movimiento del buzón; solo los dominios asociados con el nuevo inquilino. Outlook usa el nuevo UPN de los usuarios para autenticarse en el servicio y el perfil de Outlook espera encontrar la SMTPAddress principal heredada para que se corresponda con el buzón del sistema de destino. Como la dirección heredada no se encuentra en el sistema de destino, el perfil de Outlook no se conectará para encontrar el buzón recién movido. 

Para esta implementación inicial, los usuarios tendrán que volver a crear su perfil con el nuevo UPN, la dirección SMTP principal y volver a sincronizar el contenido OST. 

> [!Note]
> Planee según los usuarios por lotes para la finalización. Debe tener en cuenta la capacidad y el uso de red cuando se crean perfiles de cliente de Outlook y los archivos OST y OAB subsiguientes se descargan a los clientes. 
 
**¿En qué roles RBAC de Exchange debo ser miembro para configurar o completar un movimiento entre inquilinos?**
 
Hay una matriz de funciones basadas en la suposición de derechos delegados al ejecutar un movimiento de buzón. Actualmente, se requieren dos roles:  

- La primera función es para una tarea de configuración de una sola vez que establece la autorización de mover el contenido hacia dentro o fuera del límite de la organización o del espacio empresarial. Como la transferencia de datos del control organizacional es una preocupación fundamental para todas las empresas, decidimos con el rol asignado más alto del administrador de la organización (OrgAdmin). Este rol debe modificar o configurar un nuevo OrganizationRelationship que defina el-MailboxMoveCapability con la organización remota. Solo el OrgAdmin puede modificar la configuración de MailboxMoveCapability, mientras que el administrador federado compartido puede administrar otros atributos de OrganizationRelationhip. 
 
- El rol de ejecución de los comandos de movimiento reales se puede delegar en una función de nivel inferior. El rol de mover buzones de correo tiene asignada la capacidad de mover buzones dentro o fuera de la organización mediante el `-RemoteTenant` parámetro.  

**¿Cómo se destina la dirección SMTP seleccionada para targetAddress (TargetDeliveryDomain) en el buzón convertido (a la conversión de MailUser)?**
 
Los movimientos de buzones de correo de Exchange con MRS diseñan el targetAddress en el buzón de origen inicial al convertirlo en un MailUser con una dirección de correo electrónico (proxyAddress) en el objeto de destino. El proceso toma el valor-TargetDeliveryDomain que se pasa al comando move y, a continuación, comprueba si el dominio tiene un proxy correspondiente en el lado de destino. Cuando encontramos una coincidencia, se usa la coincidencia de proxyAddress para establecer ExternalEmailAddress (targetAddress) en el objeto de buzón de correo convertido (ahora MailUser).
 
**¿Cómo se realiza la transición de permisos de buzón?**

Los permisos de buzón incluyen enviar en nombre de y acceso al buzón: 

- Enviar en nombre de (AD: publicDelegates) almacena el DN de los destinatarios con acceso al buzón de un usuario como delegado. Este valor se almacena en Active Directory y actualmente no se mueve como parte de la transición del buzón de correo. Si el buzón de origen tiene un grupo publicDelegates, deberá volver a estampar publicDelegates en el buzón de destino una vez que la conversión de la unidad MEU a la del buzón de correo se complete en el entorno de destino con el `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` comando. 
 
- Los permisos de buzón que se almacenan en el buzón se moverán con el buzón cuando la entidad de destino y el delegado se muevan al sistema de destino. Por ejemplo, al usuario TestUser_7 se le concede FullAccess al buzón TestUser_8 en el inquilino SourceCompany.onmicrosoft.com. Una vez que el movimiento del buzón se haya completado a TargetCompany.onmicrosoft.com, se configuran los mismos permisos en el directorio de destino. A continuación, se muestran ejemplos que usan *Get-MailboxPermission* para TestUser_7 en los inquilinos de origen y de destino. Los cmdlets de Exchange llevan el prefijo de origen y destino en consecuencia. 
 
A continuación, se muestra un ejemplo del resultado del permiso de buzón antes de un movimiento. 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
A continuación, se muestra un ejemplo del resultado del permiso de buzón de correo después del traslado. 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> NO se admiten los permisos entre buzones de correo y calendario entre inquilinos. Debe organizar los principales y los delegados en lotes de movimiento consolidado para que estos buzones conectados se pasen al mismo tiempo del inquilino de origen. 
 
## <a name="known-issues"></a>Problemas conocidos 

-  **Problema: los archivos expandidos automáticamente no se pueden migrar.** La característica de migración entre espacios empresariales admite la migración del buzón de correo principal y el buzón de archivo para un usuario específico. Sin embargo, si el usuario del origen tiene un archivo de expansión automática, lo que significa más de un buzón de archivo, la característica no puede migrar los archivos adicionales.

- **Problema: MailUsers en la nube con el bloque de la MRS con SMTP no poseído se mueve el fondo.** Al crear objetos de MailUser de inquilino de destino, debe asegurarse de que todas las direcciones de proxy SMTP pertenezcan a la organización de inquilinos de destino. Si existe un proxyAddress SMTP en el usuario de correo de destino que no pertenece al inquilino local, se evita la conversión de MailUser en Mailbox. Esto se debe a la garantía de que los objetos de buzón solo pueden enviar correo desde dominios para los que el inquilino tenga autoridad (dominios reclamados por el inquilino): 
- 
   - Cuando se sincronizan usuarios de forma local mediante Azure AD Connect, se aprovisionan objetos de MailUser locales con ExternalEmailAddress que señalan al inquilino de origen donde existe el buzón (laran@contoso \. onmicrosoft.com) y se marca PrimarySMTPAddress como un dominio que reside en el inquilino de destino (Lara.Newton@northwind \. com). Estos valores se sincronizan con el inquilino y un usuario de correo adecuado se aprovisionan y están listos para la migración. Aquí se muestra un objeto de ejemplo.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > La dirección de *contoso. en Microsoft \. com* *no* está presente en la matriz EmailAddresses/proxyAddresses.

- **Problema: los objetos de MailUser con direcciones SMTP principales "externas" se modifican o se restablecen a "Internal" dominios reclamados por la empresa**

   Los objetos MailUser son punteros a buzones no locales. En el caso de las migraciones de buzones de correo entre inquilinos, usamos objetos de MailUser para representar el buzón de origen (desde el punto de vista de la organización de destino) o el buzón de correo de destino (desde el punto de vista de la organización de origen). El MailUsers tendrá un ExternalEmailAddress (targetAddress) que apunta a la dirección SMTP del buzón real (ProxyTest \@ fabrikam \. onmicrosoft.com) y la dirección primarySMTP que representa la dirección SMTP que se muestra del usuario del buzón de correo en el directorio. Algunas organizaciones optan por Mostrar la dirección SMTP principal como una dirección SMTP externa, no como una dirección propiedad o comprobada por el inquilino local (como fabrikam.com en lugar de contoso.com).  Sin embargo, una vez que un objeto de plan de servicio de Exchange se aplica a el MailUser a través de operaciones de licencia, la dirección SMTP principal se modifica para mostrarse como un dominio comprobado por la organización local (contoso.com). Hay dos motivos posibles:
   
   - Cuando se aplica un plan de servicio de Exchange a un MailUser, el proceso de Azure AD comienza a forzar la depuración del proxy para garantizar que la organización local no puede enviar correo, falsificado o correo desde otro espacio empresarial. Cualquier dirección SMTP de un objeto Recipient con estos planes de servicio se quitará si la dirección no es comprobada por la organización local. Como en el caso del ejemplo, el inquilino de \. contoso ONMICROSOFT.com no comprueba el dominio com de Fabikam \. , por lo que el borrado quita el \. dominio com de fabrikam. Si desea conservar este dominio externo en MailUser, antes de la migración o después de la migración, debe modificar los procesos de migración para eliminar las licencias una vez que se complete el movimiento o antes de la transferencia para asegurarse de que los usuarios tienen aplicada la personalización de marca externa esperada. Deberá asegurarse de que el objeto Mailbox tiene una licencia adecuada para no afectar al servicio de correo.<br/><br/>Aquí se muestra un script de ejemplo para quitar los planes de servicio de un MailUser en el inquilino de Contoso \. onmicrosoft.com.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Aquí se muestran los resultados del conjunto de ServicePlans asignado.

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
 
       El PrimarySMTPAddress del usuario ya no está borrado. El dominio fabrikam.com no es propiedad del inquilino contoso.onmicrosoft.com y se conservará como la dirección SMTP principal que se muestra en el directorio.

       Aquí le mostramos un ejemplo.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Cuando msExchRemoteRecipientType se establece en 8 (DeprovisionMailbox), para la MailUsers local que se migra al espacio empresarial de destino, la lógica de limpieza de proxy en Azure quitará los dominios no propietarios y restablecerá el primarySMTP en un dominio propietario. Al borrar msExchRemoteRecipientType en el MailUser local, la lógica de limpieza de proxy ya no se aplica. <br/><br>A continuación se muestra el conjunto completo de los planes de servicio posibles que incluyen Exchange Online.

   | Nombre                                              |
   |---------------------------------------------------|
   | Almacenamiento avanzado de eDiscovery (500 GB)               |
   | Caja de seguridad del cliente                                  |
   | Prevención de pérdida de datos                              |
   | Servicios de Exchange Enterprise CAL (EOP, DLP)       |
   | Aspectos básicos de Exchange                               |
   | Base de Exchange                               |
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
   | Barreras de la información                              |
   | Information Protection para Office 365 - Premium   |
   | Information Protection para Office 365 - Estándar  |
   | Información de myanalytics                           |
   | Microsoft 365 Advanced Auditing                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (Completo)                      |
   | eDiscovery avanzado de Office 365                    |
   | Microsoft defender para Office 365 (plan 1)    |
   | Microsoft defender para Office 365 (plan 2)    |
   | Office 365 Privileged Access Management           |
   | Outlook Customer Manager                          |
   | Cifrado Premium en Office 365                  |
   || 
 
