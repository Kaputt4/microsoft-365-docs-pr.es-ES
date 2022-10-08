---
title: Aislamiento y Access Control de Microsoft 365 en Azure Active Directory
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- scotvorg
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: En este artículo, aprenderá cómo funcionan el aislamiento y la Access Control para mantener los datos de varios inquilinos aislados entre sí dentro de Azure Active Directory.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0be353ffce6404f0c8b3a6f64eb8ba8bddb6074b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68169549"
---
# <a name="microsoft-365-isolation-and-access-control-in-azure-active-directory"></a>Aislamiento y Access Control de Microsoft 365 en Azure Active Directory

Azure Active Directory (Azure AD) se diseñó para hospedar varios inquilinos de forma muy segura a través del aislamiento de datos lógicos. El acceso a Azure AD está privado por una capa de autorización. Azure AD aísla a los clientes que usan contenedores de inquilinos como límites de seguridad para proteger el contenido de un cliente de modo que los coinquilinos no puedan acceder al contenido ni ponerlo en peligro. La capa de autorización de Azure AD realiza tres comprobaciones:

- ¿Está habilitada la entidad de seguridad para el acceso al inquilino de Azure AD?
- ¿Está habilitada la entidad de seguridad para el acceso a los datos de este inquilino?
- ¿Está autorizado el rol de la entidad de seguridad en este inquilino para el tipo de acceso a datos solicitado?

Ninguna aplicación, usuario, servidor o servicio puede acceder a Azure AD sin la autenticación y el token o certificado adecuados. Las solicitudes se rechazan si no van acompañadas de las credenciales adecuadas.

De forma eficaz, Azure AD hospeda cada inquilino en su propio contenedor protegido, con directivas y permisos para y dentro del contenedor que el inquilino solo posee y administra.
 
![Contenedor de Azure.](../media/office-365-isolation-azure-container.png)

El concepto de contenedores de inquilinos está profundamente arraigado en el servicio de directorio en todas las capas, desde los portales hasta el almacenamiento persistente. Incluso cuando varios metadatos de inquilino de Azure AD se almacenan en el mismo disco físico, no hay ninguna relación entre los contenedores que no sea lo que define el servicio de directorio, que a su vez lo dicta el administrador de inquilinos. No puede haber conexiones directas al almacenamiento de Azure AD desde ninguna aplicación o servicio solicitante sin pasar primero por la capa de autorización.

En el ejemplo siguiente, Contoso y Fabrikam tienen contenedores independientes y dedicados, y aunque esos contenedores pueden compartir parte de la misma infraestructura subyacente, como servidores y almacenamiento, permanecen separados y aislados entre sí, y están privados por capas de autorización y control de acceso.
 
![Contenedores dedicados de Azure.](../media/office-365-isolation-azure-dedicated-containers.png)

Además, no hay componentes de aplicación que se puedan ejecutar desde Azure AD y no es posible que un inquilino infrinja por la fuerza la integridad de otro inquilino, acceda a las claves de cifrado de otro inquilino o lea datos sin procesar del servidor.

De forma predeterminada, Azure AD no permite todas las operaciones emitidas por identidades en otros inquilinos. Cada inquilino está aislado lógicamente dentro de Azure AD mediante controles de acceso basados en notificaciones. Las lecturas y escrituras de datos de directorio tienen como ámbito contenedores de inquilinos y están protegidas por una capa de abstracción interna y una capa de control de acceso basado en rol (RBAC), que juntos aplican el inquilino como límite de seguridad. Estas capas procesan cada solicitud de acceso a datos de directorio y cada solicitud de acceso de Microsoft 365 se supervisa mediante la lógica anterior.

Azure AD tiene particiones Norteamérica, gobierno de EE. UU., Unión Europea, Alemania y World Wide. Un inquilino existe en una sola partición y las particiones pueden contener varios inquilinos. La información de partición se abstrae de los usuarios. Una partición determinada (incluidos todos los inquilinos que contiene) se replica en varios centros de datos. La partición de un inquilino se elige en función de las propiedades del inquilino (por ejemplo, el código de país). Los secretos y otra información confidencial de cada partición se cifran con una clave dedicada. Las claves se generan automáticamente cuando se crea una nueva partición.

Las funcionalidades del sistema de Azure AD son una instancia única de cada sesión de usuario. Además, Azure AD usa tecnologías de cifrado para proporcionar aislamiento de los recursos del sistema compartido en el nivel de red a fin de evitar la transferencia de información no autorizada y no intencionada.
