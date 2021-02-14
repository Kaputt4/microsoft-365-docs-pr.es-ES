---
title: Configurar Azure Rights Management para la versión anterior del cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: La versión anterior del cifrado de mensajes de Office 365 depende de Microsoft Azure Rights Management (anteriormente conocido como Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 879f4ec1db8a8cfe1fe3c8d3b1dd9e1fc68dd687
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165921"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Configurar Azure Rights Management para la versión anterior del cifrado de mensajes

En este tema se describen los pasos que debe seguir para activar y, a continuación, configurar Azure Rights Management (RMS), parte de Azure Information Protection, para usarlo con la versión anterior de Cifrado de mensajes de Office 365 (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Este artículo solo se aplica a la versión anterior de OME

Si aún no ha movido su organización a las nuevas funcionalidades de OME, pero ya ha implementado OME, la información de este artículo se aplica a su organización. Microsoft recomienda realizar un plan para pasar a las nuevas funcionalidades de OME tan pronto como sea razonable para su organización. Para obtener instrucciones, consulte Configurar las nuevas capacidades de cifrado de [mensajes de Office 365.](set-up-new-message-encryption-capabilities.md) Si desea obtener más información sobre cómo funcionan primero las nuevas funcionalidades, consulte Cifrado de mensajes de [Office 365.](ome.md) El resto de este artículo hace referencia al comportamiento de OME antes del lanzamiento de las nuevas funcionalidades de OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Requisitos previos para usar la versión anterior del cifrado de mensajes de Office 365
<a name="warmprereqs"> </a>

El cifrado de mensajes de Office 365 (OME), incluido IRM, depende de Azure Rights Management (Azure RMS). Azure RMS es la tecnología de protección que usa Azure Information Protection. Para usar OME, su organización debe incluir una suscripción a Exchange Online o Exchange Online Protection que, a su vez, incluya una suscripción de Azure Rights Management.
  
- Si no está seguro de lo que incluye su suscripción, consulte las descripciones del servicio de Exchange Online para la directiva de mensajes, la recuperación [y el cumplimiento.](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)

- Si tiene Azure Rights Management pero no está configurado para Exchange Online o Exchange Online Protection, en este artículo se explica cómo activar Azure Rights Management y, a continuación, se describe la mejor manera de configurar OME para trabajar con Azure Rights Management.

- Si ya ha configurado OME para que funcione con Azure Rights Management para Exchange Online o Exchange Online Protection, en función de cómo lo configure, es posible que esté listo para empezar a usar OME y sus nuevas funcionalidades inmediatamente. En este artículo se explica cómo determinar si ha configurado OME correctamente, qué hacer si necesita cambiar la configuración y qué sucede si decide no cambiar la configuración. Por ejemplo, para usar las nuevas funcionalidades, debe usar Azure RMS con OME. No puede usar las nuevas funcionalidades con un RMS de Active Directory local.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Activar Azure Rights Management para la versión anterior de OME en Office 365

Debe activar Azure Rights Management para que los usuarios de su organización puedan aplicar protección de la información a los mensajes que envían y abrir mensajes y archivos protegidos por el servicio Azure Rights Management. Para obtener instrucciones, consulte [Activar Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Una vez que haya completado la activación, vuelva aquí y continúe con las tareas de este artículo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configurar la versión anterior de OME para usar Azure RMS mediante la importación de dominios de publicación de confianza (TPD)

Un TPD es un archivo XML que contiene información sobre la configuración de administración de derechos de su organización. Por ejemplo, el TPD contiene información sobre el certificado de licencia del servidor (SLC) usado para firmar y cifrar certificados y licencias, las direcciones URL usadas para licencias y publicación, y así sucesivamente. El TPD se importa en la organización mediante Windows PowerShell.
  
> [!IMPORTANT]
> Anteriormente, podía elegir importar los TPD desde el servicio Active Directory Rights Management (AD RMS) a su organización. Sin embargo, esto le impedirá usar las nuevas funcionalidades de OME y no se recomienda. Si su organización está configurada actualmente de esta forma, Microsoft recomienda crear un plan para migrar de su RMS de Active Directory local a Azure Information Protection basado en la nube. Para obtener más información, vea [Migrar de AD RMS a Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) No podrá usar las nuevas funcionalidades de OME hasta que haya completado la migración a Azure Information Protection.
  
 **Para importar tpds desde Azure RMS**
  
1. [Conéctese a Exchange Online con PowerShell remoto.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. Elija la dirección URL de uso compartido de claves que corresponda a la ubicación geográfica de su organización:

|**Location**|**Url de ubicación de uso compartido de claves**|
|:-----|:-----|
|Norteamérica  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Unión Europea  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Sudamérica  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 Administración Pública (nube de la comunidad de administración pública)  <br/> Esta ubicación de uso compartido de claves de RMS está reservada para los clientes que han adquirido SKU de Office 365 para el gobierno.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Configure la ubicación de uso compartido de claves ejecutando el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) de la siguiente manera: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Por ejemplo, para configurar la ubicación de uso compartido de claves si su organización se encuentra en Norteamérica:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Ejecute el cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con el modificador -RMSOnline para importar el TPD desde Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Donde  *TPDName*  es el nombre que desea usar para el TPD. Por ejemplo, "TPD de Norteamérica de Contoso". 

5. Para comprobar que configuró correctamente su organización para usar el servicio Azure Rights Management, ejecute el cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con el modificador -RMSOnline de la siguiente manera:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Entre otras cosas, este cmdlet comprueba la conectividad con el servicio Azure Rights Management, descarga el TPD y comprueba su validez.

6. Ejecute el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) de la siguiente manera para deshabilitar que las plantillas de Azure Rights Management no estén disponibles en Outlook en la Web y Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Ejecute el cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) de la siguiente manera para habilitar Azure Rights Management para su organización de correo electrónico basada en la nube y configurarlo para usar Azure Rights Management para el cifrado de mensajes de Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Para comprobar que ha importado correctamente el TPD y habilitado Azure Rights Management, use el cmdlet Test-IRMConfiguration para probar la funcionalidad de Azure Rights Management. Para obtener más información, vea "Ejemplo 1" en [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Tengo la versión anterior de OME configurada con Active Directory Rights Management, no con Azure Information Protection, ¿qué puedo hacer?
<a name="importTPDs"> </a>

Puede seguir usando las reglas de flujo de correo de cifrado de mensajes de Office 365 existentes con Active Directory Rights Management, pero no puede configurar ni usar las nuevas funcionalidades de OME. En su lugar, debe migrar a Azure Information Protection. Para obtener información sobre la migración y lo que esto significa para su organización, vea Migrar [de AD RMS a Azure Information Protection.](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>Pasos siguientes
<a name="importTPDs"> </a>

Una vez que haya completado la configuración de Azure Rights Management, si desea habilitar las nuevas funcionalidades de OME, consulte Configurar las nuevas capacidades de cifrado de mensajes de [Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities) integradas sobre Azure Information Protection.
  
Después de configurar la organización para usar las nuevas funcionalidades de OME, está listo para definir reglas de flujo de correo para proteger los mensajes de correo electrónico con nuevas [capacidades de OME.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Temas relacionados
<a name="importTPDs"> </a>

[Cifrado en Office 365](encryption.md)
  
[Información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md)
  
[¿Qué es Azure Rights Management?](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
