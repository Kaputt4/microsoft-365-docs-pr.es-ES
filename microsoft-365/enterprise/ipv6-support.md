---
title: Compatibilidad con IPv6 en los servicios de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/03/2021
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Resumen: describe la compatibilidad con IPv6 en componentes Microsoft 365 y en Microsoft 365 ofertas gubernamentales.'
ms.openlocfilehash: 6cd53b71c6e15346d4940c539eea4aff0e5a613e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65096488"
---
# <a name="ipv6-support-in-microsoft-365-services"></a>Compatibilidad con IPv6 en los servicios de Microsoft 365

Microsoft 365 admite IPv6 e IPv4; sin embargo, no todas las características Microsoft 365 están totalmente habilitadas con IPv6. Esto significa que debe usar IPv4 e IPv6 para conectarse a Microsoft 365. Si va a filtrar el tráfico saliente a Microsoft 365, puede encontrar la lista completa de direcciones IPv6 compatibles con Microsoft 365 en el artículo [Microsoft 365 direcciones URL e intervalos de direcciones IP](urls-and-ip-address-ranges.md). Después de configurar la red y de permitir las direcciones IPv6 adecuadas, puede descargar el [Microsoft 365 plan de prueba IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) desde el Centro de descarga de Microsoft.

> [!NOTE]
> Permitir que los clientes experimenten Microsoft 365 servicios SaaS desde cualquier ubicación y cualquier dispositivo es una prioridad para Microsoft. Esto incluye permitir que los clientes se conecten y consuman Microsoft 365 desde los sistemas de información y clientes IPv6 habilitados para IPv6. También incluye permitir que los clientes gubernamentales cumplan los compromisos de IPv6 en sus redes mientras siguen usando escenarios de productividad Microsoft 365 sin interrupción.  
> En este artículo se proporciona la lista de Microsoft 365 servicios SaaS que permiten la conectividad IPv6 directa hoy en día. Se espera que el ámbito de los servicios que permiten la conectividad IPv6 directa continúe expandiéndose. Microsoft 365 servicios que no se mencionan explícitamente para la compatibilidad directa con IPv6, para incluir servicios de autenticación de Azure Active Directory (AAD), se deben considerar que requieren que DNS64/NAT64 se conecten solo desde los clientes y entornos de IPv6.  Esto se alinea con la intención que se describe actualmente en la documentación existente de NIST USGv6: Los requisitos de capacidad del mecanismo de transición en la [publicación especial 500-267A de NIST 1](https://nvlpubs.nist.gov/nistpubs/specialpublications/NIST.SP.500-267Ar1.pdf) NAT64/DNS64 son tecnologías aceptables para emplear.
> - Compatibilidad con NAT64 para el mecanismo de transición NAT64 [RFC6146 NAT64 con](https://datatracker.ietf.org/doc/html/rfc6146) estado: traducción de direcciones de red y protocolo de clientes IPv6 a servidores IPv4
> - Compatibilidad de DNS64 con el mecanismo de transición DNS64. [RFC6147](https://datatracker.ietf.org/doc/html/rfc6147) DNS64: Extensiones DNS para la traducción de direcciones de red de clientes IPv6 al servidor IPv4

  
## <a name="ipv6-support-in-microsoft-365-subscription-service"></a>Compatibilidad con IPv6 en Microsoft 365 servicio de suscripción

### <a name="exchange-online-and-ipv6"></a>Exchange Online e IPv6

Si el programa que usa para conectarse a Exchange Online admite IPv6, usará IPv6 de forma predeterminada en redes cableadas e inalámbricas. Si desea controlar las comunicaciones con Exchange Online, use los intervalos de direcciones IP en [Microsoft 365 direcciones URL e intervalos de direcciones IP](urls-and-ip-address-ranges.md).
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online e IPv6

 **Microsoft 365 Government G1/G3/G4/K1** Si el programa que usa para conectarse a SharePoint Online admite IPv6, intentará usar IPv6 de forma predeterminada.
  
 **Nube multiinquilino pública** Microsoft habilita SharePoint IPv6 en línea a petición. Debe proporcionar las direcciones IP con nota CIDR para la infraestructura DNS de su organización. Tenga en cuenta que otras organizaciones no pueden compartir esta infraestructura DNS para que IPv6 esté habilitada para el inquilino. Una vez habilitado IPv6, si el programa que usa para conectarse a SharePoint Online admite IPv6, usa IPv6 de forma predeterminada.
  
Si el programa que usa para conectarse a SharePoint Online admite IPv6, usará IPv6 de forma predeterminada en redes cableadas e inalámbricas. Si desea controlar las comunicaciones con SharePoint Online, use los intervalos de direcciones IP en [Microsoft 365 direcciones URL e intervalos de direcciones IP](urls-and-ip-address-ranges.md).
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype Empresarial e IPv6

Tenga en cuenta que IPv6 no se admite en Skype Empresarial y ya no se puede habilitar.

### <a name="microsoft-teams-sip-gateway-and-ipv6"></a>Microsoft Teams, puerta de enlace SIP e IPV6

Microsoft Teams enrutamiento directo y puerta de enlace SIP solo admiten IPv4. El servicio Microsoft Teams y el cliente admiten IPv4 e IPv6. Si desea controlar las comunicaciones con Microsoft Teams, use los intervalos de direcciones IP en [Microsoft 365 direcciones URL e intervalos de direcciones IP](urls-and-ip-address-ranges.md).
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection e IPv6

Exchange Online Protection (EOP) admite IPv6 si la transmisión se produce a través del Protocolo de seguridad de la capa de transporte. Para el intervalo EOP, use [Microsoft 365 direcciones URL e intervalos de direcciones IP](urls-and-ip-address-ranges.md).
  
### <a name="ipv6-support-for-microsoft-365-government-offerings"></a>Compatibilidad con IPv6 para ofertas gubernamentales de Microsoft 365

Microsoft 365 soporte de IPv6 para las ofertas gubernamentales se ajusta al memorándum de Office de Administración y Presupuesto (OMB) para los jefes de información de departamentos ejecutivos y agencias, así como al memorándum sobre la adopción del protocolo de Internet versión 6 (IPv6) por parte del gobierno federal. [Microsoft Microsoft 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) es un servicio multiinquilino que almacena datos del gobierno de EE. UU. en una nube de la comunidad segregada. Al igual que otras ofertas de Microsoft 365, proporciona servicios de productividad y colaboración, incluidos Exchange Online, Skype Empresarial, SharePoint Online y Aplicaciones Microsoft 365 para empresas. 

Las ofertas gubernamentales de Microsoft Microsoft 365 solo se aplican para 2013 y versiones posteriores. Para obtener más información sobre las ofertas gubernamentales Microsoft 365, consulte [Anuncio de Microsoft 365 para government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414). International Traffic in Arms Regulations (ITAR) es un conjunto de regulaciones gubernamentales estadounidenses que controlan la exportación e importación de artículos y servicios relacionados con la defensa en la [lista de municiones de Estados Unidos (USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415) 

Microsoft Microsoft 365 for Enterprises proporciona servicios de hospedaje dedicados para soluciones de productividad de Microsoft que admiten los requisitos de seguridad, privacidad y cumplimiento normativo para las agencias federales de EE. UU. que requieren la certificación de Administración federal de seguridad de la información (FISMA) y entidades comerciales sujetas a ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-microsoft-365"></a>Aspectos a tener en cuenta al usar IPv6 y Microsoft 365

Se recomienda no deshabilitar IPv6. Para obtener más información, consulte este [artículo de orientación](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Para determinar qué versiones ip se usan en la red, tenga en cuenta lo siguiente:
  
- Si la presentación del comando **IPConfig** en el símbolo del sistema contiene filas denominadas "Dirección IPv6" o "Dirección IPv6 temporal", tiene IPv6 en su entorno.

- Si todas las direcciones IPv6 comienzan por "fe80" y corresponden a filas denominadas "Dirección IPv6 local de vínculo", no tiene IPv6 en su entorno.

Estas consideraciones pueden aplicarse a la red:
  
- El servicio de suscripción pública no admite la compra con tarjeta de crédito a través de IPv6. Esto no se aplica al Government Community Cloud (GCC) porque los gobiernos tienen licencias de Enterprise Agreement (EA).

- IPv6 no admite algunos escenarios de Rights Management Services (RMS).

- IPv6 no admite BlackBerry® Enterprise Server (BES) porque BlackBerry no admite IPv6.

- Si usa Servicios de federación de Active Directory (AD FS) (AD FS) con Microsoft 365, no se admite la publicidad del punto de conexión de red de AD FS para Microsoft 365 mediante IPv6. No debe incluir registros AAAA en la entrada DNS de AD FS al usar Exchange Online. 

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/o365ip6]()

## <a name="see-also"></a>Vea también

[Hoja de ruta de Learning IPv6](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Guía de supervivencia de IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
