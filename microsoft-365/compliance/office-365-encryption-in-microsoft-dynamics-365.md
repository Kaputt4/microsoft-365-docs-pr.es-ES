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
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Obtenga información sobre cómo Microsoft usa la tecnología de cifrado para proteger los datos de los clientes en Microsoft Dynamics 365 mientras están en reposo en una base de datos de Microsoft y mientras están en tránsito.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ba3dbef73b7674364f19e83befdbb8cdfe417ad6
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67678809"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Cifrado en Microsoft Dynamics 365

Microsoft usa la tecnología de cifrado para proteger los datos de los clientes en Dynamics 365 mientras están en reposo en un centro de datos de Microsoft y mientras están en tránsito entre los dispositivos de usuario y nuestros centros de datos. Las conexiones establecidas entre los clientes y los centros de datos de Microsoft se cifran y todos los puntos de conexión públicos se protegen mediante TLS estándar del sector. TLS establece de forma eficaz una conexión de explorador a servidor mejorada con seguridad para ayudar a garantizar la confidencialidad y la integridad de los datos entre los equipos de escritorio y los centros de datos. Una vez activado el cifrado de datos, no se puede desactivar. Para obtener más información, consulte [Cifrado de datos de nivel de](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8)) campo.

Dynamics 365 usa el cifrado estándar de nivel de celda de Microsoft SQL Server para un conjunto de atributos de entidad predeterminados que contienen información confidencial, como nombres de usuario y contraseñas de correo electrónico. Esta característica puede ayudar a las organizaciones a cumplir los requisitos de cumplimiento asociados a FIPS 140-2. El cifrado de datos de nivel de campo es especialmente importante en escenarios que aprovechan la [Microsoft Dynamics CRM Email Router](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8)), que debe almacenar nombres de usuario y contraseñas para habilitar la integración entre una instancia de Dynamics 365 y un servicio de correo electrónico.

Todas las instancias de Dynamics 365 usan [Microsoft SQL Server Cifrado de datos transparente](/sql/relational-databases/security/encryption/transparent-data-encryption) (TDE) para realizar el cifrado de datos en tiempo real cuando se escriben en disco (en reposo). TDE cifra los archivos de datos SQL Server, Azure SQL Database y Azure SQL Data Warehouse. De forma predeterminada, Microsoft almacena y administra las claves de cifrado de base de datos para las instancias de Dynamics 365. (Las claves que usa Dynamics 365 for Financials se generan mediante la API de protección de datos de .NET Framework).

La característica administrar claves del Centro de administración de Dynamics 365 ofrece a los administradores la capacidad de administrar automáticamente las claves de cifrado de base de datos asociadas a instancias de Dynamics 365. (Las claves de cifrado de base de datos autoadministrado solo están disponibles en la actualización de enero de 2017 para Microsoft Dynamics 365 y es posible que no estén disponibles para versiones posteriores. Para obtener más información, consulte [Administración de las claves de cifrado de la instancia de Dynamics 365 (en línea](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance)). La característica de administración de claves admite archivos de clave de cifrado PFX y BYOK, como los almacenados en un HSM. (Para obtener más información sobre cómo generar y transferir una clave protegida por HSM a través de Internet, consulte [Cómo generar y transferir claves protegidas por HSM para Azure Key Vault](/azure/key-vault/key-vault-hsm-protected-keys)).

Para usar la opción cargar clave de cifrado, necesita la clave de cifrado pública y privada.

La característica de administración de claves elimina la complejidad de la administración de claves de cifrado mediante Azure Key Vault para almacenar de forma segura las claves de cifrado. Azure Key Vault ayuda a proteger las claves criptográficas y los secretos que usan las aplicaciones y servicios en la nube. La característica de administración de claves no requiere que tenga una suscripción de Azure Key Vault y, en la mayoría de las situaciones, no es necesario acceder a las claves de cifrado usadas para Dynamics 365 en el almacén.
