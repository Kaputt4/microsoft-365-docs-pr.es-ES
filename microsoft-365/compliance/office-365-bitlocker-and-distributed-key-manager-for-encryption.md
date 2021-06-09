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
description: Obtenga información sobre cómo Office 365 usar BitLocker cifrado, lo que reduce el potencial de robo de datos debido a la pérdida o robo de equipos y discos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc329a053544ba6cf1753ae07caac642546cad11
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033628"
---
# <a name="bitlocker-and-distributed-key-manager-dkm-for-encryption"></a>BitLocker y Administrador de claves distribuidas (DKM) para el cifrado

Los servidores microsoft usan BitLocker para cifrar las unidades de disco que contienen datos del cliente en reposo en el nivel de volumen. BitLocker cifrado es una característica de protección de datos integrada en Windows. BitLocker es una de las tecnologías usadas para protegerse contra amenazas en caso de que haya lapsos en otros procesos o controles (por ejemplo, control de acceso o reciclaje de hardware) que podrían llevar a alguien a obtener acceso físico a discos que contienen datos de clientes. En este caso, BitLocker elimina la posibilidad de robo o exposición de datos debido a la pérdida, robo o retirada inadecuada de discos y equipos.

BitLocker se implementa con cifrado de 256 bits estándar de cifrado avanzado (AES) en discos que contienen datos de clientes en Exchange Online, SharePoint Online y Skype Empresarial. Los sectores de disco se cifran con una clave de cifrado de volumen completo (FVEK), que se cifra con la clave maestra de volumen (VMK), que a su vez está enlazada al Módulo de plataforma de confianza (TPM) en el servidor. La VMK protege directamente el FVEK y, por lo tanto, proteger la VMK se vuelve fundamental. En la figura siguiente se muestra un ejemplo de la cadena de protección de claves BitLocker para un servidor determinado (en este caso, mediante un Exchange Online servidor).

En la tabla siguiente se describe la BitLocker de protección de claves de un servidor determinado (en este caso, un Exchange Online servidor).

| PROTECTOR DE TECLAS | GRANULARIDAD | ¿CÓMO SE GENERA? | ¿DÓNDE SE ALMACENA? | PROTECCIÓN |
|--------------------------------------------------------------------------------|-------------------------------------------------|----------------|-------------------------|--------------------------------------------------------------------------------------------------|
| Clave externa de AES de 256 bits | Por servidor | BitLocker API | TPM o Secret Caja fuerte | Caja de seguridad /Control de acceso |
|  |  |  | Registro del servidor de buzones | TPM cifrado |
| Contraseña numérica de 48 dígitos | Por disco | BitLocker API | Active Directory | Caja de seguridad /Control de acceso |
| Certificado X.509 como agente de recuperación de datos (DRA) también denominado Protector de clave pública | Entorno (por ejemplo, Exchange Online multitenant) | Microsoft CA | Sistema de compilación | Ningún usuario tiene la contraseña completa de la clave privada. La contraseña está bajo protección física. |


BitLocker administración de claves implica la administración de claves de recuperación que se usan para desbloquear o recuperar discos cifrados en un centro de datos de Microsoft. Microsoft 365 almacena las claves maestras en un recurso compartido protegido, al que solo pueden acceder las personas que se han proyectado y aprobado. Las credenciales de las claves se almacenan en un repositorio protegido para los datos de control de acceso (lo que llamamos "almacén secreto"), lo que requiere un alto nivel de aprobaciones de elevación y administración para acceder mediante una herramienta de elevación de acceso justo a tiempo.

BitLocker admite claves que se encuensen en dos categorías de administración:

- BitLocker claves administradas por el usuario, que generalmente son de corta duración y están vinculadas a la duración de una instancia del sistema operativo instalada en un servidor o en un disco determinado. Estas claves se eliminan y restablecen durante la reinstalación del servidor o el formato de disco.

- BitLocker claves de recuperación, que se administran fuera de BitLocker pero que se usan para el descifrado de disco. BitLocker claves de recuperación para el escenario en el que se reinstala un sistema operativo y los discos de datos cifrados ya existen. Los sondeos de supervisión de disponibilidad administrada también usan las claves de recuperación Exchange Online donde un respondedor puede necesitar desbloquear un disco.

BitLocker los volúmenes protegidos por volumen se cifran con una clave de cifrado de volumen completo, que a su vez se cifra con una clave maestra de volumen. BitLocker algoritmos compatibles con FIPS para asegurarse de que las claves de cifrado nunca se almacenan ni se envían a través del cable de forma clara. La Microsoft 365 de protección de datos en reposo del cliente no se desvía de la implementación BitLocker cliente.
