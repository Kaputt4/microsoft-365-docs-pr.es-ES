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
description: Obtén información sobre cómo Office 365 cifrado de BitLocker, lo que reduce el potencial de robo de datos debido a la pérdida o robo de equipos y discos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 343a5966dc24954e98d7d31977aacbc09daaba11
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197574"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker y Administrador de claves distribuidas (DKM) para el cifrado

Los servidores de Microsoft usan BitLocker para cifrar las unidades de disco que contienen datos de clientes en reposo en el nivel de volumen. El cifrado de BitLocker es una característica de protección de datos integrada en Windows. BitLocker es una de las tecnologías usadas para protegerse contra amenazas en caso de que haya lapsos en otros procesos o controles (por ejemplo, control de acceso o reciclaje de hardware) que podrían llevar a alguien a obtener acceso físico a discos que contienen datos de clientes. En este caso, BitLocker elimina la posibilidad de robo o exposición de datos debido a equipos y discos perdidos, robados o desmantelados de forma inapropiada.

BitLocker se implementa con cifrado estándar de cifrado avanzado (AES) de 256 bits en discos que contienen datos de clientes en Exchange Online, SharePoint Online y Skype Empresarial. Los sectores de disco se cifran con una clave de cifrado de volumen completo (FVEK), que se cifra con la clave maestra de volumen (VMK), que a su vez está enlazada al Módulo de plataforma de confianza (TPM) en el servidor. La VMK protege directamente el FVEK y, por lo tanto, proteger la VMK se vuelve fundamental. En la siguiente figura se muestra un ejemplo de la cadena de protección de claves de BitLocker para un servidor determinado (en este caso, mediante un Exchange Online servidor).

En la tabla siguiente se describe la cadena de protección de claves de BitLocker para un servidor determinado (en este caso, un Exchange Online servidor).

| PROTECTOR DE TECLAS | GRANULARIDAD | ¿CÓMO SE GENERA? | ¿DÓNDE SE ALMACENA? | PROTECCIÓN |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Clave externa de AES de 256 bits | Por servidor | API de BitLocker | TPM o Secret Caja fuerte | Caja de seguridad /Control de acceso |
|  |  |  | Registro del servidor de buzones | TPM cifrado |
| Contraseña numérica de 48 dígitos | Por disco | API de BitLocker | Active Directory | Caja de seguridad /Control de acceso |
| Certificado X.509 como agente de recuperación de datos (DRA) también denominado Protector de clave pública | Entorno (por ejemplo, Exchange Online multitenant) | Microsoft CA | Sistema de compilación | Ningún usuario tiene la contraseña completa de la clave privada. La contraseña está bajo protección física. |


La administración de claves de BitLocker implica la administración de claves de recuperación que se usan para desbloquear o recuperar discos cifrados en un centro de datos de Microsoft. Microsoft 365 almacena las claves maestras en una unidad compartida protegida, a la que solo pueden acceder personas que se hayan sometido a un proceso de filtrado y aprobación. Las credenciales de las claves se almacenan en un repositorio protegido para los datos de control de acceso (lo que llamamos "almacén secreto"), lo que requiere un alto nivel de aprobaciones de elevación y administración para acceder mediante una herramienta de elevación de acceso justo a tiempo.

BitLocker admite claves que se dividen en dos categorías de administración:

- Claves administradas por BitLocker, que, en general, son de corta duración y están vinculadas a la vigencia de una instancia de sistema operativo instalada en un servidor o en un disco determinado. Estas claves se eliminan y restablecen durante la reinstalación del servidor o el formateo del disco.

- Claves de recuperación de BitLocker, que se administran fuera de BitLocker pero que se usan para el descifrado de disco. BitLocker usa claves de recuperación para el escenario en el que un sistema operativo se reinstala y los discos de datos cifrados ya existen. Los sondeos de supervisión de disponibilidad administrada también utilizan claves de recuperación en Exchange Online cuando un respondedor pueda tener que desbloquear un disco.

Los volúmenes protegidos con BitLocker se cifran con una clave de cifrado de volumen completo, que a su vez se cifra con una clave maestra de volumen. BitLocker usa algoritmos compatibles con FIPS para asegurarse de que las claves de cifrado nunca se almacenan o envían a través del cable de forma clara. La implementación por parte de Microsoft 365 de una protección de los datos de cliente en reposo no es distinta de la implementación por defecto de BitLocker.
