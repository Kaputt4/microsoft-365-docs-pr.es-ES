---
title: Aislamiento y control de acceso de Microsoft 365 en Azure Active Directory
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: En este artículo, obtenga información sobre cómo funcionan el aislamiento y el control de acceso para mantener los datos de varios inquilinos aislados entre sí en Azure Active Directory.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 198e1f37a7378d14d5a4ad28d5bce9d480b2c49e
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332417"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Aislamiento y control de acceso de Microsoft 365 en Azure Active Directory

Azure Active Directory (Azure AD) se diseñó para hospedar varios inquilinos de forma altamente segura a través del aislamiento de datos lógicos. El acceso a Azure AD está privado por una capa de autorización. Azure AD aísla a los clientes que usan contenedores de inquilinos como límites de seguridad para proteger el contenido de un cliente de modo que los coinquilinos no puedan acceder al contenido ni comprometerlo. La capa de autorización de Azure AD realiza tres comprobaciones:

- ¿La entidad de seguridad está habilitada para el acceso al inquilino de Azure AD?
- ¿La entidad de seguridad está habilitada para obtener acceso a los datos de este espacio empresarial?
- ¿El rol de la entidad de seguridad en este espacio empresarial está autorizado para el tipo de acceso a datos solicitado?

Ninguna aplicación, usuario, servidor o servicio puede acceder a Azure AD sin la autenticación y el token o certificado adecuados. Las solicitudes se rechazan si no van acompañadas de las credenciales adecuadas.

De hecho, Azure AD hospeda cada inquilino en su propio contenedor protegido, con directivas y permisos en y dentro del contenedor que solo es propiedad y está administrado por el inquilino.
 
![Contenedor de Azure](../media/office-365-isolation-azure-container.png)

El concepto de contenedores de inquilinos está profundamente arraigado en el servicio de directorio en todas las capas, desde portales hasta el almacenamiento persistente. Incluso cuando se almacenan varios metadatos de inquilino de Azure AD en el mismo disco físico, no hay ninguna relación entre los contenedores que no sea la definida por el servicio de directorio, que a su vez está dictada por el administrador de inquilinos. No puede haber conexiones directas al almacenamiento de Azure AD desde cualquier aplicación o servicio solicitante sin pasar primero por la capa de autorización.

En el ejemplo siguiente, Contoso y Fabrikam tienen contenedores independientes y dedicados, y aunque estos contenedores pueden compartir parte de la misma infraestructura subyacente, como servidores y almacenamiento, permanecen separados y aislados entre sí, y aislados por capas de autorización y control de acceso.
 
![Contenedores dedicados de Azure](../media/office-365-isolation-azure-dedicated-containers.png)

Además, no hay componentes de aplicación que se puedan ejecutar desde Azure AD y no es posible que un inquilino incumbe la integridad de otro inquilino, acceda a las claves de cifrado de otro inquilino o lea datos sin procesar del servidor.

De forma predeterminada, Azure AD no permite todas las operaciones emitidas por identidades en otros inquilinos. Cada inquilino se aísla lógicamente en Azure AD a través de controles de acceso basados en notificaciones. Las lecturas y escrituras de datos de directorio se aplican a contenedores de inquilinos y están delimitadas por una capa de abstracción interna y una capa de control de acceso basado en roles (RBAC), que, en conjunto, aplican el inquilino como límite de seguridad. Estas capas procesan todas las solicitudes de acceso a datos de directorio y cada solicitud de acceso de Microsoft 365 está bajo la protección de la lógica anterior.

Azure AD tiene particiones de Norteamérica, Estados Unidos, Unión Europea, Alemania y todo el mundo. Un inquilino existe en una sola partición y las particiones pueden contener varios inquilinos. La información de partición se abstrae de los usuarios. Una partición determinada (incluidos todos los inquilinos dentro de ella) se replica en varios centros de datos. La partición de un inquilino se elige en función de las propiedades del inquilino (por ejemplo, el código de país). Los secretos y otra información confidencial de cada partición se cifran con una clave dedicada. Las claves se generan automáticamente cuando se crea una partición nueva.

Las funcionalidades del sistema de Azure AD son una instancia única para cada sesión de usuario. Además, Azure AD usa tecnologías de cifrado para proporcionar aislamiento de los recursos compartidos del sistema en el nivel de red para evitar la transferencia no autorizada y no intencionado de información.
