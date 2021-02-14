---
title: Cifrado en Microsoft Dynamics 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Obtenga información sobre cómo Microsoft usa la tecnología de cifrado para proteger los datos de los clientes en Microsoft Dynamics 365 mientras están en reposo en una base de datos de Microsoft y mientras están en tránsito.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bd349890fc7fc1ae7f1f7eaf07f90c22423637cf
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031420"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Cifrado en Microsoft Dynamics 365

Microsoft usa la tecnología de cifrado para proteger los datos de los clientes en Dynamics 365 mientras están en reposo en una base de datos de Microsoft y mientras están en tránsito entre los dispositivos de usuario y nuestros centros de datos. Las conexiones establecidas entre los clientes y los centros de datos de Microsoft se cifran y todos los puntos de conexión públicos se protegen mediante TLS estándar del sector. TLS establece de forma eficaz una conexión de explorador a servidor con seguridad mejorada para ayudar a garantizar la confidencialidad e integridad de los datos entre escritorios y centros de datos. Después de activar el cifrado de datos, no se puede desactivar. Para obtener más información, vea [Cifrado de datos de nivel de campo.](https://msdn.microsoft.com/library/dn481562.aspx)

Dynamics 365 usa cifrado Microsoft SQL Server nivel de celda estándar para un conjunto de atributos de entidad predeterminados que contienen información confidencial, como nombres de usuario y contraseñas de correo electrónico. Esta característica puede ayudar a las organizaciones a cumplir los requisitos de cumplimiento asociados con FIPS 140-2. El cifrado de datos de nivel de campo es especialmente importante en escenarios que aprovechan el enrutador de correo electrónico de [Microsoft Dynamics CRM,](https://technet.microsoft.com/library/hh699800.aspx)que debe almacenar nombres de usuario y contraseñas para permitir la integración entre una instancia de Dynamics 365 y un servicio de correo electrónico. 

Todas las instancias de Dynamics 365 usan [Microsoft SQL Server Cifrado](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) de datos transparente (TDE) para realizar el cifrado de datos en tiempo real cuando se escriben en el disco (en reposo). TDE cifra los archivos SQL Server, Azure SQL Database y Azure SQL Data Warehouse. De forma predeterminada, Microsoft almacena y administra las claves de cifrado de base de datos para las instancias de Dynamics 365. (Las claves que usa Dynamics 365 for Financials son generadas por la API de protección de datos de .NET Framework). 

La característica administrar claves en el Centro de administración de Dynamics 365 ofrece a los administradores la capacidad de administrar por sí mismo las claves de cifrado de base de datos asociadas con instancias de Dynamics 365. (Las claves de cifrado de bases de datos auto administradas solo están disponibles en la actualización de enero de 2017 para Microsoft Dynamics 365 y es posible que no estén disponibles para versiones posteriores. Para obtener más información, vea [Administrar las claves de cifrado para la instancia de Dynamics 365 (en línea).](https://docs.microsoft.com/dynamics365/customer-engagement/admin/manage-encryption-keys-instance) La característica de administración de claves admite archivos de clave de cifrado PFX y BYOK, como los almacenados en un LOCKER. (Para obtener más información acerca de cómo generar y transferir una clave protegida con HSM a través de Internet, vea Cómo generar y transferir claves protegidas con HSM para [Azure Key Vault).](https://docs.microsoft.com/azure/key-vault/key-vault-hsm-protected-keys) 

Para usar la opción de la clave de cifrado de carga, necesita la clave de cifrado pública y privada.

La característica de administración de claves quita la complejidad de la administración de claves de cifrado mediante Azure Key Vault para almacenar claves de cifrado de forma segura. Azure Key Vault ayuda a proteger claves criptográficas y secretos usados por servicios y aplicaciones en la nube. La característica de administración de claves no requiere que tenga una suscripción a Azure Key Vault y, en la mayoría de los casos, no es necesario tener acceso a las claves de cifrado que se usan para Dynamics 365 dentro del almacén.
