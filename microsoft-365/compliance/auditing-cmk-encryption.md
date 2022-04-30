---
title: Uso de claves administradas por el cliente para cifrar los datos de auditoría de la organización
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo usar claves administradas por el cliente para cifrar los registros de auditoría de su organización.
ms.openlocfilehash: afbae48b0417c42edd7e14220fb21f6402af1da7
ms.sourcegitcommit: e0f890f46ae0bde03cc9e1ce178a7c1b8fbe12db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2022
ms.locfileid: "65145427"
---
# <a name="use-customer-key-to-encrypt-audit-records"></a>Uso de la clave de cliente para cifrar los registros de auditoría

Ahora puede habilitar el cifrado de claves de cliente de Microsoft Purview para los registros de auditoría. La auditoría se basa en el [cifrado del servicio con la clave de cliente de Microsoft Purview](customer-key-overview.md) para cifrar los datos de auditoría de la organización. La implementación de la clave de cliente proporciona protección adicional al impedir que los sistemas no autorizados o el personal del centro de datos de Microsoft vean los datos de auditoría en la canalización de auditoría y en reposo. El uso de la clave de cliente para cifrar los datos de auditoría también le ayuda a cumplir las obligaciones normativas o de cumplimiento, ya que su organización proporciona y controla las claves de cifrado.

La clave de cliente requiere una suscripción Microsoft 365 E5. Para obtener más información, consulte [Microsoft 365 guía para el cumplimiento de & de seguridad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-customer-key-for-microsoft-365).

Incluso si no usa la clave de cliente para cifrar los registros de auditoría, los datos en reposo en Microsoft 365 se cifran de forma predeterminada.

## <a name="implement-customer-key-for-auditing"></a>Implementación de la clave de cliente para la auditoría

Para implementar la clave de cliente para la auditoría, debe crear una directiva de cifrado de datos (DEP) de varias cargas de trabajo, que defina la jerarquía de cifrado. El servicio usa esta jerarquía para cifrar los datos de auditoría mediante las dos claves raíz que administra y la clave de disponibilidad generada y protegida automáticamente por Microsoft.

Para obtener instrucciones detalladas paso a paso, consulte [Configuración de la clave de cliente](customer-key-set-up.md).

Después de completar la instalación, Microsoft 365 cifra todos los datos de la organización, incluidos los registros de auditoría, mediante las claves que se identifican en el DEP de varias cargas de trabajo que ha creado.

## <a name="offboarding-from-customer-key"></a>Offboarding from Customer Key

Si decide no usar la clave de cliente para asignar dep de varias cargas de trabajo, deberá ponerse en contacto con el soporte técnico de Microsoft con una solicitud para "offboard" desde la clave de cliente. Pida al equipo de soporte técnico que abra una solicitud de servicio contra el equipo de clave de cliente de Microsoft Purview. Póngase en contacto con m365-ck@service.microsoft.com si tiene alguna pregunta. Consulte [Reversión de la clave de cliente a las claves administradas por Microsoft](customer-key-manage.md#roll-back-from-customer-key-to-microsoft-managed-keys) para obtener más información.

Es posible que los clientes ya no quieran administrar sus propias claves y que opten por desconectarse de CMK.
Para la auditoría: no hemos incorporado a MMK. Por lo tanto, una vez que el inquilino se desconecte de CMK, no habrá ninguna reserva en el segundo nivel de cifrado. Los datos se cifrarán en reposo mediante el cifrado de almacenamiento de Azure predeterminado.

<!--
Steps: 

- Customer reaches out to MDEPS team to offboard from CMK.

- MDEPS team offboards the customer and marks their DEPs as disabled -

- New data for the customer / tenant will not be encrypted

- Existing / Older encrypted data will be decrypted using the keys associated with the DEP

NOTE: Even after offboarding, tenant is expected to keep their pre-used encryption keys and keep the MDEPS AAD app access to the AKVs till the lifetime of their encrypted data.
-->

## <a name="offboarding-from-microsoft-365"></a>Offboarding from Microsoft 365

No se admite la purga de un DEP de varias cargas de trabajo para la clave de cliente de Microsoft Purview. El DEP de varias cargas de trabajo se usa para cifrar los datos en varias cargas de trabajo entre todos los usuarios del inquilino. La purga de un DEP de varias cargas de trabajo provocaría que los datos de varias cargas de trabajo se hicieran inaccesibles. Si decide salir por completo de los servicios de Microsoft Purview, podría seguir la ruta de acceso de eliminación de inquilinos según el [proceso documentado](/azure/active-directory/enterprise-users/directory-delete-howto). Vea cómo eliminar un inquilino en Azure Active Directory."

<!--
- Customer in this case wants to leave the M365 eco-system and ensure all their data is purged / deleted.
- In case of "multi-workload" DEP - purging or deleting the DEP is NOT allowed by policy.
- In this case the customer would revoke access to the AKV containing the CMK keys.
The customer would proceed with the Tenant Deprovisioning process in order to fully leave the service. They may revoke keys, but not required by the process.
- This change would be reflected in ~24 hours across ALE and MDEPS after caches have expired.
- Ideally since customer is exiting the eco-system, no more audit events would be generated for the customer. However in case there are new audit events for the customer, then they will NOT be encrypted using CMK as customer has offboarded / revoked key access.
-->

## <a name="more-information"></a>Más información

- Los pasos de implementación tardan hasta 24 horas en cifrar los registros de auditoría de la organización.
- Si su organización ya tiene compatibilidad con MDEPS para otras cargas de trabajo (por ejemplo, Exchange o SharePoint), solo tiene que habilitarla para varias cargas de trabajo.
- Solo se cifrarán los registros de auditoría que se generan después de implementar la clave de cliente para la auditoría (o si su organización implementó la clave de cliente para varias cargas de trabajo). Los registros de auditoría existentes no se cifran.
