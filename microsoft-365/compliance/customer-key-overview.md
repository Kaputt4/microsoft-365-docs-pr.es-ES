---
title: Cifrado de servicio con clave de cliente de Microsoft Purview
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- purview-compliance
- m365solution-mip
- m365initiative-compliance
- tier1
- highpri
ms.custom: seo-marvel-apr2020
description: En este artículo, obtendrá información sobre cómo funciona el cifrado de servicio con la clave de cliente de Microsoft Purview.
ms.openlocfilehash: 9d4e19b322f1dd4672dfdf06fedeef23b1cdadbc
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68641873"
---
# <a name="service-encryption-with-microsoft-purview-customer-key"></a>Cifrado de servicio con clave de cliente de Microsoft Purview

Microsoft 365 proporciona cifrado de nivel de volumen y línea base habilitado a través de BitLocker y el Administrador de claves distribuidas (DKM). Microsoft 365 ofrece una capa de cifrado adicional para el contenido. Este contenido incluye datos de Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Microsoft Teams.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Cómo funcionan conjuntamente el cifrado de servicio, BitLocker y la clave de cliente

Los datos siempre se cifran en reposo en el servicio Microsoft 365 con BitLocker y DKM. Para obtener más información, consulte [Cómo Exchange Online protege los secretos de correo electrónico](exchange-online-secures-email-secrets.md). La clave de cliente proporciona protección adicional contra la visualización de datos por parte de sistemas o personal no autorizados, y complementa el cifrado de disco de BitLocker en centros de datos de Microsoft. El cifrado del servicio no está diseñado para impedir que el personal de Microsoft acceda a los datos. En su lugar, la clave de cliente le ayuda a cumplir las obligaciones normativas o de cumplimiento para controlar las claves raíz. Autoriza explícitamente a los servicios de Microsoft 365 a usar las claves de cifrado para proporcionar servicios en la nube de valor agregado, como eDiscovery, antimalware, antispam, indexación de búsqueda, etc.

La clave de cliente se basa en el cifrado del servicio y le permite proporcionar y controlar las claves de cifrado. A continuación, Microsoft 365 usa estas claves para cifrar los datos en reposo, como se describe en los [Términos de servicios en línea (OST)](https://www.microsoft.com/licensing/product-licensing/products.aspx) . La clave de cliente le ayuda a cumplir las obligaciones de cumplimiento porque controla las claves de cifrado que Microsoft 365 usa para cifrar y descifrar datos.
  
La clave del cliente mejora la capacidad de su organización para satisfacer las demandas de los requisitos de cumplimiento que especifican acuerdos clave con el proveedor de servicios en la nube. Con La clave de cliente, proporciona y controla las claves de cifrado raíz para los datos de Microsoft 365 en reposo en el nivel de aplicación. Como resultado, puede ejercer el control sobre las claves de su organización.

## <a name="customer-key-with-hybrid-deployments"></a>Clave de cliente con implementaciones híbridas

Customer Key solo cifra los datos en reposo en la nube. La clave de cliente no funciona para proteger los buzones y archivos locales. Puede cifrar los datos locales mediante otro método, como BitLocker.

## <a name="about-data-encryption-policies"></a>Acerca de las directivas de cifrado de datos

Una directiva de cifrado de datos (DEP) define la jerarquía de cifrado. El servicio usa esta jerarquía para cifrar los datos mediante cada una de las claves que administra y la clave de disponibilidad protegida por Microsoft. Los DEP se crean mediante cmdlets de PowerShell y, a continuación, se asignan esos DEP para cifrar los datos de la aplicación. Hay tres tipos de DEP compatibles con la clave de cliente; cada tipo de directiva usa cmdlets diferentes y proporciona cobertura para un tipo de datos diferente. Los DEP que puede definir incluyen:

**DEP para varias cargas de trabajo de Microsoft 365** Estos DEP cifran los datos en varias cargas de trabajo M365 para todos los usuarios del inquilino. Estas cargas de trabajo incluyen:

- Mensajes de chat de Teams (chats 1:1, chats de grupo, chats de reuniones y conversaciones de canal)
- Mensajes multimedia de Teams (imágenes, fragmentos de código, mensajes de vídeo, mensajes de audio, imágenes wiki)
- Grabaciones de llamadas y reuniones de Teams almacenadas en el almacenamiento de Teams
- Notificaciones de chat de Teams
- Sugerencias de chat de Teams de Cortana
- Mensajes de estado de Teams
- Información de usuario y señal para Exchange Online
- Exchange Online buzones que aún no están cifrados por los DEP de buzón
- Microsoft Purview Information Protection:

  - Datos exactos de coincidencia de datos (EDM), incluidos esquemas de archivos de datos, paquetes de reglas y las sales que se usan para aplicar hash a la información confidencial. Para EDM y Microsoft Teams, el DEP de varias cargas de trabajo cifra los nuevos datos desde el momento en que asigna el DEP al inquilino. Por Exchange Online, Clave de cliente cifra todos los datos existentes y nuevos.

  - Configuración de etiquetas para etiquetas de confidencialidad

Los DEP de varias cargas de trabajo no cifran los siguientes tipos de datos. En su lugar, Microsoft 365 usa otros tipos de cifrado para proteger estos datos.

- SharePoint y OneDrive para la Empresa datos.
- Los archivos de Microsoft Teams y algunas grabaciones de llamadas y reuniones de Teams guardadas en OneDrive para la Empresa y SharePoint Online se cifran mediante el DEP de SharePoint Online.
- Otras cargas de trabajo de Microsoft 365, como Yammer y Planner, que actualmente no son compatibles con la clave de cliente.
- Datos de eventos en directo de Teams.

Puede crear varios DEP por inquilino, pero asignar solo un DEP a la vez. Al asignar el DEP, el cifrado comienza automáticamente, pero tarda algún tiempo en completarse en función del tamaño del inquilino.

**Los DEP de los buzones de Exchange Online buzones** de correo proporcionan un control más preciso sobre los buzones individuales dentro de Exchange Online. Use los DEP de buzón de correo para cifrar los datos almacenados en buzones EXO de diferentes tipos, como UserMailbox, MailUser, Group, PublicFolder y Shared mailboxes. Puede tener hasta 50 DEP activos por inquilino y asignar esos DEP a buzones individuales. Puede asignar un DEP a varios buzones.

De forma predeterminada, los buzones se cifran mediante claves administradas por Microsoft. Al asignar un DEP de clave de cliente a un buzón de correo:

- Si el buzón de correo se cifra mediante un DEP de varias cargas de trabajo, el servicio vuelve a encapsular el buzón con el nuevo DEP de buzón, siempre y cuando un usuario o una operación del sistema acceda a los datos del buzón.

- Si el buzón ya está cifrado mediante claves administradas por Microsoft, el servicio vuelve a encapsular el buzón con el nuevo DEP de buzón, siempre y cuando un usuario o una operación del sistema acceda a los datos del buzón.

- Si el buzón de correo aún no está cifrado mediante cifrado predeterminado, el servicio marca el buzón para un movimiento. El cifrado tiene lugar una vez completado el movimiento. Los movimientos de buzón se rigen en función de las prioridades establecidas para todo Microsoft 365. Para obtener más información, vea [Mover solicitudes en el servicio Microsoft 365](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-microsoft-365-or-office-365-service). Si los buzones no se cifran en el tiempo especificado, póngase en contacto con Microsoft.

Más adelante, puede actualizar el DEP o asignar un DEP diferente al buzón, tal como se describe en [Administrar clave de cliente para Office 365](customer-key-manage.md). Cada buzón debe tener las licencias adecuadas para que se le asigne un DEP. Para obtener más información sobre las licencias, consulte [Antes de configurar la clave de cliente](customer-key-set-up.md#before-you-set-up-customer-key).

Los DEP se pueden asignar a un buzón compartido, un buzón de carpeta pública y un buzón de grupo de Microsoft 365 para los inquilinos que cumplen el requisito de licencia para los buzones de usuario. No necesita licencias independientes para que los buzones no específicos del usuario asignen DEP de clave de cliente.

En el caso de los DEP de clave de cliente que asigne a buzones individuales, puede solicitar que Microsoft purgue los DEP específicos cuando deje el servicio. Para obtener información sobre el proceso de purga de datos y la revocación de claves, consulte [Revocación de las claves e inicio del proceso de ruta de acceso de purga de datos](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

Al revocar el acceso a las claves como parte de la salida del servicio, se elimina la clave de disponibilidad, lo que da lugar a la eliminación criptográfica de los datos. La eliminación criptográfica mitiga el riesgo de remanencia de datos, que es importante para cumplir las obligaciones de seguridad y cumplimiento.

**DEP para SharePoint Online y OneDrive para la Empresa** Este DEP se usa para cifrar el contenido almacenado en SPO y OneDrive para la Empresa, incluidos los archivos de Microsoft Teams almacenados en SPO. Si usa la característica multigeográfica, puede crear un DEP por ubicación geográfica para su organización. Si no usa la característica multigeográfica, solo puede crear un DEP por inquilino. Consulte los detalles de [Configuración de la clave de cliente](customer-key-set-up.md).

### <a name="encryption-ciphers-used-by-customer-key"></a>Cifrado de cifrado utilizado por la clave de cliente

La clave de cliente usa varios cifrados para cifrar las claves, como se muestra en las ilustraciones siguientes.

La jerarquía de claves que se usa para los DEP que cifran los datos de varias cargas de trabajo de Microsoft 365 es similar a la jerarquía que se usa para los DEP para buzones de Exchange Online individuales. La única diferencia es que la clave de buzón de correo se reemplaza por la clave de carga de trabajo de Microsoft 365 correspondiente.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Cifrado de cifrado que se usa para cifrar claves para Exchange Online y Skype Empresarial

![Cifrado de cifrado para Exchange Online clave de cliente.](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Cifrado de cifrado que se usa para cifrar claves para archivos de SharePoint Online, OneDrive para la Empresa y Teams

![Cifrado de cifrado para la clave de cliente de SharePoint Online.](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artículos relacionados

- [Configuración de la clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Más información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Caja de seguridad del cliente](customer-lockbox-requests.md)

- [Cifrado de servicio](office-365-service-encryption.md)
