---
title: Cómo se controlan las actualizaciones en el Escritorio administrado de Microsoft
description: Mantener actualizados Microsoft Managed Desktop es un equilibrio entre velocidad y estabilidad.
keywords: Servicio de escritorio administrado de Microsoft, Microsoft 365, documentación
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871265"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Cómo se controlan las actualizaciones en el Escritorio administrado de Microsoft


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop se conecta a todos los dispositivos a una infraestructura basada en la nube moderna. Mantener Windows, Office, controladores, firmware y Microsoft Store para actualizaciones de la aplicación empresarial actualizado es un equilibrio entre velocidad y estabilidad. Suena de implementación se usarán para asegurarse de sistema operativo y las directivas se implementan de forma segura. 

## <a name="update-rings"></a>Suena de actualización

Microsoft Managed Desktop usa cuatro grupos de Azure AD para administrar las actualizaciones:

- Prueba: La llamada de prueba sólo está diseñado para la prueba y validación de los cambios realizados en el inquilino del cliente.  
- Primera: en primer lugar está pensada para ser un anillo anticipado de prueba con los usuarios más experimentados tech limitadas que están dispuestos a instalar software pronto y estar sujeto a algunas actualizaciones anteriores a la versión.
- Fast: El anillo fast es donde se esperaría un conjunto grande de usuarios.  El objetivo de esta llamada es para mantener los dispositivos actualizada y segura con un rápido ritmo de entrega de software.  
- Amplia: El anillo lento es un equilibrado roll conservador fuera de la calidad y la característica de actualizaciones.  Actualizaciones de calidad aún se entregan rápidamente ritmo, pero no inmediatamente. 

Las actualizaciones en el sistema de anillo se clasifican como calidad o actualizaciones de la característica:
- Actualizaciones de calidad incluyen crítico para la seguridad, y controlador.  Éstas son actualizaciones normalmente mensuales. 
- Característica actualizaciones contienen no sólo seguridad y las revisiones de calidad, pero también característica significativa adiciones y cambios; se publican dos veces al año. 

Cómo funciona la promoción de anillo:
- Microsoft Managed Desktop implementa una nueva actualización de característica o calidad según la programación especificada debajo.
- Durante la implementación, Microsoft Managed Desktop supervisa signos de error o cualquier otra alteración (a través de las señales de telemetría y nuestro sistema de soporte técnico del usuario final); Si se detecta alguno, de la implementación para todos los anillos actuales y futuros inmediatamente está en pausa.
    - Ejemplo: si se detecta un problema durante la implementación de una actualización de calidad para el primer tono de llamada, a continuación, en primer lugar, Fast y amplia se todos los pondrá en pausa hasta que se resuelve el problema.
    - Problemas de compatibilidad se pueden informar al archivar un vale en el portal de administración de TI administrado de escritorio de Microsoft.
- Actualizaciones de característica y calidad están en pausa por separado.  Pausa está en vigor para 35 días de forma predeterminada, pero puede reducirse o extendida dependiendo de si se corrigió el problema.
- Una vez que los anillos reactivar en pausa, se reanuda la implementación según la programación que aparece a continuación.
- Este proceso de promoción se aplica a las actualizaciones de la característica y calidad, aunque la escala de tiempo varía para cada uno.

<table>
<tr><th colspan="5">Suena y configuración de aplazamiento</th></tr>
<tr><th>Tipo de actualización</th><th>Llamada de prueba</th><th>Primera</th><th>Rápido</th><th>Amplia</th></tr>
<tr><td>Actualizaciones de calidad de sistema operativo</td><td>0 días</td><td>0 días</td><td>1 día</td><td>5 días</td></tr>
<tr><td>Actualizaciones de la característica de sistema operativo</td><td>Canal semestral (dirigidas) + 0 días</td><td>Canal semestral (dirigidas) + 30 días</td><td>Canal semestral (dirigidas) + 60 días</td><td>Canal semestral + 30 días</td></tr>
<tr><td>Controladores/firmware</td><td colspan="4">Sigue la programación para actualizaciones de calidad</td></tr>
<tr><td>Definición del antivirus</td><td colspan="4">Se actualizó con cada examen</td></tr>
<tr><td>Haga clic en más proactiva de Office para ejecutar</td><td colspan="4">Alinea con canal semestral</td></tr>
</table>


## <a name="windows-insider-program"></a>Programa de información confidencial de Windows

Escritorio administrado de Microsoft no es compatible con los dispositivos que forman parte del programa de especialista en Windows. Este programa se usa para validar el software de Windows de la versión preliminar y está pensado para que no sean de misión críticos dispositivos. Aunque esto es una iniciativa importante de Microsoft, no está pensada para una amplia implementación de entornos de producción. 

Todos los dispositivos que se encuentra con compilaciones de información confidencial de Windows se colocarán en el anillo de prueba y no se incluye para la actualización de los SLA.

## <a name="bandwidth-management"></a>Administración de ancho de banda

Optimización de entrega se usa para operativas todas las actualizaciones del sistema y el controlador. Minimiza el tamaño de descarga del servicio Windows Update (WU) de forma que busquen actualizaciones de elementos del mismo nivel dentro de la red corporativa.


