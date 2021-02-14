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
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Obtenga información sobre cómo Office 365 usa el cifrado de BitLocker, lo que reduce el potencial de robo de datos debido a equipos y discos perdidos o robados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033628"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker y Administrador de claves distribuidas (DKM) para el cifrado

Los servidores de Microsoft usan BitLocker para cifrar las unidades de disco que contienen datos de clientes en reposo en el nivel de volumen. El cifrado de BitLocker es una característica de protección de datos integrada en Windows. BitLocker es una de las tecnologías que se usan para proteger contra amenazas en caso de que haya fallos en otros procesos o controles (por ejemplo, control de acceso o reciclaje de hardware) que podrían llevar a que alguien obtenga acceso físico a discos que contienen datos de clientes. En este caso, BitLocker elimina la posibilidad de robo o exposición de datos debido a la pérdida, robo o retirada inapropiada de equipos y discos.

BitLocker se implementa con cifrado estándar de cifrado avanzado (AES) de 256 bits en discos que contienen datos de clientes en Exchange Online, SharePoint Online y Skype Empresarial. Los sectores de disco se cifran con una clave de cifrado de volumen completo (FVEK), que se cifra con la clave maestra de volumen (VMK), que a su vez está enlazada al Módulo de plataforma segura (TPM) del servidor. La VMK protege directamente el FVEK y, por lo tanto, la protección de la VMK se vuelve fundamental. En la figura siguiente se muestra un ejemplo de la cadena de protección de claves de BitLocker para un servidor determinado (en este caso, mediante un servidor de Exchange Online).

En la tabla siguiente se describe la cadena de protección de claves de BitLocker para un servidor determinado (en este caso, un servidor de Exchange Online).

| PROTECTOR DE CLAVE | GRANULARIDAD | ¿CÓMO SE GENERA? | ¿DÓNDE SE ALMACENA? | PROTECCIÓN |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Clave externa AES de 256 bits | Por servidor | API de BitLocker | TPM o secreto seguro | Caja de seguridad /Control de acceso |
|  |  |  | Registro del servidor de buzones de correo | TPM cifrado |
| Contraseña numérica de 48 dígitos | Por disco | API de BitLocker | Active Directory | Caja de seguridad /Control de acceso |
| Certificado X.509 como agente de recuperación de datos (DRA) también denominado Protector de clave pública | Entorno (por ejemplo, Multitenant de Exchange Online) | Entidad de certificación de Microsoft | Sistema de compilación | Ningún usuario tiene la contraseña completa para la clave privada. La contraseña está bajo protección física. |


La administración de claves de BitLocker implica la administración de claves de recuperación que se usan para desbloquear o recuperar discos cifrados en un centro de datos de Microsoft. Microsoft 365 almacena las claves maestras en un recurso compartido seguro, al que solo pueden acceder las personas que se han proyectado y aprobado. Las credenciales de las claves se almacenan en un repositorio seguro para los datos de control de acceso (lo que se llama "almacén secreto"), lo que requiere un alto nivel de aprobaciones de elevación y administración para acceder mediante una herramienta de elevación de acceso just-in-time.

BitLocker admite claves que se divide en dos categorías de administración:

- Claves administradas por BitLocker, que generalmente son de corta duración y están vinculadas a la duración de una instancia del sistema operativo instalada en un servidor o en un disco determinado. Estas claves se eliminan y restablecen durante la reinstalación del servidor o el formato de disco.

- Claves de recuperación de BitLocker, que se administran fuera de BitLocker pero se usan para el descifrado de disco. BitLocker usa claves de recuperación para el escenario en el que se reinstala un sistema operativo y ya existen discos de datos cifrados. Los sondeos de supervisión de disponibilidad administrada también usan las claves de recuperación en Exchange Online, donde un respondedor puede necesitar desbloquear un disco.

Los volúmenes protegidos con BitLocker se cifran con una clave de cifrado de volumen completo, que a su vez se cifra con una clave maestra de volumen. BitLocker usa algoritmos compatibles con FIPS para garantizar que las claves de cifrado nunca se almacenan ni se envían a través de la conexión sin cifrar. La implementación de Microsoft 365 de la protección de datos en reposo de clientes no se desvía de la implementación predeterminada de BitLocker.
