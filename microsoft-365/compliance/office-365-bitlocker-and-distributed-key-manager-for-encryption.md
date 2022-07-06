---
title: BitLocker para cifrado
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
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Obtenga información sobre cómo Office 365 usa el cifrado de BitLocker, lo que reduce la posibilidad de robo de datos debido a discos y equipos perdidos o robados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dec62da7bc4d29891dcd86ec378faeb52a2d3d9f
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633903"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker y Administrador de claves distribuidas (DKM) para el cifrado

Los servidores de Microsoft usan BitLocker para cifrar las unidades de disco que contienen datos del cliente en reposo en el nivel de volumen. El cifrado de BitLocker es una característica de protección de datos integrada en Windows. BitLocker es una de las tecnologías que se usan para protegerse contra amenazas en caso de que haya errores en otros procesos o controles (por ejemplo, el control de acceso o el reciclaje de hardware) que podrían dar lugar a que alguien obtenga acceso físico a los discos que contienen datos del cliente. En este caso, BitLocker elimina la posibilidad de robo o exposición de datos debido a la pérdida, robo o retirada inapropiada de equipos y discos.

BitLocker se implementa con cifrado estándar de cifrado avanzado (AES) de 256 bits en discos que contienen datos de cliente en Exchange Online, SharePoint Online y Skype Empresarial. Los sectores de disco se cifran con una clave de cifrado de volumen completo (FVEK), que se cifra con la clave maestra de volumen (VMK), que a su vez está enlazada al módulo de plataforma segura (TPM) del servidor. El VMK protege directamente el FVEK y, por lo tanto, la protección del VMK es fundamental. En la ilustración siguiente se muestra un ejemplo de la cadena de protección de claves de BitLocker para un servidor determinado (en este caso, mediante un servidor de Exchange Online).

En la tabla siguiente se describe la cadena de protección de claves de BitLocker para un servidor determinado (en este caso, un servidor Exchange Online).

| PROTECTOR DE CLAVE | GRANULARIDAD | ¿CÓMO SE GENERA? | ¿DÓNDE SE ALMACENA? | PROTECCIÓN |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Clave externa de 256 bits de AES | Por servidor | API de BitLocker | TPM o secreto seguro | Caja de seguridad/Access Control |
|  |  |  | Registro del servidor de buzones | TPM cifrado |
| Contraseña numérica de 48 dígitos | Por disco | API de BitLocker | Active Directory | Caja de seguridad/Access Control |
| Certificado X.509 como agente de recuperación de datos (DRA) también denominado protector de clave pública | Entorno (por ejemplo, Exchange Online multiinquilino) | Microsoft CA | Sistema de compilación | Ningún usuario tiene la contraseña completa en la clave privada. La contraseña está bajo protección física. |


La administración de claves de BitLocker implica la administración de claves de recuperación que se usan para desbloquear o recuperar discos cifrados en un centro de datos de Microsoft. Microsoft 365 almacena las claves maestras en una unidad compartida protegida, a la que solo pueden acceder personas que se hayan sometido a un proceso de filtrado y aprobación. Las credenciales de las claves se almacenan en un repositorio seguro para los datos de control de acceso (lo que llamamos un "almacén secreto"), lo que requiere un alto nivel de aprobaciones de elevación y administración para acceder mediante una herramienta de elevación de acceso Just-In-Time.

BitLocker admite claves que se dividen en dos categorías de administración:

- Claves administradas por BitLocker, que, en general, son de corta duración y están vinculadas a la vigencia de una instancia de sistema operativo instalada en un servidor o en un disco determinado. Estas claves se eliminan y restablecen durante la reinstalación del servidor o el formateo del disco.

- Claves de recuperación de BitLocker, que se administran fuera de BitLocker pero se usan para el descifrado de disco. BitLocker usa claves de recuperación para el escenario en el que un sistema operativo se reinstala y los discos de datos cifrados ya existen. Los sondeos de supervisión de disponibilidad administrada también utilizan claves de recuperación en Exchange Online cuando un respondedor pueda tener que desbloquear un disco.

Los volúmenes protegidos por BitLocker se cifran con una clave de cifrado de volumen completa, que a su vez se cifra con una clave maestra de volumen. BitLocker usa algoritmos compatibles con FIPS para asegurarse de que las claves de cifrado nunca se almacenan o envían a través de la conexión sin cifrar. La implementación por parte de Microsoft 365 de una protección de los datos de cliente en reposo no es distinta de la implementación por defecto de BitLocker.
