---
title: Cifrado de servicio con clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
ms.custom: seo-marvel-apr2020
description: En este artículo, aprenderá cómo funciona el cifrado de servicio con la clave de cliente en Microsoft 365.
ms.openlocfilehash: 3d0c86dbca02a66547f0ade643b745ecfc8f92cd
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344775"
---
# <a name="service-encryption-with-customer-key"></a>Cifrado de servicio con clave de cliente

Microsoft 365 proporciona cifrado de nivel de volumen y línea base habilitado mediante BitLocker y el Administrador de claves distribuidas (DKM). Microsoft 365 ofrece una capa de cifrado adicional para el contenido. Este contenido incluye datos de Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Microsoft Teams.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Cómo funcionan conjuntamente el cifrado de servicio, BitLocker y clave de cliente

Los datos siempre se cifran en reposo en el servicio Microsoft 365 con BitLocker y DKM. Para obtener más información, [vea How Exchange Online secures your email secrets](exchange-online-secures-email-secrets.md). Clave de cliente proporciona protección adicional contra la visualización de datos por parte de sistemas o personal no autorizados, y complementa BitLocker cifrado de disco en centros de datos de Microsoft. El cifrado de servicio no está diseñado para impedir que el personal de Microsoft acceda a sus datos. En su lugar, la clave de cliente le ayuda a cumplir con las obligaciones reglamentarias o de cumplimiento para controlar las claves raíz. Autoriza explícitamente Microsoft 365 servicios de cifrado para que usen las claves de cifrado para proporcionar servicios en la nube de valor agregado, como exhibición de documentos electrónicos, antimalware, correo no deseado, indización de búsqueda, entre otros.

La clave de cliente se basa en el cifrado de servicio y le permite proporcionar y controlar claves de cifrado. Microsoft 365 a continuación, usa estas claves para cifrar los datos en reposo, tal como se describe en los Términos de servicios en [línea (OST).](https://www.microsoft.com/licensing/product-licensing/products.aspx) Clave de cliente le ayuda a cumplir las obligaciones de cumplimiento porque controla las claves de cifrado que Microsoft 365 para cifrar y descifrar datos.
  
Clave de cliente mejora la capacidad de su organización para satisfacer las demandas de requisitos de cumplimiento que especifican acuerdos clave con el proveedor de servicios en la nube. Con la clave de cliente, proporciona y controla las claves de cifrado raíz de sus Microsoft 365 datos en reposo en el nivel de aplicación. Como resultado, se ejerce el control sobre las claves de la organización.

## <a name="customer-key-with-hybrid-deployments"></a>Clave de cliente con implementaciones híbridas

Clave de cliente solo cifra los datos en reposo en la nube. La clave de cliente no funciona para proteger los buzones y archivos locales. Puede cifrar los datos locales mediante otro método, como BitLocker.

## <a name="about-data-encryption-policies"></a>Acerca de las directivas de cifrado de datos

Una directiva de cifrado de datos (DEP) define la jerarquía de cifrado. El servicio usa esta jerarquía para cifrar los datos con cada una de las claves que administra y la clave de disponibilidad protegida por Microsoft. Puede crear DEP con cmdlets de PowerShell y, a continuación, asignar esos DEP para cifrar los datos de la aplicación. Hay tres tipos de DEP admitidos por Microsoft 365 customer key, cada tipo de directiva usa cmdlets diferentes y proporciona cobertura para un tipo diferente de datos. Los DEP que puede definir incluyen:

**DEP para varias cargas Microsoft 365 de trabajo** Estos DEP cifran los datos en varias cargas de trabajo M365 para todos los usuarios del espacio empresarial. Estas cargas de trabajo incluyen:

- Teams de chat (chats de 1:1, chats de grupo, chats de reunión y conversaciones de canal)
- Teams multimedia (imágenes, fragmentos de código, mensajes de vídeo, mensajes de audio, imágenes wiki)
- Teams de llamadas y reuniones almacenadas en Teams almacenamiento
- Teams de chat
- Teams sugerencias de chat de Cortana
- Teams de estado
- Información de usuario y señal para Exchange Online
- Exchange Online buzones de correo que no están cifrados por los DEP de buzones
- Datos de coincidencia exacta de datos mip (EDM): (esquemas de archivo de datos, paquetes de reglas y sales usadas para hash de los datos confidenciales).
  Para la coincidencia exacta de datos de MIP (EDM) y Microsoft Teams, el DEP de varias cargas de trabajo cifra los nuevos datos desde el momento en que asigna el DEP al inquilino. Por Exchange Online, clave de cliente cifra todos los datos existentes y nuevos.

Los DEP de varias cargas de trabajo no cifran los siguientes tipos de datos. En su lugar, Microsoft 365 otros tipos de cifrado para proteger estos datos.

- SharePoint y OneDrive para la Empresa datos.
- Microsoft Teams archivos y algunas Teams de llamadas y reuniones guardadas en OneDrive para la Empresa y SharePoint Online se cifran mediante SharePoint Online DEP.
- Otras Microsoft 365 de trabajo como Yammer y Planner que actualmente no son compatibles con la clave de cliente.
- Teams Eventos en directo y preguntas&A en eventos en directo. Por Teams, este escenario es el único que no está cifrado por clave de cliente mediante DEP de varias cargas de trabajo.

Puede crear varios DEP por inquilino, pero solo asignar un DEP a la vez. Al asignar el DEP, el cifrado comienza automáticamente pero tarda algún tiempo en completarse en función del tamaño del espacio empresarial.

**DEP para Exchange Online buzones de correo** Los DEP de buzones proporcionan un control más preciso sobre los buzones individuales dentro de Exchange Online. Use DEP de buzones de correo para cifrar los datos almacenados en buzones EXO de distintos tipos, como UserMailbox, MailUser, Group, PublicFolder y Buzones compartidos. Puede tener hasta 50 DEP activos por inquilino y asignar esos DEP a buzones individuales. Puede asignar un DEP a varios buzones.

De forma predeterminada, los buzones se cifran con claves administradas por Microsoft. Al asignar un DEP de clave de cliente a un buzón:

- Si el buzón se cifra mediante un DEP de varias cargas de trabajo, el servicio vuelve a envolver el buzón con el nuevo DEP de buzón siempre que un usuario o una operación del sistema tenga acceso a los datos del buzón.

- Si el buzón ya está cifrado mediante claves administradas por Microsoft, el servicio vuelve a envolver el buzón con el nuevo DEP de buzón siempre que un usuario o una operación del sistema acceda a los datos del buzón.

- Si el buzón aún no está cifrado mediante cifrado predeterminado, el servicio marca el buzón para un movimiento. El cifrado tiene lugar una vez completado el movimiento. Los movimientos de buzones se rigen en función de las prioridades establecidas para todos los Microsoft 365. Para obtener más información, vea [Move requests in the Microsoft 365 service](/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service). Si los buzones no están cifrados en el tiempo especificado, póngase en contacto con Microsoft.

Más adelante, puede actualizar el DEP o asignar un DEP diferente al buzón, tal como se describe en Administrar clave de cliente [para Office 365](customer-key-manage.md). Cada buzón debe tener licencias adecuadas para tener asignado un DEP. Para obtener más información acerca de las licencias, vea [Before you set up Customer Key](customer-key-set-up.md#before-you-set-up-customer-key).

Los DEP se pueden asignar a un buzón compartido, un buzón de carpetas públicas y un buzón de Microsoft 365 de grupo para los inquilinos que cumplan el requisito de licencia para los buzones de usuario. No necesita licencias independientes para buzones que no son específicos del usuario para asignar DEP de clave de cliente.

Para los DEP de clave de cliente que asigne a buzones individuales, puede solicitar que Microsoft purgue los DEP específicos al salir del servicio. Para obtener información sobre el proceso de purga de datos y la revocación de claves, vea Revocar las claves e iniciar el proceso de ruta [de depuración de datos.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

Al revocar el acceso a las claves como parte de la salida del servicio, se elimina la clave de disponibilidad, lo que da como resultado la eliminación criptográfica de los datos. La eliminación criptográfica mitiga el riesgo de remanencia de datos, lo que es importante para cumplir con las obligaciones de seguridad y cumplimiento.

**DEP para SharePoint Online y OneDrive para la Empresa** Este DEP se usa para cifrar el contenido almacenado en SPO y OneDrive para la Empresa, incluidos los Microsoft Teams almacenados en SPO. Si usa la característica multige geográfica, puede crear un DEP por geo para su organización. Si no usa la característica multigeós, solo puede crear un DEP por inquilino. Consulte los detalles de [Configurar clave de cliente](customer-key-set-up.md).

### <a name="encryption-ciphers-used-by-customer-key"></a>Cifrados usados por clave de cliente

Clave de cliente usa varios cifrados de cifrado para cifrar claves como se muestra en las siguientes figuras.

La jerarquía de claves usada para los DEP que cifran los datos de varias cargas de trabajo Microsoft 365 es similar a la jerarquía usada para los DEP para buzones de correo Exchange Online individuales. La única diferencia es que la clave de buzón se reemplaza por la clave Microsoft 365 de carga de trabajo correspondiente.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Cifrados usados para cifrar claves para Exchange Online y Skype Empresarial

![Cifrado de cifrado para Exchange Online clave de cliente](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Cifrados usados para cifrar claves para SharePoint online, OneDrive para la Empresa y Teams archivos

![Cifrado de cifrado para SharePoint clave de cliente en línea](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artículos relacionados

- [Configurar clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Obtenga información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Caja de seguridad del cliente](customer-lockbox-requests.md)

- [Cifrado de servicio](office-365-service-encryption.md)