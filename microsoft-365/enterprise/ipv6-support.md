---
title: Compatibilidad con IPv6 en servicios de Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/10/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: c08786fb-298e-437c-8222-dab7625fc815
description: 'Resumen: describe la compatibilidad con IPv6 en Microsoft Office 365 componentes y en ofertas gubernamentales de Office 365.'
ms.openlocfilehash: a509b19711092bddf153a677c41860e7a4e5277a
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028912"
---
# <a name="ipv6-support-in-office-365-services"></a>Compatibilidad con IPv6 en servicios de Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Office 365 admite IPv6 e IPv4; sin embargo, no todas las características de Office 365 están totalmente habilitadas con IPv6. Esto significa que debe usar IPv4 e IPv6 para conectarse a Office 365. Si está filtrando el tráfico saliente a Office 365, puede encontrar la lista completa de direcciones IPv6 compatibles con Office 365 en el artículo Direcciones URL e intervalos de direcciones IP de [Office 365.](urls-and-ip-address-ranges.md) Después de configurar la red y permitir las direcciones IPv6 adecuadas, puede descargar el plan de prueba de [Office 365 IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) desde el Centro de descarga de Microsoft.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Compatibilidad con IPv6 en el servicio de suscripción de Office 365

### <a name="exchange-online-and-ipv6"></a>Exchange Online e IPv6

Si el programa que usa para conectarse a Exchange Online admite IPv6, usará IPv6 de forma predeterminada en redes cableadas e inalámbricas. Si desea controlar las comunicaciones con Exchange Online, use los intervalos de direcciones IP en las direcciones URL de [Office 365](urls-and-ip-address-ranges.md)y los intervalos de direcciones IP.
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online e IPv6

 **Office 365 Government G1/G3/G4/K1** Si el programa que usa para conectarse a SharePoint Online admite IPv6, intentará usar IPv6 de forma predeterminada.
  
 **Nube pública multiinquilino** Microsoft habilita SharePoint Online IPv6 a petición. Debe proporcionar las direcciones IP con nota CIDR para la infraestructura DNS de su organización. Tenga en cuenta que otras organizaciones no pueden compartir esta infraestructura DNS para que IPv6 esté habilitada para su inquilino. Después de habilitar IPv6, si el programa que usa para conectarse a SharePoint Online admite IPv6, usa IPv6 de forma predeterminada.
  
Si el programa que usa para conectarse a SharePoint Online admite IPv6, usará IPv6 de forma predeterminada en redes cableadas e inalámbricas. Si desea controlar las comunicaciones a SharePoint Online, use los intervalos de direcciones IP en las direcciones URL de [Office 365](urls-and-ip-address-ranges.md)y los intervalos de direcciones IP.
  
 
  
### <a name="skype-for-business-and-ipv6"></a>Skype Empresarial e IPv6

Tenga en cuenta que IPv6 no es compatible con Skype Empresarial y ya no se puede habilitar.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPV6

El enrutamiento directo de Microsoft Teams solo admite IPv4. El servicio de Microsoft Teams y el cliente admiten IPv4 e IPv6. Si desea controlar las comunicaciones con Microsoft Teams, use los intervalos de direcciones IP en las direcciones URL de [Office 365](urls-and-ip-address-ranges.md)y los intervalos de direcciones IP.
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection e IPv6

Exchange Online Protection (EOP) admite IPv6 si la transmisión se produce a través del protocolo de seguridad de la capa de transporte. Para el intervalo de EOP, use direcciones URL e intervalos de [direcciones IP de Office 365.](urls-and-ip-address-ranges.md)
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Compatibilidad con IPv6 para ofertas gubernamentales de Office 365

La compatibilidad con IPv6 de Office 365 para ofertas gubernamentales se ajusta al memorándum de la Oficina de Administración y Presupuesto (OMB) para jefes de información de departamentos ejecutivos y agencias, así como al memorándum de adopción por parte del gobierno federal del protocolo de Internet versión 6 (IPv6). [Microsoft Office 365 for Government](https://go.microsoft.com/fwlink/p/?LinkId=325414) es un servicio multiinquilino que almacena datos del gobierno de Estados Unidos en una nube de comunidad segregada. Al igual que otras ofertas de Office 365, proporciona servicios de productividad y colaboración, como Exchange Online, Skype Empresarial, SharePoint Online y Aplicaciones de Microsoft 365 para empresas. 

Las Microsoft Office 365 ofertas gubernamentales solo se aplican para 2013 y versiones posteriores. Para obtener más información acerca de las ofertas gubernamentales de Office 365, vea [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414). International Traffic in Arms Regulations (ITAR) es un conjunto de reglamentos gubernamentales estadounidenses que controlan la exportación e importación de artículos y servicios relacionados con la defensa en la Lista de munición de los Estados Unidos [(USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415) 

Microsoft Office 365 para empresas proporciona servicios de hospedaje dedicados para soluciones de productividad de Microsoft que admiten los requisitos de seguridad, privacidad y cumplimiento normativo para las agencias federales de Estados Unidos que requieren la certificación de administración federal de seguridad de la información (FISMA) y entidades comerciales sujetas a ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Aspectos a tener en cuenta al usar IPv6 y Office 365

Se recomienda no deshabilitar IPv6. Para obtener más información, vea este [artículo de instrucciones](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Para determinar qué versiones IP se usan en la red, tenga en cuenta lo siguiente:
  
- Si la presentación del comando **IPConfig** en el símbolo del sistema contiene filas denominadas "Dirección IPv6" o "Dirección IPv6 temporal", tiene IPv6 en el entorno.

- Si todas las direcciones IPv6 comienzan por "fe80" y corresponden a filas denominadas "Dirección IPv6 local de vínculo", no tienes IPv6 en el entorno.

Estas consideraciones pueden aplicarse a la red:
  
- El servicio de suscripción pública no admite la compra con tarjeta de crédito a través de IPv6. Esto no se aplica a la nube de la comunidad gubernamental (GCC) porque los gobiernos Contrato Enterprise licencias (EA).

- IPv6 no admite algunos escenarios de Rights Management Services (RMS).

- IPv6 no admite BlackBerry® Enterprise Server (BES) porque BlackBerry no admite IPv6.

- Si usa Servicios de federación de Active Directory (AD FS) con Office 365, no se admite la publicidad del extremo de red de AD FS en Office 365 con IPv6. No debe incluir registros AAAA en la entrada DNS de AD FS al usar Exchange Online. 

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>Vea también

[Guía básica de aprendizaje de IPv6](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Guía de supervivencia de IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)
