---
title: Solucionar problemas de Microsoft Defender para endpoint en Linux RHEL6
ms.reviewer: ''
description: Solucionar problemas de conectividad en la nube para Microsoft Defender para Endpoint en Linux
keywords: microsoft, defender, Microsoft Defender para endpoint, linux, nube, conectividad, comunicación
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 43a60d12883dc639c4ee5b831d305010cef58533
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2021
ms.locfileid: "61163643"
---
# <a name="troubleshoot-issues-for-microsoft-defender-for-endpoint-on-linux-rhel6"></a>Solucionar problemas de Microsoft Defender para endpoint en Linux RHEL6

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Plan 2 de Microsoft Defender para endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

En este artículo se proporcionan instrucciones sobre cómo solucionar problemas que puedan surgir con Microsoft Defender para Linux en Red Hat Linux 6 (RHEL 6) o posterior. 

Después de instalar el paquete (mdatp_XXX.XX.XX.XX.x86_64.rpm), lleve a cabo las acciones proporcionadas para comprobar que la instalación se ha realizado correctamente. 


## <a name="check-the-service-health"></a>Comprobar el estado del servicio

Use el siguiente comando para comprobar el estado del servicio:

```bash
mdatp health 
```

## <a name="verify-that-the-service-is-running"></a>Comprobar que el servicio se está ejecutando

Use el siguiente comando para comprobar que el servicio se está ejecutando:

```bash
service mdatp status 
```

Salida esperada: `mdatp start/running, process 4517`

## <a name="verify-the-distribution-and-kernel-version"></a>Comprobar la distribución y la versión del kernel
Las versiones de distribución y kernel deben estar en la lista admitida.

Use el siguiente comando para obtener la versión de distribución:

```bash
cat /etc/redhat-release (or /etc/system-release) 
```

Use el siguiente comando para obtener la versión del kernel:

```bash
uname -r
```
## <a name="check-if-mdatp-audisp-process-is-running"></a>Comprobar si se está ejecutando el proceso de mdatp audisp 
El resultado esperado es que el proceso se está ejecutando.

Use el siguiente comando para comprobar:

```bash
pidof mdatp_audisp_plugin 
```

## <a name="check-talpa-modules"></a>Comprobar módulos TALPA
Debe haber nueve módulos cargados. 

Use el siguiente comando para comprobar:

```bash
lsmod | grep talpa
```

Salida esperada: Habilitada

```bash
talpa_pedconnector       878  0 

talpa_pedevice          5189  2 talpa_pedconnector 

talpa_vfshook          32300  1 

talpa_vcdevice          4947  1 

talpa_syscall           9127  0 

talpa_core             90699  4 talpa_vfshook,talpa_vcdevice,talpa_syscall 

talpa_linux            29424  5 talpa_vfshook,talpa_vcdevice,talpa_syscall,talpa_core 

talpa_syscallhookprobe      882  0 

talpa_syscallhook      14987  2 talpa_vfshook,talpa_syscallhookprobe 
```


```bash
lsmod | grep talpa | wc -l 
```

Salida esperada: 9

## <a name="check-talpa-status"></a>Comprobar el estado de TALPA

```bash
cat /proc/sys/talpa/interceptors/VFSHookInterceptor/status 
```

Depurar archivos de registro (aparte de la agrupación "mdatp diagnostic create") 

```bash
/var/log/audit/audit.log 

/var/log/messages 

semanage fcontext -l > selinux.log 
```
 

Rendimiento y memoria 

```bash
top -p <wdavdaemon pid>      

pmap -x <wdavdaemon pid> 
```

Dónde `<wdavdaemon pid>` se puede encontrar con `pidof wdavdaemon` .

