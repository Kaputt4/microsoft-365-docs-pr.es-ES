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
description: 'Resumen: describe la compatibilidad con IPv6 en Microsoft Office 365 componentes y en Office 365 ofertas gubernamentales.'
ms.openlocfilehash: 7f06ed6f8df2c6552ee0a331ad958bca289d0a09
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909687"
---
# <a name="ipv6-support-in-office-365-services"></a>Compatibilidad con IPv6 en servicios de Office 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Office 365 admite IPv6 e IPv4; sin embargo, no todas Office 365 características están totalmente habilitadas con IPv6. Esto significa que debe usar IPv4 e IPv6 para conectarse a Office 365. Si está filtrando el tráfico saliente a Office 365, puede encontrar la lista completa de direcciones IPv6 compatibles con Office 365 en el artículo Office 365 URL e [intervalos](urls-and-ip-address-ranges.md)de direcciones IP . Después de configurar la red y permitir las direcciones IPv6 adecuadas, puede descargar el plan de prueba Office 365 [IPv6](https://go.microsoft.com/fwlink/?LinkId=293447) desde el Centro de descarga de Microsoft.
  
## <a name="ipv6-support-in-office-365-subscription-service"></a>Compatibilidad con IPv6 en Office 365 de suscripción

### <a name="exchange-online-and-ipv6"></a>Exchange Online e IPv6

Si el programa que usas para conectarte a Exchange Online admite IPv6, usará IPv6 de forma predeterminada en redes cableadas e inalámbricas. Si desea controlar las comunicaciones a Exchange Online, use los intervalos de direcciones IP en Office 365 direcciones URL e [intervalos de direcciones IP](urls-and-ip-address-ranges.md).
  
### <a name="sharepoint-online-and-ipv6"></a>SharePoint Online e IPv6

 **Office 365 Administración Pública G1/G3/G4/K1** Si el programa que usa para conectarse a SharePoint Online admite IPv6, intentará usar IPv6 de forma predeterminada.
  
 **Nube pública multiinquilino** Microsoft habilita SharePoint Online IPv6 a su solicitud. Debe proporcionar las direcciones IP con nota CIDR para la infraestructura DNS de su organización. Tenga en cuenta que otras organizaciones no pueden compartir esta infraestructura DNS para que IPv6 esté habilitada para su inquilino. Después de habilitar IPv6, si el programa que usas para conectarte a SharePoint Online admite IPv6, usa IPv6 de forma predeterminada.
  
Si el programa que usas para conectarte a SharePoint Online admite IPv6, usará IPv6 de forma predeterminada en redes cableadas e inalámbricas. Si desea controlar las comunicaciones a SharePoint Online, use los intervalos de direcciones IP en Office 365 direcciones URL e [intervalos de direcciones IP](urls-and-ip-address-ranges.md).
  
 **Office 365 Administración Pública G1/G3/G4/K1** Si el programa que usa para conectarse a SharePoint Online admite IPv6, intentará usar IPv6 de forma predeterminada.
  
### <a name="skype-for-business-and-ipv6"></a>Skype Empresarial e IPv6

Tenga en cuenta que IPv6 no es compatible con Skype Empresarial y ya no se puede habilitar.

### <a name="microsoft-teams-and-ipv6"></a>Microsoft Teams e IPV6

Microsoft Teams El enrutamiento directo solo admite IPv4. El Microsoft Teams y el cliente admiten IPv4 e IPv6. Si desea controlar las comunicaciones a Microsoft Teams, use los intervalos de direcciones IP en Office 365 direcciones URL e [intervalos de direcciones IP](urls-and-ip-address-ranges.md).
  
### <a name="exchange-online-protection-and-ipv6"></a>Exchange Online Protection e IPv6

Exchange Online Protection (EOP) admite IPv6 si la transmisión se produce a través del protocolo de seguridad de la capa de transporte. Para el intervalo de EOP, use [Office 365 direcciones URL e intervalos de direcciones IP](urls-and-ip-address-ranges.md).
  
### <a name="ipv6-support-for-office-365-government-offerings"></a>Compatibilidad con IPv6 para Office 365 ofertas gubernamentales

Office 365 La compatibilidad con IPv6 para ofertas gubernamentales se ajusta al memorándum Office de administración y presupuesto (OMB) para jefes de información de departamentos ejecutivos y agencias, así como al memorándum de adopción por el gobierno federal del protocolo de Internet versión 6 (IPv6). [Microsoft Office 365 para Gobierno es](https://go.microsoft.com/fwlink/p/?LinkId=325414) un servicio multiinquilino que almacena datos del gobierno de Estados Unidos en una nube de comunidad segregada. Al igual que otras Office 365, proporciona servicios de productividad y colaboración, incluidos Exchange Online, Skype Empresarial, SharePoint Online y Aplicaciones Microsoft 365 para empresas. 

Las Microsoft Office 365 las ofertas gubernamentales solo se aplican para 2013 y versiones posteriores. Para obtener más información acerca de las Office 365 de administración pública, vea [Announcing Office 365 for Government: A US Government Community Cloud](https://go.microsoft.com/fwlink/p/?LinkId=325414). International Traffic in Arms Regulations (ITAR) es un conjunto de reglamentos gubernamentales estadounidenses que controlan la exportación e importación de artículos y servicios relacionados con la defensa en la Lista de munición de los Estados Unidos [(USML).](https://go.microsoft.com/fwlink/p/?LinkId=325415) 

Microsoft Office 365 para empresas proporciona servicios de hospedaje dedicados para soluciones de productividad de Microsoft que admiten los requisitos de seguridad, privacidad y cumplimiento normativo para las agencias federales de Estados Unidos que requieren la certificación de Administración federal de seguridad de la información (FISMA) y entidades comerciales sujetas a ITAR.
  
## <a name="things-to-consider-when-using-ipv6-and-office-365"></a>Aspectos a tener en cuenta al usar IPv6 y Office 365

Se recomienda no deshabilitar IPv6. Para obtener más información, vea este [artículo de instrucciones](https://support.microsoft.com/help/929852/guidance-for-configuring-ipv6-in-windows-for-advanced-users). Para determinar qué versiones IP se usan en la red, tenga en cuenta lo siguiente:
  
- Si la presentación del comando **IPConfig** en el símbolo del sistema contiene filas denominadas "Dirección IPv6" o "Dirección IPv6 temporal", tiene IPv6 en el entorno.

- Si todas las direcciones IPv6 comienzan por "fe80" y corresponden a filas denominadas "Dirección IPv6 local de vínculo", no tienes IPv6 en el entorno.

Estas consideraciones pueden aplicarse a la red:
  
- El servicio de suscripción pública no admite la compra con tarjeta de crédito a través de IPv6. Esto no se aplica al Government Community Cloud (GCC) porque los gobiernos Enterprise Agreement licencias (EA).

- IPv6 no admite algunos escenarios de Rights Management Services (RMS).

- IPv6 no admite BlackBerry® Enterprise Server (BES) porque BlackBerry no admite IPv6.

- Si usas Servicios de federación de Active Directory (AD FS) con Office 365, no se admite la publicidad del extremo de red de AD FS Office 365 usar IPv6. No debe incluir registros AAAA en la entrada DNS de AD FS al usar Exchange Online. 

Este es un vínculo breve que se puede usar para volver: [https://aka.ms/o365ip6]()
  
## <a name="see-also"></a>Vea también

[Guía básica de aprendizaje de IPv6](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/gg250710(v%3dws.10))
  
[Guía de supervivencia de IPv6](https://social.technet.microsoft.com/wiki/contents/articles/1728.ipv6-survival-guide.aspx)