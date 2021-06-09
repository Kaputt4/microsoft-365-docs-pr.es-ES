---
title: Planificación de los certificados SSL de terceros para Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.date: 05/15/2019
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: 'Resumen: describe los certificados SSL necesarios para Exchange local e híbrido, SSO con AD FS, servicios Exchange Online y servicios Exchange web.'
ms.openlocfilehash: f2505a40e87ab36c96c0ed24514420b56d1479d5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927493"
---
# <a name="plan-for-third-party-ssl-certificates-for-microsoft-365"></a>Planificación de los certificados SSL de terceros para Microsoft 365

*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*

Para cifrar las comunicaciones entre los clientes y el entorno Microsoft 365, los certificados de capa de socket seguro (SSL) de terceros deben instalarse en los servidores de infraestructura.

Este artículo forma parte de [la planeación de red y el ajuste del rendimiento para Microsoft 365](./network-planning-and-performance.md).
   
Los certificados son necesarios para los siguientes Microsoft 365 componentes:
  
- Implementación local de Exchange
    
- Inicio de sesión único (SSO) (tanto para los servidores de federación de Servicios de federación de Active Directory (AD FS) como para los servidores proxy de servidor de federación de AD FS)
    
- Exchange Online, como Detección automática, Outlook en cualquier lugar y servicios Exchange web
    
- Exchange híbrido
    
## <a name="certificates-for-exchange-on-premises"></a>Certificados para Exchange locales

Para obtener información general sobre cómo usar certificados digitales para hacer que la comunicación entre la organización Exchange local y Exchange Online segura, vea el artículo de TechNet [Understanding Certificate Requirements](/previous-versions/exchange-server/exchange-141/gg476123(v=exchg.141)).
  
## <a name="certificates-for-single-sign-on"></a>Certificados para el inicio de sesión único

Para proporcionar a los usuarios una experiencia de inicio de sesión único simplificada que incluya una seguridad sólida, los certificados que se muestran en la tabla siguiente son necesarios en los servidores de federación o en los servidores proxy de servidor de federación. La tabla siguiente se centra en Servicios de federación de Active Directory (AD FS), también tenemos más información sobre el uso de proveedores [de identidades de terceros.](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)
  
| Tipo de certificado | Descripción | Lo que necesita saber antes de implementar |
|:-----|:-----|:-----|
|**Certificado SSL (también denominado certificado de autenticación de servidor)** <br/> |Se trata de un certificado SSL estándar que se usa para proteger las comunicaciones entre servidores de federación, clientes y equipos proxy de servidor de federación.  <br/> |AD FS requiere un certificado SSL. De forma predeterminada, AD FS usa el certificado SSL configurado para el sitio web predeterminado en Internet Information Services (IIS).  <br/> El nombre de sujeto de este certificado SSL se usa para determinar el nombre del servicio de federación (FS) para cada instancia de AD FS que implemente. Considere la posibilidad de elegir un nombre de sujeto para los certificados emitidos por cualquier nueva entidad de certificación (CA) que mejor represente el nombre de su empresa u organización para Microsoft 365. Este nombre debe ser enrutable a Internet.  <br/>**Precaución:** AD FS requiere que este certificado SSL no tenga ningún nombre de sujeto sin puntos (nombre corto).          <br/> **Recomendación:** Dado que los clientes de AD FS deben confiar en este certificado, se recomienda usar un certificado SSL emitido por una CA pública (de terceros) o por una CA subordinada a una raíz de confianza pública; por ejemplo, VeriSign o Thawte.  <br/> |
|**Certificado de firma de tokens** <br/> |Se trata de un certificado X.509 estándar que se usa para firmar de forma segura todos los tokens que emite el servidor de federación y que Microsoft 365 acepta y valida.  <br/> |El certificado de firma de tokens debe contener una clave privada que se encadena a una raíz de confianza en el FS. De forma predeterminada, AD FS crea un certificado autofirmado. Sin embargo, en función de las necesidades de su organización, puede cambiar este certificado a un certificado emitido por la CA mediante el complemento de administración de AD FS.  <br/>**Precaución:** El certificado de firma de tokens es fundamental para la estabilidad del FS. Si se cambia el certificado, Microsoft 365 debe recibir una notificación del cambio. Si no se proporciona notificación, los usuarios no pueden iniciar sesión en sus Microsoft 365 de servicio.<br/>**Recomendación:** Se recomienda usar el certificado de firma de tokens autofirmado generado por AD FS. Al hacerlo, administra este certificado de forma predeterminada. Por ejemplo, cuando este certificado está a punto de expirar, AD FS generará un nuevo certificado autofirmado.  <br/> |
   
Los servidores proxy de servidor de federación requieren el certificado que se describe en la tabla siguiente.
  
| Tipo de certificado | Descripción | Lo que necesita saber antes de implementar |
|:-----|:-----|:-----|
|certificado SSL  <br/> |Se trata de un certificado SSL estándar que se usa para proteger las comunicaciones entre un servidor de federación, un proxy de servidor de federación y equipos cliente de Internet.  <br/> |Este certificado SSL debe enlazarse al sitio web predeterminado de IIS para poder ejecutar correctamente el Asistente para configuración de proxy de servidor de federación de AD FS.  <br/> Este certificado debe tener el mismo nombre de sujeto que el certificado SSL que se configuró en el servidor de federación en la red corporativa.  <br/> **Recomendación:** Se recomienda usar el mismo certificado de autenticación de servidor configurado en el servidor de federación al que se conecta este proxy de servidor de federación.  <br/> |
   
## <a name="certificates-for-autodiscover-outlook-anywhere-and-active-directory-synchronization"></a>Certificados para detección automática, Outlook en cualquier lugar y sincronización de Active Directory

Los servidores de acceso de cliente (CAS) de Exchange 2013, Exchange 2010, Exchange 2007 y Exchange 2003 requieren un certificado SSL de terceros para conexiones seguras para los servicios de sincronización de Active Directory, Outlook Anywhere y Autodiscover. Es posible que ya tenga instalado este certificado en el entorno local.
  
## <a name="certificate-for-an-exchange-hybrid-server"></a>Certificado para un servidor Exchange híbrido

Los servidores o servidores híbridos Exchange externos requieren un certificado SSL de terceros para una conectividad segura con el Exchange Online cliente. Debe obtener este certificado de su proveedor SSL de terceros.
  
## <a name="microsoft-365-certificate-chains"></a>Microsoft 365 Cadenas de certificados

En este artículo se describen los certificados que puede que necesite instalar en la infraestructura. Para obtener más información sobre los certificados instalados en nuestros servidores Microsoft 365, vea [Microsoft 365 Cadenas de certificados](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb).
  
## <a name="see-also"></a>Consulte también

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)