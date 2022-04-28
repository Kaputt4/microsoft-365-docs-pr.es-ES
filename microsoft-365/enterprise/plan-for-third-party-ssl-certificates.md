---
title: Planificación de los certificados SSL de terceros para Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: b48cdf63-07e0-4cda-8c12-4871590f59ce
description: 'Resumen: describe los certificados SSL necesarios para Exchange local e híbrido, sso mediante AD FS, servicios de Exchange Online y servicios web de Exchange.'
ms.openlocfilehash: 0cd7cce2cd5f0aba8baecab7048d86d629d30427
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65100311"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Planificación de los certificados SSL de terceros para Microsoft 365

*Este artículo se aplica tanto a Microsoft 365 Enterprise como a Office 365 Enterprise.*

Para cifrar las comunicaciones entre los clientes y el entorno de Microsoft 365, se deben instalar certificados SSL (Capa de sockets seguros) de terceros en los servidores de infraestructura.

Este artículo forma parte del [planeamiento de la red y la optimización del rendimiento para Microsoft 365](./network-planning-and-performance.md).
   
Los certificados son necesarios para los siguientes componentes de Microsoft 365:
  
- Implementación local de Exchange
    
- Inicio de sesión único (SSO) (para los servidores de federación de Servicios de federación de Active Directory (AD FS) (AD FS) y servidores proxy de servidor de federación de AD FS)
    
- Exchange Online servicios, como detección automática, Outlook en cualquier lugar y Exchange servicios web
    
- Exchange servidor híbrido
    
## <a name="certificates-for-exchange-on-premises"></a>Certificados para Exchange local

Para obtener información general sobre cómo usar certificados digitales para hacer que la comunicación entre la organización de Exchange local y Exchange Online segura, consulte el artículo de TechNet [Descripción de los requisitos de certificado](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141)).
  
## <a name="certificates-for-single-sign-on"></a>Certificados para el inicio de sesión único

Para proporcionar a los usuarios una experiencia de inicio de sesión único simplificada que incluya una seguridad sólida, los certificados que se muestran en la tabla siguiente son necesarios en los servidores de federación o en los servidores proxy del servidor de federación. La tabla siguiente se centra en Servicios de federación de Active Directory (AD FS) (AD FS), también tenemos más información sobre [el uso de proveedores de identidades de terceros](/azure/active-directory/hybrid/how-to-connect-fed-compatibility).
  
| Tipo de certificado | Descripción | Lo que necesita saber antes de implementar |
|:-----|:-----|:-----|
|**Certificado SSL (también denominado certificado de autenticación de servidor)** <br/> |Se trata de un certificado SSL estándar que se usa para proteger las comunicaciones entre servidores de federación, clientes y equipos proxy de servidor de federación.  <br/> |AD FS requiere un certificado SSL. De forma predeterminada, AD FS usa el certificado SSL configurado para el sitio web predeterminado en Internet Information Services (IIS).  <br/> El nombre del firmante de este certificado SSL se usa para determinar el nombre del servicio de federación (FS) para cada instancia de AD FS que implemente. Considere la posibilidad de elegir un nombre de firmante para los certificados emitidos por una nueva entidad de certificación (CA) que mejor represente el nombre de su empresa u organización para Microsoft 365. Este nombre debe ser enrutable a Internet.  <br/>**Precaución:** AD FS requiere que este certificado SSL no tenga ningún nombre de firmante sin punto (nombre corto).          <br/> **Recomendación:** Dado que los clientes de AD FS deben confiar en este certificado, se recomienda usar un certificado SSL emitido por una entidad de certificación pública (de terceros) o por una entidad de certificación subordinada a una raíz de confianza pública; por ejemplo, VeriSign o Thawte.  <br/> |
|**Certificado de firma de tokens** <br/> |Se trata de un certificado X.509 estándar que se usa para firmar de forma segura todos los tokens que emite el servidor de federación y que Microsoft 365 acepta y valida.  <br/> |El certificado de firma de tokens debe contener una clave privada que se encadena a una raíz de confianza en el FS. De forma predeterminada, AD FS crea un certificado autofirmado. Sin embargo, en función de las necesidades de su organización, puede cambiar este certificado a un certificado emitido por la ENTIDAD de certificación mediante el complemento de administración de AD FS.  <br/>**Precaución:** El certificado de firma de tokens es fundamental para la estabilidad del FS. Si se cambia el certificado, Microsoft 365 debe recibir una notificación del cambio. Si no se proporciona la notificación, los usuarios no pueden iniciar sesión en sus ofertas de servicio de Microsoft 365.<br/>**Recomendación:** Se recomienda usar el certificado de firma de tokens autofirmado generado por AD FS. Al hacerlo, administra este certificado automáticamente de forma predeterminada. Por ejemplo, cuando este certificado esté a punto de expirar, AD FS generará un nuevo certificado autofirmado.  <br/> |
   
Los servidores proxy de servidor de federación requieren el certificado que se describe en la tabla siguiente.
  
| Tipo de certificado | Descripción | Lo que necesita saber antes de implementar |
|:-----|:-----|:-----|
|certificado SSL  <br/> |Se trata de un certificado SSL estándar que se usa para proteger las comunicaciones entre un servidor de federación, un proxy de servidor de federación y equipos cliente de Internet.  <br/> |Este certificado SSL debe enlazarse al sitio web predeterminado de IIS para poder ejecutar correctamente el Asistente para la configuración del proxy del servidor de federación de AD FS.  <br/> Este certificado debe tener el mismo nombre de firmante que el certificado SSL configurado en el servidor de federación de la red corporativa.  <br/> **Recomendación:** Se recomienda usar el mismo certificado de autenticación de servidor configurado en el servidor de federación al que se conecta este proxy de servidor de federación.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certificados para detección automática, Outlook en cualquier lugar y sincronización de Active Directory

Los Exchange externos de 2013, Exchange 2010, Exchange 2007 y Exchange 2003 Client Access Servers (CASs) requieren un certificado SSL de terceros para conexiones seguras para los servicios de sincronización de Autodiscover, Outlook Anywhere y Active Directory. Es posible que ya tenga instalado este certificado en el entorno local.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certificado para un servidor híbrido de Exchange

Los servidores o servidores híbridos Exchange externos requieren un certificado SSL de terceros para una conectividad segura con el servicio Exchange Online. Debe obtener este certificado del proveedor SSL de terceros.
  
## <a name="microsoft-365-certificate-chains"></a>cadenas de certificados de Microsoft 365

En este artículo se describen los certificados que puede que necesite instalar en la infraestructura. Para obtener más información sobre los certificados instalados en nuestros servidores de Microsoft 365, consulte [Microsoft 365 Cadenas de certificados](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb).
  
## <a name="see-also"></a>Vea también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)