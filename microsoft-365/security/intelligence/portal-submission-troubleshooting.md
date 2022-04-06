---
title: Solución de problemas de errores del portal msi causados por el bloque de administración
description: Solución de problemas de errores del portal msi
ms.reviewer: ''
keywords: seguridad, ayuda de envío de ejemplo, archivo de malware, archivo de virus, archivo troyano, enviar, enviar a Microsoft, enviar una muestra, virus, troyano, gusano, no detectado, no detecta, correo electrónico microsoft, malware de correo electrónico, creo que se trata de malware, creo que es un virus, donde puedo enviar un virus, es este un virus, MSE, no detecta, sin firma, sin detección, archivo sospechoso,  MMPC, Centro de protección contra malware de Microsoft, investigadores, analista, WDSI, inteligencia de seguridad
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
ms.openlocfilehash: 544e96bd0a3985856f47bc8df424a2c2932f3c7e
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665676"
---
# <a name="troubleshooting-malware-submission-errors-caused-by-administrator-block"></a>Solución de problemas de errores de envío de malware causados por el bloque de administrador

En algunos casos, un bloque de administrador puede causar problemas de envío al intentar enviar un archivo potencialmente infectado al [sitio web de Inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi) para su análisis. El siguiente proceso muestra cómo resolver este problema.

## <a name="review-your-settings"></a>Revisar la configuración

Abra la [configuración de la aplicación de Azure Enterprise](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/UserSettings/menuId/). En **Enterprise AplicacionesUsuarios** >   **pueden dar su consentimiento a las aplicaciones que acceden a los datos de la empresa en su nombre**, compruebe si está seleccionado Sí o No.

- Si se selecciona **No**, un administrador de Azure AD para el inquilino del cliente deberá proporcionar su consentimiento para la organización. En función de la configuración con Azure AD, es posible que los usuarios puedan enviar una solicitud directamente desde el mismo cuadro de diálogo. Si no hay ninguna opción para solicitar el consentimiento del administrador, los usuarios deben solicitar estos permisos para agregarlos a su administrador de Azure AD. Vaya a la sección siguiente para obtener más información.

- Si se selecciona **Sí**, asegúrese de que la configuración de la aplicación De inteligencia de seguridad de Windows Defender **Habilitada para que los usuarios inicien sesión esté establecida en** **Sí** [en Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Properties/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/4a918a14-4069-4108-9b7d-76486212d75d). **Si no** está seleccionado, deberá solicitar un administrador de Azure AD habilitarlo.

## <a name="implement-required-enterprise-application-permissions"></a>Implementación de permisos de aplicación de Enterprise necesarios

Este proceso requiere un administrador global o de la aplicación en el inquilino.

1. Abra [Enterprise Configuración de la aplicación](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Permissions/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/4a918a14-4069-4108-9b7d-76486212d75d).
2. Seleccione **Conceder consentimiento de administrador para la organización**.
3. Si puede hacerlo, revise los permisos de API necesarios para esta aplicación, como se muestra en la siguiente imagen. Proporcione el consentimiento para el inquilino.

    ![conceder la imagen de consentimiento.](../../media/security-intelligence-images/msi-grant-admin-consent.jpg)

4. Si el administrador recibe un error al intentar proporcionar el consentimiento manualmente, pruebe la [opción 1](#option-1-approve-enterprise-application-permissions-by-user-request) o [la opción 2](#option-2-provide-admin-consent-by-authenticating-the-application-as-an-admin) como posibles soluciones alternativas.

## <a name="option-1-approve-enterprise-application-permissions-by-user-request"></a>Opción 1 Aprobar permisos de aplicación empresarial por solicitud de usuario

> [!NOTE]
> Actualmente se trata de una característica en versión preliminar.

Azure Active Directory los administradores deberán permitir que los usuarios soliciten el consentimiento del administrador a las aplicaciones. Compruebe que la configuración está configurada en **Sí** en [Enterprise aplicaciones](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/UserSettings/menuId/).

![Enterprise la configuración de usuario de las aplicaciones.](../../media/security-intelligence-images/msi-enterprise-app-user-setting.jpg)

Encontrará más información en [Configurar el flujo de trabajo de consentimiento del administrador](/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Una vez comprobada esta configuración, los usuarios pueden pasar por el inicio de sesión del cliente empresarial en [Microsoft Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) y enviar una solicitud de consentimiento del administrador, incluida la justificación.

![Flujo de inicio de sesión de Contoso.](../../media/security-intelligence-images/msi-contoso-approval-required.png)

El administrador podrá revisar y aprobar los permisos de aplicación [solicitudes de consentimiento del administrador de Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/AccessRequests/menuId/).

Después de proporcionar el consentimiento, todos los usuarios del inquilino podrán usar la aplicación.

## <a name="option-2-provide-admin-consent-by-authenticating-the-application-as-an-admin"></a>Opción 2 Proporcionar consentimiento de administrador mediante la autenticación de la aplicación como administrador

Este proceso requiere que los administradores globales pasen por el flujo de inicio de sesión de Enterprise cliente en [Microsoft Security Intelligence](https://www.microsoft.com/wdsi/filesubmission).

![Flujo de inicio de sesión de consentimiento.](../../media/security-intelligence-images/msi-microsoft-permission-required.jpg)

A continuación, los administradores revisan los permisos y asegúrese de seleccionar **Consentimiento en nombre de su organización** y, a continuación, seleccione **Aceptar**.

Todos los usuarios del inquilino ahora podrán usar esta aplicación.

## <a name="option-3-delete-and-readd-app-permissions"></a>Opción 3: Eliminar y leer permisos de aplicación

Si ninguna de estas opciones resuelve el problema, pruebe los pasos siguientes (como administrador):

1. Quite las configuraciones anteriores de la aplicación. Vaya a [Enterprise aplicaciones](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Properties/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/982e94b2-fea9-4d1f-9fca-318cda92f90b) y seleccione **Eliminar**.

   ![Eliminar permisos de aplicación.](../../media/security-intelligence-images/msi-properties.png)

2. Capture TenantID desde [Propiedades](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).

3. Reemplace {tenant-id} por el inquilino específico que necesita conceder consentimiento a esta aplicación en la dirección URL siguiente. Copie esta dirección URL en el explorador. El resto de los parámetros ya están completados.
``https://login.microsoftonline.com/{tenant-id}/v2.0/adminconsent?client_id=f0cf43e5-8a9b-451c-b2d5-7285c785684d&state=12345&redirect_uri=https%3a%2f%2fwww.microsoft.com%2fwdsi%2ffilesubmission&scope=openid+profile+email+offline_access``

   ![Permisos necesarios.](../../media/security-intelligence-images/msi-microsoft-permission-requested-your-organization.png)

4. Revise los permisos necesarios para la aplicación y, a continuación, seleccione **Aceptar**.

5. Confirme que los permisos se aplican en el [Azure Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ManagedAppMenuBlade/Permissions/appId/f0cf43e5-8a9b-451c-b2d5-7285c785684d/objectId/ce60a464-5fca-4819-8423-bcb46796b051).

   ![Revise que se aplican los permisos.](../../media/security-intelligence-images/msi-permissions.jpg)

6. Inicie sesión en [Microsoft Security Intelligence](https://www.microsoft.com/wdsi/filesubmission) como usuario empresarial con una cuenta que no sea de administrador para ver si tiene acceso.

 Si la advertencia no se resuelve después de seguir estos pasos de solución de problemas, llame al soporte técnico de Microsoft.