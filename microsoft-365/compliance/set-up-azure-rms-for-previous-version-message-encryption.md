---
title: Configuración de Azure Rights Management para la versión anterior de Cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: La versión anterior de Office 365 Message Encryption depende de Microsoft Azure Rights Management (anteriormente conocida como Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 386056c282ea5f4ad996cc7ae7c50926436fe720
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66641370"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Configuración de Azure Rights Management para la versión anterior de Cifrado de mensajes

En este tema se describen los pasos que debe seguir para activar y configurar Azure Rights Management (RMS), parte de Azure Information Protection, para su uso con la versión anterior de Office 365 Message Encryption (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Este artículo solo se aplica a la versión anterior de OME

Si aún no ha movido su organización a Cifrado de mensajes de Microsoft Purview, pero ya ha implementado OME, la información de este artículo se aplica a su organización. Microsoft recomienda que realice un plan para pasar a Cifrado de mensajes de Microsoft Purview tan pronto como sea razonable para su organización. Para obtener instrucciones, consulte [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md). Si quiere obtener más información sobre cómo funcionan las nuevas funcionalidades primero, consulte [Cifrado de](ome.md) mensajes. El resto de este artículo hace referencia al comportamiento de OME antes de la publicación de Cifrado de mensajes de Microsoft Purview.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Requisitos previos para usar la versión anterior de Office 365 cifrado de mensajes
<a name="warmprereqs"> </a>

Office 365 cifrado de mensajes (OME), incluido IRM, depende de Azure Rights Management (Azure RMS). Azure RMS es la tecnología de protección que usa Azure Information Protection. Para usar OME, la organización debe incluir una suscripción Exchange Online o Exchange Online Protection que, a su vez, incluya una suscripción de Azure Rights Management.

- Si no está seguro de lo que incluye la suscripción, consulte las descripciones del servicio de Exchange Online para [directivas de mensajes, recuperación y cumplimiento](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

- Si tiene Azure Rights Management pero no está configurado para Exchange Online o Exchange Online Protection, en este artículo se explica cómo activar Azure Rights Management y, a continuación, se describe la mejor manera de configurar OME con la que trabajar. Azure Rights Management.

- Si ya ha configurado OME para que funcione con Azure Rights Management para Exchange Online o Exchange Online Protection, en función de cómo lo configure, es posible que esté listo para empezar a usar OME y sus nuevas funcionalidades de inmediato. En este artículo se explica cómo determinar si ha configurado OME correctamente, qué hacer si necesita cambiar la configuración y qué ocurre si decide no cambiar la configuración. Por ejemplo, para usar las nuevas funcionalidades, debe usar Azure RMS con OME. No puede usar las nuevas funcionalidades con un Active Directory local RMS.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Activar Azure Rights Management para la versión anterior de OME en Office 365

Debe activar Azure Rights Management para que los usuarios de su organización puedan aplicar protección de la información a los mensajes que envían y abrir mensajes y archivos protegidos por el servicio Azure Rights Management. Para obtener instrucciones, consulte [Activación de Azure Rights Management](/azure/information-protection/activate-service). Una vez que haya completado la activación, vuelva aquí y continúe con las tareas de este artículo.

## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configuración de la versión anterior de OME para usar Azure RMS mediante la importación de dominios de publicación de confianza (TPD)

Un TPD es un archivo XML que contiene información sobre la configuración de administración de derechos de la organización. Por ejemplo, el TPD contiene información sobre el certificado de licenciante de servidor (SLC) que se usa para firmar y cifrar certificados y licencias, las direcciones URL usadas para licencias y publicación, etc. El TPD se importa en la organización mediante PowerShell.

> [!IMPORTANT]
> Anteriormente, podía optar por importar TPD desde el servicio Active Directory Rights Management (AD RMS) a su organización. Sin embargo, si lo hace, no podrá usar Cifrado de mensajes de Microsoft Purview y no se recomienda. Si su organización está configurada actualmente de esta manera, Microsoft recomienda crear un plan para migrar desde el Active Directory local RMS a Azure Information Protection basado en la nube. Para obtener más información, consulte [Migración de AD RMS a Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). No podrá usar Cifrado de mensajes de Microsoft Purview hasta que haya completado la migración a Azure Information Protection.

**Para importar TPD desde Azure RMS**:

1. [Conéctese al PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Elija la dirección URL de uso compartido de claves que corresponde a la ubicación geográfica de su organización:

   |Ubicación|Dirección URL de ubicación de uso compartido de claves|
   |---|---|
   |Norteamérica|<https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc>|
   |Unión Europea|<https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc>|
   |Asia|<https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc>|
   |Sudamérica|<https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc>|
   |Office 365 Administración Pública (nube de la comunidad de administración pública)  <br/> Esta ubicación de uso compartido de claves de RMS está reservada para los clientes que han comprado Office 365 para SKU gubernamentales.|<https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc>|

3. Configure la ubicación de uso compartido de claves mediante la ejecución del cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) como se indica a continuación:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```

   Por ejemplo, para configurar la ubicación de uso compartido de claves si su organización se encuentra en Norteamérica:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Ejecute el cmdlet [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) con el modificador -RMSOnline para importar el TPD desde Azure Rights Management:

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Donde  *TPDName*  es el nombre que desea usar para el TPD. Por ejemplo, "Contoso North American TPD".

5. Para comprobar que ha configurado correctamente la organización para usar el servicio Azure Rights Management, ejecute el cmdlet [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) con el modificador -RMSOnline de la siguiente manera:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Entre otras cosas, este cmdlet comprueba la conectividad con el servicio Azure Rights Management, descarga el TPD y comprueba su validez.

6. Ejecute el cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) como se indica a continuación para deshabilitar que las plantillas de Azure Rights Management estén disponibles en Outlook en la Web y Outlook:

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Ejecute el cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) como se indica a continuación para habilitar Azure Rights Management para la organización de correo electrónico basada en la nube y configurarlo para que use Azure Rights Management para el cifrado de mensajes de Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Para comprobar que ha importado correctamente el TPD y ha habilitado Azure Rights Management, use el cmdlet Test-IRMConfiguration para probar Azure Rights Management funcionalidad. Para obtener más información, vea "Ejemplo 1" en [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Tengo la versión anterior de OME configurada con Active Directory Rights Management no con Azure Information Protection, ¿qué hago?
<a name="importTPDs"> </a>

Puede seguir usando las reglas de flujo de correo de cifrado de mensajes Office 365 existentes con Active Directory Rights Management, pero no puede configurar ni usar Cifrado de mensajes de Microsoft Purview. En su lugar, debe migrar a Azure Information Protection. Para obtener información sobre la migración y lo que esto significa para su organización, consulte [Migración de AD RMS a Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).

## <a name="next-steps"></a>Pasos siguientes
<a name="importTPDs"> </a>

Una vez que haya completado Azure Rights Management configuración, si desea habilitar Cifrado de mensajes de Microsoft Purview, consulte [Configuración de Cifrado de mensajes de Microsoft Purview](./set-up-new-message-encryption-capabilities.md).

Después de configurar la organización para usar Cifrado de mensajes de Microsoft Purview, está listo para [definir reglas de flujo de correo](define-mail-flow-rules-to-encrypt-email.md).

## <a name="related-topics"></a>Temas relacionados
<a name="importTPDs"> </a>

[Cifrado en Office 365](encryption.md)

[Información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md)

[¿Qué es Azure Rights Management?](/information-protection/understand-explore/what-is-azure-rms)
