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
description: Obtenga información sobre cómo Microsoft usa la tecnología de cifrado para proteger los datos de los clientes en Microsoft Dynamics 365 mientras está en reposo en una base de datos de Microsoft y mientras está en tránsito.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1c55c4ac233c61f7a583f4f1a94222133f1d7c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926227"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Cifrado en Microsoft Dynamics 365

Microsoft usa la tecnología de cifrado para proteger los datos de los clientes en Dynamics 365 mientras está en reposo en una base de datos de Microsoft y mientras está en tránsito entre los dispositivos de usuario y nuestros centros de datos. Las conexiones establecidas entre clientes y centros de datos de Microsoft están cifradas y todos los puntos de conexión públicos se protegen mediante TLS estándar del sector. TLS establece eficazmente una conexión de explorador a servidor mejorada en seguridad para ayudar a garantizar la confidencialidad e integridad de los datos entre escritorios y centros de datos. Después de activar el cifrado de datos, no se puede desactivar. Para obtener más información, vea [Field-level data encryption](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8)).

Dynamics 365 usa el cifrado Microsoft SQL Server nivel de celda estándar para un conjunto de atributos de entidad predeterminados que contienen información confidencial, como nombres de usuario y contraseñas de correo electrónico. Esta característica puede ayudar a las organizaciones a cumplir los requisitos de cumplimiento asociados con FIPS 140-2. El cifrado de datos a nivel de campo es especialmente importante en escenarios que aprovechan el enrutador de correo electrónico de [Microsoft Dynamics CRM](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8)), que debe almacenar nombres de usuario y contraseñas para permitir la integración entre una instancia de Dynamics 365 y un servicio de correo electrónico. 

Todas las instancias de Dynamics 365 usan [Microsoft SQL Server Transparent Data Encryption](/sql/relational-databases/security/encryption/transparent-data-encryption?view=sql-server-2017) (TDE) para realizar el cifrado en tiempo real de los datos cuando se escriben en el disco (en reposo). TDE cifra los SQL Server, azure SQL base de datos y azure SQL de datos de almacenamiento de datos. De forma predeterminada, Microsoft almacena y administra las claves de cifrado de base de datos para las instancias de Dynamics 365. (Las claves usadas por Dynamics 365 for Financials se generan mediante la API .NET Framework protección de datos). 

La característica administrar claves del Centro de administración de Dynamics 365 ofrece a los administradores la capacidad de administrar las claves de cifrado de bases de datos asociadas con instancias de Dynamics 365. (Las claves de cifrado de bases de datos auto administradas solo están disponibles en la actualización de enero de 2017 para Microsoft Dynamics 365 y es posible que no estén disponibles para versiones posteriores. Para obtener más información, vea [Manage the encryption keys for your Dynamics 365 (online) instance](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance).) La característica de administración de claves admite archivos de clave de cifrado PFX y BYOK, como los almacenados en un HSM. (Para obtener más información acerca de cómo generar y transferir una clave protegida por HSM a través de Internet, consulte How [to generate and transfer HSM-protected keys for Azure Key Vault](/azure/key-vault/key-vault-hsm-protected-keys).) 

Para usar la opción de la clave de cifrado de carga, necesita la clave de cifrado pública y privada.

La característica de administración de claves quita la complejidad de la administración de claves de cifrado mediante Azure Key Vault para almacenar de forma segura las claves de cifrado. Azure Key Vault ayuda a proteger las claves criptográficas y los secretos usados por los servicios y aplicaciones en la nube. La característica de administración de claves no requiere que tenga una suscripción a Azure Key Vault y, en la mayoría de las situaciones, no es necesario tener acceso a las claves de cifrado usadas para Dynamics 365 en el almacén.