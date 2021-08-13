---
title: Cómo Exchange Online protege su información confidencial de correo electrónico
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Además del Centro de confianza de Office 365 que proporciona información de seguridad, privacidad y cumplimiento para Microsoft 365, es posible que desee saber cómo Microsoft ayuda a proteger los secretos que almacena en sus centros de datos. Usamos una tecnología denominada Distributed Key Manager (DKM).
ms.openlocfilehash: fe049f600f9ffef496febae2e1c773d562e5693c2ab66fdc37ee377cb66f01e1
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53795871"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Cómo Exchange Online protege su información confidencial de correo electrónico

Este artículo describe cómo Microsoft protege su información confidencial de correo electrónico en sus centros de datos.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>¿Cómo se protege la información confidencial proporcionada por el usuario?

Además del Centro de confianza de Office 365 que proporciona información de [seguridad,](./get-started-with-service-trust-portal.md)privacidad y cumplimiento para Office 365 , es posible que desee saber cómo Microsoft ayuda a proteger los secretos que proporciona en sus centros de datos. Usamos una tecnología denominada Distributed Key Manager (DKM).
  
[El Administrador de claves](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) distribuidas (DKM) es una funcionalidad del lado cliente que usa un conjunto de claves secretas para cifrar y descifrar información. Solo los miembros de un grupo de seguridad específico de los Servicios de dominio de Active Directory pueden tener acceso a dichas claves para descifrar los datos cifrados por el DKM. En Exchange Online, solo determinadas cuentas de servicio bajo las cuales se ejecutan procesos de Exchange forman parte del grupo de seguridad. Como parte del procedimiento operativo estándar en el centro de datos, ningún humano tiene credenciales que forman parte de este grupo de seguridad y, por lo tanto, nadie tiene acceso a las claves que pueden descifrar la información confidencial.
  
Para depuración, solución de problemas o fines de auditoria, un administrador del centro de datos debe solicitar acceso con privilegios elevados para obtener credenciales temporales que forman parte del grupo de seguridad. Este proceso requiere varios niveles de aprobación legal. Si se concede acceso, toda la actividad se registra y se audita. Además, solo se otorga acceso durante un determinado intervalo de tiempo, que caduca automáticamente una vez concluido.
  
Para brindar protección adicional, la tecnología del DKM incluye sustitución de claves y archivado automáticos. Esto también garantiza el acceso al contenido anterior sin tener que recurrir a la misma clave de forma indefinida.

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>¿De qué forma Exchange Online usa el DKM?

Microsoft usa [el Administrador de claves distribuidas](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) para cifrar los secretos en Exchange Online centros de datos. Por ejemplo:
  
- Credenciales de cuentas de correo electrónico de cuentas conectadas. Las cuentas conectadas son cuentas de terceros, como las de Hotmail, Gmail y Yahoo!.

- Clave de cliente. Si usa el cifrado [de servicio con clave de](customer-key-overview.md)cliente, usará Azure Key [Vault](/azure/key-vault/key-vault-whatis) para proteger sus secretos.

## <a name="related-topics"></a>Temas relacionados

[Cifrado en Office 365](encryption.md)
  
[Información de referencia técnica sobre el cifrado](technical-reference-details-about-encryption.md)
  
[Garantía de servicio en el Centro de &amp; cumplimiento de seguridad](./service-assurance.md)
