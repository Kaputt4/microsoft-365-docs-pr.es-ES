---
title: Cifrado de servicio de Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumen: comprenda el cifrado de datos en la capa de servicio en Microsoft Office 365.'
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193466"
---
# <a name="office-365-service-encryption"></a>Cifrado de servicio de Office 365

Además de usar BitLocker para el cifrado de nivel de volumen, Exchange Online, Skype empresarial, SharePoint Online, OneDrive para la empresa y Teams también usan el cifrado de servicio para cifrar los datos de clientes. El cifrado del servicio permite dos opciones de administración de claves:

- Microsoft administra todas las claves de cifrado. Esta opción está disponible actualmente en chats de SharePoint Online, OneDrive para la empresa, Skype empresarial y Microsoft Teams. Los datos se cifran de forma predeterminada con las claves administradas de Microsoft.

- La organización proporciona las claves raíz. Estas claves se administran con Azure Key Vault. Esta opción se denomina clave de cliente. La clave de cliente está disponible actualmente para los archivos de Exchange Online, SharePoint Online, OneDrive para la empresa, Skype empresarial y Microsoft Teams. Si usa la clave de cliente, estas claves reemplazan las claves administradas de Microsoft para cifrar los datos.

Independientemente de la opción que elija, el cifrado de servicio ofrece varias ventajas:

- Exige la autenticación del usuario para recuperar y descifrar los datos solicitados por un usuario autorizado.

- Proporciona la separación de los administradores del sistema operativo Windows del acceso a los datos de clientes almacenados o procesados por el sistema operativo.

- Mejora la capacidad de Office 365 para satisfacer las demandas de los clientes que tienen requisitos de cumplimiento relacionados con el cifrado.

Para obtener información sobre cómo configurar la clave de cliente de Office 365 para los archivos de Exchange Online, Skype empresarial, SharePoint Online, OneDrive para la empresa y Microsoft Teams, vea estos artículos:

- [Cifrado de servicios con clave de cliente en Office 365](customer-key-overview.md)

- [Configurar la clave de cliente de Office 365](customer-key-set-up.md)

- [Administrar la clave de cliente de Office 365](customer-key-manage.md)

- [Rollo o rotación de una clave de cliente o una clave de disponibilidad](customer-key-availability-key-roll.md)

- [Descripción de la clave de disponibilidad](customer-key-availability-key-understand.md)
