---
title: Solucionar errores del portal MSI causados por el bloqueo de administración
description: Solucionar errores del portal MSI
ms.reviewer: ''
keywords: security, sample submission help, malware file, virus file, trojan file, submit, send to Microsoft, submit a sample, virus, trojan, worm, undetected, doesn't detect, email microsoft, email malware, I think this is malware, I think it's a virus, where can I send a virus, is this a virus, MSE, doesn't detect, no signature, no detection, suspect file,  MMPC, Centro de protección contra malware de Microsoft, investigadores, analistas, WDSI, inteligencia de seguridad
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: e70eb5192a1fd6171b8e515509ad336aa99a2c63
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680360"
---
# <a name="troubleshooting-malware-submission-errors-caused-by-administrator-block"></a>Solución de errores de envío de malware causados por el bloqueo de administrador
En algunos casos, un bloque de administrador puede causar problemas de envío cuando intenta enviar un archivo potencialmente infectado al sitio web de inteligencia de [Microsoft Security](https://www.microsoft.com/wdsi) para su análisis. El siguiente proceso muestra cómo resolver este problema.

## <a name="review-your-settings"></a>Revisar la configuración
Abra la configuración [Enterprise aplicación de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/UserSettings/menuId/). En **Enterprise ApplicationsUsers** >   puede dar su consentimiento para que las aplicaciones accedan a datos de la compañía en **su** nombre, compruebe si sí o no está seleccionado.

- Si **se** selecciona No, Azure AD administrador del inquilino del cliente tendrá que proporcionar su consentimiento para la organización. Según la configuración con Azure AD, es posible que los usuarios puedan enviar una solicitud directamente desde el mismo cuadro de diálogo. Si no hay ninguna opción para solicitar el consentimiento de administrador, los usuarios deben solicitar que estos permisos se agregó a su administrador de Azure AD. Vaya a la sección siguiente para obtener más información.

- Si **está** seleccionado Sí, asegúrese de que Windows Defender configuración de la aplicación Inteligencia de seguridad Habilitada para que **los** usuarios inicien sesión? está establecida en **Sí** [en Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Properties/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/4a918a14-4069-4108-9b7d-76486212d75d).Si **no** está seleccionado, tendrás que solicitar un administrador Azure AD habilitarlo. 
  
## <a name="implement-required-enterprise-application-permissions"></a>Implementar permisos Enterprise aplicación obligatoria 
Este proceso requiere un administrador global o de aplicación en el inquilino.
 1. Abra [Enterprise configuración de la aplicación](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Permissions/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/4a918a14-4069-4108-9b7d-76486212d75d). 
 2. Seleccione **Conceder consentimiento de administrador para la organización**.
 3. Si puede hacerlo, revise los permisos de api necesarios para esta aplicación, como se muestra en la siguiente imagen. Proporcionar consentimiento para el inquilino.

    ![conceder la imagen de consentimiento.](../../media/security-intelligence-images/msi-grant-admin-consent.jpg)

  4. Si el administrador recibe un error al intentar proporcionar el consentimiento manualmente, pruebe la [opción 1](#option-1-approve-enterprise-application-permissions-by-user-request) o [la opción 2](#option-2-provide-admin-consent-by-authenticating-the-application-as-an-admin) como soluciones alternativas posibles.
  
## <a name="option-1-approve-enterprise-application-permissions-by-user-request"></a>Opción 1 Aprobar permisos de aplicación empresarial por solicitud de usuario
> [!Note]
> Esta es actualmente una característica de vista previa.

Azure Active Directory administradores tendrán que permitir que los usuarios soliciten el consentimiento de administrador a las aplicaciones. Compruebe que la configuración está configurada en **Sí** [en Enterprise aplicaciones](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/UserSettings/menuId/).

![Enterprise de usuario de aplicaciones.](../../media/security-intelligence-images/msi-enterprise-app-user-setting.jpg)

Encontrará más información en [Configurar flujo de trabajo de consentimiento de administrador](/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Una vez comprobada esta configuración, los usuarios pueden pasar por el inicio de sesión del cliente de empresa en inteligencia de seguridad de [Microsoft](https://www.microsoft.com/wdsi/filesubmission) y enviar una solicitud de consentimiento de administrador, incluida la justificación.

![Flujo de inicio de sesión de Contoso.](../../media/security-intelligence-images/msi-contoso-approval-required.png)

El administrador podrá revisar y aprobar los permisos de aplicación solicitudes de [consentimiento de administrador de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/AccessRequests/menuId/).

Después de proporcionar el consentimiento, todos los usuarios del espacio empresarial podrán usar la aplicación.
  
## <a name="option-2-provide-admin-consent-by-authenticating-the-application-as-an-admin"></a>Opción 2 Proporcionar consentimiento de administrador autenticando la aplicación como administrador 
Este proceso requiere que los administradores globales pasen por el flujo Enterprise de inicio de sesión del cliente en inteligencia [de seguridad de Microsoft](https://www.microsoft.com/wdsi/filesubmission).

![Flujo de inicio de sesión de consentimiento.](../../media/security-intelligence-images/msi-microsoft-permission-required.jpg)

A continuación, los administradores revisan los permisos y se asegura de seleccionar **Consentimiento en nombre de** la organización y, a continuación, selecciona **Aceptar**.

Todos los usuarios del espacio empresarial ahora podrán usar esta aplicación.

## <a name="option-3-delete-and-readd-app-permissions"></a>Opción 3: Eliminar y leer permisos de aplicación
Si ninguna de estas opciones resuelve el problema, pruebe los siguientes pasos (como administrador):

1. Quite las configuraciones anteriores de la aplicación. Vaya a [Enterprise aplicaciones y](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Properties/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/982e94b2-fea9-4d1f-9fca-318cda92f90b) seleccione **eliminar**.

   ![Eliminar permisos de aplicación.](../../media/security-intelligence-images/msi-properties.png)

2. Capture TenantID de [Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).

3. Reemplace {tenant-id} por el inquilino específico que necesita conceder el consentimiento a esta aplicación en la dirección URL siguiente. Copie esta dirección URL en el explorador. El resto de los parámetros ya están completados. 
``https://login.microsoftonline.com/{tenant-id}/v2.0/adminconsent?client_id=f0cf43e5-8a9b-451c-b2d5-7285c785684d&state=12345&redirect_uri=https%3a%2f%2fwww.microsoft.com%2fwdsi%2ffilesubmission&scope=openid+profile+email+offline_access``

   ![Permisos necesarios.](../../media/security-intelligence-images/msi-microsoft-permission-requested-your-organization.png)

4. Revise los permisos requeridos por la aplicación y, a continuación, seleccione **Aceptar**. 

5. Confirme que los permisos se aplican en [Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Permissions/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/ce60a464-5fca-4819-8423-bcb46796b051).

   ![Revise que se aplican permisos.](../../media/security-intelligence-images/msi-permissions.jpg)
   
6. Inicie sesión en [inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi/filesubmission) como usuario de empresa con una cuenta que no sea de administrador para ver si tiene acceso.

 Si la advertencia no se resuelve después de seguir estos pasos de solución de problemas, llama al soporte técnico de Microsoft.