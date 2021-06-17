---
title: Ver eventos de la reducción de la superficie expuesta a ataques
description: Importar vistas personalizadas para ver eventos de reducción de superficie de ataque.
keywords: vista de eventos, protección contra vulnerabilidades, auditoría, revisión, eventos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f8de3d8b2d7c07f8d783ecbe85b7e4a9c612aae5
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985479"
---
# <a name="view-attack-surface-reduction-events"></a>Ver eventos de la reducción de la superficie expuesta a ataques

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Microsoft Defender para endpoint? [Registrarse para obtener una versión de prueba gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink).

Revisa los eventos de reducción de superficie de ataque en el Visor de eventos para supervisar qué reglas o configuraciones funcionan. También puede determinar si alguna configuración es demasiado "ruidosa" o si afecta al flujo de trabajo diario.

Revisar los eventos es útil al evaluar las características. Puede habilitar el modo de auditoría para las características o la configuración y, a continuación, revisar lo que hubiera ocurrido si estuvieran totalmente habilitadas.

En este artículo se enumeran todos los eventos, su característica o configuración asociadas y se describe cómo crear vistas personalizadas para filtrar a eventos específicos.

Obtenga informes detallados sobre eventos, bloques y advertencias como parte de Seguridad de Windows si tiene una suscripción a E5 y usa [Microsoft Defender para Endpoint](microsoft-defender-endpoint.md).

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Usar vistas personalizadas para revisar las capacidades de reducción de superficie de ataque

Cree vistas personalizadas en el Windows de eventos para ver solo eventos para funciones y configuraciones específicas. La forma más sencilla es importar una vista personalizada como un archivo XML. Puede copiar el XML directamente desde esta página.

También puede navegar manualmente hasta el área de eventos que corresponde a la característica.

### <a name="import-an-existing-xml-custom-view"></a>Importar una vista personalizada XML existente

1. Cree un archivo .txt y copie el XML de la vista personalizada que desea usar en el .txt archivo. Haga esto para cada una de las vistas personalizadas que desee usar. Cambie el nombre de los archivos de la siguiente manera (asegúrese de cambiar el tipo de .txt a .xml):
    - Vista personalizada de eventos de acceso a carpetas *controladas:cfa-events.xml*
    - Vista personalizada de eventos de protección contra *vulnerabilidades:ep-events.xml*
    - Vista personalizada de eventos de reducción de superficie *de ataque:asr-events.xml*
    - Vista personalizada de eventos de *red/protección:np-events.xml*

2. Escriba **el visor de** eventos en el menú Inicio y abra el Visor de **eventos**.

3. Seleccionar **acción**  >  **Importar vista personalizada...**

  > [!div class="mx-imgBorder"]
  > ![Animación resaltando Importar vista personalizada a la izquierda de la ventana Visor par](images/events-import.gif)

4. Navegue hasta donde extrajo el archivo XML para la vista personalizada que desee y selecciónelo.

5. Seleccione **Abrir**.

6. Creará una vista personalizada que filtra para mostrar solo los eventos relacionados con esa característica.

### <a name="copy-the-xml-directly"></a>Copiar el XML directamente

1. Escriba **el visor** de eventos en el menú Inicio y abra el Windows de **eventos**.

2. En el panel izquierdo, en **Acciones,** seleccione **Crear vista personalizada...**

  > [!div class="mx-imgBorder"]
  > ![Animación que resalta la opción crear vista personalizada en la ventana Visor de eventos](images/events-create.gif)

3. Vaya a la pestaña XML y seleccione **Editar consulta manualmente.** Verá una advertencia de que no puede editar  la consulta mediante la pestaña Filtro si usa la opción XML. Seleccione **Sí**.

4. Pegue el código XML de la característica desde la que desea filtrar los eventos en la sección XML.

5. Seleccione **Aceptar**. Especifique un nombre para el filtro. Esto crea una vista personalizada que filtra para mostrar solo los eventos relacionados con esa característica.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML para eventos de regla de reducción de superficie de ataque

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>XML para eventos de acceso controlado a carpetas

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>XML para eventos de protección contra vulnerabilidades

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>XML para eventos de protección de red

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>Lista de eventos de reducción de superficie de ataque

Todos los eventos de reducción de superficie de ataque se encuentran en Registros de aplicaciones y **servicios > Microsoft > Windows** y, a continuación, la carpeta o el proveedor como se muestra en la tabla siguiente.

Puede tener acceso a estos eventos en Windows visor de eventos:

1. Abra el **menú Inicio** y escriba visor **de eventos** y, a continuación, seleccione el resultado del **Visor de** eventos.
2. Expanda Registros de aplicaciones y **servicios > Microsoft > Windows** y, a continuación, vaya a la carpeta que aparece en **Proveedor/origen** en la tabla siguiente.
3. Haga doble clic en el sub elemento para ver los eventos. Desplácese por los eventos para encontrar el que está buscando.

   ![Animación que muestra con el Visor de eventos](images/event-viewer.gif)

Característica | Proveedor/origen | Id. de evento | Descripción
:-|:-|:-:|:-
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 1 | Auditoría de ACG
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 2 | Aplicación de ACG
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 3 | No permitir la auditoría de procesos secundarios
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 4  | No permitir el bloqueo de procesos secundarios
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 5  | Bloquear la auditoría de imágenes de baja integridad
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 6  | Bloquear bloque de imágenes de baja integridad
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 7  | Bloquear la auditoría de imágenes remotas
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 8  | Bloquear bloque de imágenes remotas
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 9  | Deshabilitar la auditoría de llamadas del sistema win32k
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 10 | Deshabilitar el bloqueo de llamadas del sistema win32k
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 11 | Auditoría de protección de integridad de código
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 12  | Bloqueo de protección de integridad de código
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 13 | Auditoría del EAF
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 14  | Aplicación de EAF
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 15 | Auditoría de EAF+
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 16  | Aplicación de EAF+
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 17  | Auditoría de IAF
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 18  | IAF enforce
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 19 | Auditoría de StackPivot de ROP
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 20 | Aplicación de StackPivot de ROP
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) |  21 | Auditoría rop CallerCheck
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 22 | Exigir ROP CallerCheck
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 23 | Auditoría de Rop SimExec
Protección contra vulnerabilidades de seguridad | Security-Mitigations (modo kernel/modo de usuario) | 24 | Rop SimExec enforce
Protección contra vulnerabilidades de seguridad | WER-Diagnostics | 5  | Bloque de CFG
Protección contra vulnerabilidades de seguridad | Win32K (operativo) | 260 | Fuente que no es de confianza
Protección de red | Windows Defender (operativo) | 5007 | Evento cuando se cambia la configuración
Protección de red | Windows Defender (operativo) | 1125 | Evento cuando la protección de red se dispara en modo auditoría
Protección de red | Windows Defender (operativo) | 1126 | Evento cuando la protección de red se dispara en modo de bloqueo
Acceso controlado a carpetas | Windows Defender (operativo) | 5007 | Evento cuando se cambia la configuración
Acceso controlado a carpetas | Windows Defender (operativo) | 1124 | Evento de acceso a carpetas controladas auditadas
Acceso controlado a carpetas | Windows Defender (operativo) | 1123 | Evento de acceso a carpetas controladas bloqueadas
Acceso controlado a carpetas | Windows Defender (operativo) | 1127 | Evento de bloque de escritura del sector de acceso controlado a carpetas bloqueadas
Acceso controlado a carpetas | Windows Defender (operativo) | 1128 | Evento de bloque de escritura auditado del sector de acceso controlado a carpetas
Reducción de la superficie expuesta a ataques | Windows Defender (operativo) | 5007 | Evento cuando se cambia la configuración
Reducción de la superficie expuesta a ataques | Windows Defender (operativo) | 1122 | Evento cuando la regla se dispara en modo auditoría
Reducción de la superficie expuesta a ataques | Windows Defender (operativo) | 1121 | Evento cuando la regla se dispara en modo bloque
