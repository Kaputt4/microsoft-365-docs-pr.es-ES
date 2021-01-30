---
title: Cifrado de servicio con clave de cliente
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
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
ms.openlocfilehash: efb2ba9c2532973a096c509b57639544fc2ddbe5
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058493"
---
# <a name="service-encryption-with-customer-key"></a>Cifrado de servicio con clave de cliente

Microsoft 365 proporciona cifrado de nivel de volumen de línea base habilitado a través de BitLocker y el Administrador de claves distribuidas (DKM). Microsoft 365 ofrece una capa adicional de cifrado en la capa de la aplicación para su contenido. Este contenido incluye datos de archivos de Exchange Online, Skype Empresarial, SharePoint Online, OneDrive para la Empresa y Teams. Este nivel de cifrado agregado se denomina cifrado de servicio.

## <a name="how-service-encryption-bitlocker-and-customer-key-work-together"></a>Cómo funcionan conjuntamente el cifrado de servicio, BitLocker y clave de cliente

El cifrado del servicio garantiza que el contenido en reposo se cifra en la capa de servicio. Los datos siempre se cifran en reposo en el servicio **de Microsoft 365 con BitLocker y DKM.** Para obtener más información, consulte "Seguridad, privacidad e información de cumplimiento" y cómo Exchange Online protege [sus secretos de correo electrónico.](exchange-online-secures-email-secrets.md) La clave de cliente proporciona protección adicional contra la visualización de datos por parte de sistemas o personal no autorizados, y complementa el cifrado de disco de BitLocker en centros de datos de Microsoft. El cifrado del servicio no está diseñado para impedir que el personal de Microsoft acceda a los datos de los clientes. El propósito principal es ayudar a los clientes a cumplir con las obligaciones reglamentarias o de cumplimiento para controlar las claves raíz. Los clientes autorizan explícitamente a los servicios de O365 a usar sus claves de cifrado para proporcionar servicios en la nube de valor agregado, como eDiscovery, antimalware, correo no deseado, indización de búsqueda, etc.

La clave de cliente se basa en el cifrado del servicio y le permite proporcionar y controlar las claves de cifrado. A continuación, Microsoft 365 usa estas claves para cifrar los datos en reposo, tal como se describe en los Términos de [Online Services (OST).](https://www.microsoft.com/licensing/product-licensing/products.aspx) La clave de cliente le ayuda a cumplir las obligaciones de cumplimiento, ya que controla las claves de cifrado que Microsoft 365 usa para cifrar y descifrar datos.
  
Clave de cliente mejora la capacidad de su organización para satisfacer las demandas de requisitos de cumplimiento que especifican las disposiciones clave con el proveedor de servicios en la nube. Con la clave de cliente, proporciona y controla las claves de cifrado raíz de los datos en reposo de Microsoft 365 en el nivel de aplicación. Como resultado, puede ejercer el control sobre las claves de su organización. Si decide salir del servicio, revocará el acceso a las claves raíz de su organización. Para todos los servicios de Microsoft 365, revocar el acceso a las claves es el primer paso en la ruta hacia la eliminación de datos. Al revocar el acceso a las claves, los datos son ilegibles para el servicio.

## <a name="customer-key-encrypts-data-at-rest-in-office-365"></a>Clave de cliente cifra los datos en reposo en Office 365

Con las claves que proporciones, la clave de cliente cifra:

- Archivos de SharePoint Online, OneDrive para la Empresa y Teams.
- Archivos cargados en OneDrive para la Empresa.
- Contenido del buzón de Exchange Online, incluido el contenido del cuerpo del correo electrónico, las entradas de calendario y el contenido de los datos adjuntos del correo electrónico.
- Conversaciones de texto de Skype Empresarial.

Actualmente no ofrecemos al cliente el control de las claves de cifrado para las cargas de contenido de difusión de reunión de Skype y reunión de Skype. En su lugar, este contenido se cifra junto con el resto del contenido de Office 365.

### <a name="customer-key-with-hybrid-deployments"></a>Clave de cliente con implementaciones híbridas

La clave de cliente solo cifra los datos en reposo en la nube. La clave de cliente no funciona para proteger los buzones y archivos locales. Puedes cifrar los datos locales mediante otro método, como BitLocker.

## <a name="about-the-data-encryption-policy-dep"></a>Acerca de la directiva de cifrado de datos (DEP)

Una directiva de cifrado de datos define la jerarquía de cifrado para cifrar datos mediante cada una de las claves que proporcione, así como la clave de disponibilidad protegida por Microsoft. Puede crear DEP con cmdlets de PowerShell, que son diferentes para cada servicio, y asignar esos DEP para cifrar los datos de la aplicación. Por ejemplo:

**Exchange Online y Skype Empresarial** Puede crear hasta 50 DEP por inquilino. Los DEP se asocian a las claves de cliente en Azure Key Vault y, a continuación, se asignan a buzones individuales. Cuando asigna un DEP a un buzón:

- el buzón está marcado para un movimiento de buzón. En función de las prioridades de Microsoft 365, como se describe aquí, solicitudes de movimiento en el servicio [de Microsoft 365](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#move-requests-in-the-office-365-service).

- El cifrado tiene lugar mientras se mueve el buzón. Espere 72 horas para que el buzón se cifra con el nuevo DEP. Si los buzones no están cifrados después de esperar 72 horas desde el momento en que asignó el DEP, póngase en contacto con Microsoft.

Más adelante, puede actualizar el DEP o asignar un DEP diferente al buzón como se describe en Administrar clave de cliente [para Office 365.](customer-key-manage.md) Cada buzón debe tener las licencias adecuadas para asignar un DEP. Para obtener más información acerca de las licencias, vea [Antes de configurar la clave de cliente.](customer-key-set-up.md#before-you-set-up-customer-key)

> [!NOTE]
> El DEP se puede aplicar a un buzón compartido, un buzón de carpetas públicas y un buzón de grupo de Microsoft 365 para los inquilinos que cumplan los requisitos de licencia para los buzones de usuario, aunque algunos de estos tipos de buzones no pueden ser una licencia asignada (buzón de carpetas públicas y buzón de grupo de Microsoft 365) o necesitan una licencia para aumentar el almacenamiento (buzón compartido).

**Archivos de SharePoint Online, OneDrive para la Empresa y Teams** Si usa la característica multige geográfica, puede crear hasta un DEP por geo para su organización. Puede usar claves de cliente diferentes para cada ubicación geográfica. Si no usa la característica multige geográfica, solo puede crear un DEP por inquilino. Al asignar el DEP, el cifrado comienza automáticamente, pero puede tardar algún tiempo en completarse. Consulte los detalles de [Configurar clave de cliente.](customer-key-set-up.md)

## <a name="leaving-the-service"></a>Salir del servicio

La clave de cliente le ayuda a cumplir las obligaciones de cumplimiento, ya que le permite revocar las claves al salir del servicio de Microsoft 365. Al revocar las claves como parte de la salida del servicio, la clave de disponibilidad se elimina, lo que provoca la eliminación criptográfica de los datos. La eliminación criptográfica mitiga el riesgo de remanencia de datos, lo que es importante para cumplir con las obligaciones de seguridad y cumplimiento. Para obtener información sobre el proceso de depuración de datos y la revocación de claves, vea Revocar las [claves e iniciar el proceso de ruta de depuración de datos.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

### <a name="encryption-ciphers-used-by-customer-key"></a>Cifrados usados por clave de cliente

La clave de cliente usa una variedad de cifrados para cifrar claves, como se muestra en las siguientes figuras.

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Cifrados usados para cifrar claves para Exchange Online y Skype Empresarial

![Cifrado de cifrado para la clave de cliente de Exchange Online](../media/customerkeyencryptionhierarchiesexchangeskype.png)

#### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Cifrados usados para cifrar claves para archivos de SharePoint Online, OneDrive para la Empresa y Teams

![Cifrado de cifrado para la clave de cliente de SharePoint Online](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Artículos relacionados

- [Configurar la clave de cliente](customer-key-set-up.md)

- [Administrar clave de cliente](customer-key-manage.md)

- [Rotar o alternar una Clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Más información sobre la clave de disponibilidad](customer-key-availability-key-understand.md)

- [Caja de seguridad del cliente](customer-lockbox-requests.md)

- [Cifrado de servicio](office-365-service-encryption.md)
