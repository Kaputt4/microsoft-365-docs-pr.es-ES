---
title: Cómo Exchange Online protege su información confidencial de correo electrónico
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/31/2022
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- purview-compliance
description: 'Además del Centro de confianza de Microsoft que proporciona información de seguridad, privacidad e cumplimiento para Microsoft 365, obtenga información sobre cómo Microsoft ayuda a proteger los secretos que almacena en sus centros de datos. '
ms.openlocfilehash: e46788c763e7b930c79abc918a9f4706b896ff23
ms.sourcegitcommit: a66b30765efc0ea0eca865f08a62d45047a90246
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68828062"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Cómo Exchange Online protege su información confidencial de correo electrónico

Este artículo describe cómo Microsoft protege su información confidencial de correo electrónico en sus centros de datos.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="how-we-secure-secret-information-provided-by-you"></a>Cómo protegemos la información secreta proporcionada por usted

Además del Centro de confianza de Office 365 que proporciona [información de seguridad, privacidad e cumplimiento para Office 365](./get-started-with-service-trust-portal.md), usamos una tecnología denominada Distributed Key Manager (DKM).
  
[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) es una tecnología del lado cliente que usa un conjunto de claves secretas para cifrar y descifrar información. Solo los miembros de un grupo de seguridad específico de los Servicios de dominio de Active Directory pueden tener acceso a dichas claves para descifrar los datos cifrados por el DKM. En Exchange Online, solo determinadas cuentas de servicio bajo las cuales se ejecutan procesos de Exchange forman parte del grupo de seguridad. No se proporcionan credenciales humanas que formen parte de este grupo de seguridad y, por lo tanto, ningún usuario tiene acceso a las claves que pueden descifrar estos secretos.
  
Para depuración, solución de problemas o fines de auditoria, un administrador del centro de datos debe solicitar acceso con privilegios elevados para obtener credenciales temporales que forman parte del grupo de seguridad. Este proceso requiere varios niveles de aprobación legal. Si se concede acceso, toda la actividad se registra y se audita. El acceso solo se concede durante un intervalo de tiempo establecido después del cual expira automáticamente.
  
Para brindar protección adicional, la tecnología del DKM incluye sustitución de claves y archivado automáticos. La sustitución y el archivado automatizados garantizan que puede seguir accediendo al contenido anterior sin tener que depender de la misma clave indefinidamente.
  
## <a name="where-exchange-online-uses-dkm"></a>Donde Exchange Online usa DKM

Microsoft usa [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) para cifrar los secretos en Exchange Online centros de datos. Por ejemplo:
  
- Email credenciales de cuenta para las cuentas conectadas. Las cuentas conectadas son cuentas de terceros, como Hotmail, Gmail y Yahoo! cuentas de correo.

- Clave de cliente. Si usa el cifrado de [servicio con la clave de cliente de Microsoft Purview](customer-key-overview.md), usará [Azure Key Vault](/azure/key-vault/key-vault-whatis) para proteger los secretos.

## <a name="related-articles"></a>Artículos relacionados

[Cifrado en Office 365](encryption.md)
  
[Información de referencia técnica sobre el cifrado](technical-reference-details-about-encryption.md)
  
[Garantía de servicio en el portal de cumplimiento Microsoft Purview](./service-assurance.md)
