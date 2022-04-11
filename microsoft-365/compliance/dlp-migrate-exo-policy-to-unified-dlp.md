---
title: Migrar directivas de prevención de pérdida de datos de Exchange Online al Centro de cumplimiento
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Obtenga información sobre cómo planear y migrar las directivas de prevención de pérdida de datos en línea de Exchange a Microsoft 365 DLP.
ms.openlocfilehash: c6b941a0dd1f66e2f44494fded9ba47e8c3d7230
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760875"
---
# <a name="migrate-exchange-online-data-loss-prevention-policies-to-compliance-center"></a>Migrar directivas de prevención de pérdida de datos de Exchange Online al Centro de cumplimiento

[Exchange Online directivas de prevención de pérdida de datos (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) están en desuso. [La funcionalidad DLP mucho más enriquecida](dlp-learn-about-dlp.md), incluida Exchange Online DLP, se ofrece en el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/datalossprevention?viewid=policies). Puede usar el Asistente para migración de directivas DLP para ayudarle a llevar las directivas DLP de Exchange Online al Centro de cumplimiento donde las administrará.

El asistente para migración funciona leyendo la configuración de las directivas DLP en Exchange y, a continuación, creando directivas duplicadas en el Centro de cumplimiento. De forma predeterminada, el asistente crea las nuevas versiones de las directivas en modo **de prueba** , para que pueda ver qué impacto tendrían en el entorno sin aplicar ninguna de las acciones. Una vez que esté listo para realizar la transición completa a las versiones del Centro de cumplimiento, **_debe_**:

1. Desactive o elimine la directiva de origen en el Centro de administración de Exchange (EAC).
1. Edite la versión del Centro de cumplimiento de la directiva y cambie su estado de **Prueba** a **Aplicar**.

> [!WARNING]
> Si no elimina ni desactiva la directiva de origen en el EAC antes de establecer la versión del Centro de cumplimiento en **Aplicar** ambos conjuntos de directivas intentará aplicar acciones y recibirá eventos duplicados. **_Se trata de una configuración no admitida._**

El asistente para migración solo migra directivas EXO y reglas de flujo de correo asociadas. No se migran reglas de flujo de correo Exchange independientes.

## <a name="migration-workflow"></a>Flujo de trabajo de migración

Hay cuatro fases para migrar directivas DLP de Exchange a la consola de administración dlp unificada en el Centro de cumplimiento.

1. Preparación para la migración
    1. Evalúe y compare las directivas DLP de Exchange Online (EXO) y las directivas DLP del Centro de cumplimiento para obtener una funcionalidad duplicada.
    1. Decida qué directivas DLP de EXO desea traer exactamente tal cual, puede usar el asistente para migrarlas.
    1. Decida qué directivas DLP de EXO desea consolidar y consolidarlas en el centro de administración de Exchange y, a continuación, use el Asistente para migración para traerlas al Centro de cumplimiento.
1. Realización de la migración: use el asistente
1. Pruebas y validación: examinar los resultados
1. Activación de las directivas migradas

## <a name="before-you-begin"></a>Antes de empezar

### <a name="licensing-and-versions"></a>Licencias y versiones

Antes de empezar a migrar directivas DLP, debe confirmar la [suscripción Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) y los complementos.

Para acceder y usar el Asistente para migración de directivas, debe tener una de estas suscripciones o complementos.

- Microsoft 365 E3
- Microsoft 365 E5
- Microsoft 365 A5 (EDU)
- Cumplimiento de Microsoft 365 E5
- Cumplimiento de Microsoft 365 A5
- Gobierno y protección de información de Microsoft 365 E5
- Gobierno y protección de información de Microsoft 365 A5

Para obtener una lista detallada de los requisitos de licencias DLP, consulte [Microsoft 365 Guía de licencias para el cumplimiento de la seguridad & y la prevención de pérdida de datos](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

### <a name="permissions"></a>Permisos

La cuenta que use para ejecutar el Asistente para migración debe tener acceso a la página DLP de Exchange Consola de administración y a la consola DLP unificada en el Centro de cumplimiento.

## <a name="prepare-for-migration"></a>Preparación para la migración

1. Si no está familiarizado con DLP, la consola DLP del Centro de cumplimiento o la consola DLP del Centro de administración de Exchange, debe familiarizarse antes de intentar una migración de directiva.
    1. [Exchange Online directivas de prevención de pérdida de datos (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    1. [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
    1. [Creación, prueba y optimización de una directiva DLP](create-test-tune-dlp-policy.md)
1. Evalúe las directivas Exchange DLP y del Centro de cumplimiento haciendo estas preguntas:

|Pregunta|Action|Procedimiento de migración|
|---|---|---|
|¿Sigue siendo necesaria la directiva?|Si no es así, elimínelo o desactívelo.|no migrar|
|¿Se superpone con cualquier otra directiva DLP de Exchange o centro de cumplimiento?|Si es así, ¿puede consolidar las directivas superpuestas?|- Si se superpone con otra directiva de Exchange, cree manualmente la directiva DLP consolidada en el centro de administración de Exchange y, a continuación, use el asistente para migración. </br> - Si se superpone con una directiva del Centro de cumplimiento existente, puede modificar la directiva del Centro de cumplimiento existente para que coincida, no migrar la versión Exchange|
|¿La directiva DLP de Exchange tiene un ámbito estricto y tiene condiciones, acciones, inclusiones y exclusiones bien definidas?|Si es así, es un buen candidato para migrar con el asistente, tome nota de la directiva para que recuerde volver a eliminarla más adelante.|migración con el asistente|

## <a name="migration"></a>Migración

Una vez que haya evaluado todas las directivas DLP de Exchange y del Centro de cumplimiento por necesidad y compatibilidad, puede usar el Asistente para migración.

1. Abra la consola DLP del [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/datalossprevention?viewid=policies).
2. Si hay Exchange directivas DLP que se pueden migrar, aparecerá un banner en la parte superior de la página para informarle.
3. Elija **Migrar directivas** en el banner para abrir el Asistente para migración. Se muestran todas las directivas DLP de Exchange. Las directivas migradas anteriormente no se pueden seleccionar.
4. Seleccione las directivas que desea migrar. Puede migrarlos individualmente o en grupos mediante un enfoque por fases o todo a la vez. Seleccione **Siguiente**.
5. Revise el panel flotante para ver si hay advertencias o mensajes. Resuelva los problemas antes de continuar.
6. Seleccione el modo en el que desea crear la nueva directiva del Centro de cumplimiento, **Activo**, **Prueba** o **Deshabilitado**.  El valor predeterminado es **Test**. Seleccione **Siguiente**.
7. Si lo desea, puede crear más directivas basadas en las directivas DLP Exchange para otras ubicaciones DLP unificadas. Esto dará lugar a una nueva directiva DLP unificada para la directiva de Exchange migrada y una nueva directiva DLP unificada para cualquier otra ubicación que elija aquí.

   > [!IMPORTANT]
   > Cualquier Exchange condiciones y acciones de directiva DLP que no sean compatibles con otras ubicaciones DLP, como Dispositivos, SharePoint, OneDrive, Local, MCAS o Teams mensajes de chat y canal se quitarán de la directiva adicional. Además, hay un trabajo previo que debe realizarse para las otras ubicaciones. Vea:
   >
   > - [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
   > - [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)
   > - [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
   > - [Obtenga más información sobre el examinador de prevención de pérdida de datos locales de Microsoft 365](dlp-on-premises-scanner-learn.md#learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner)
   > - [Introducción al examinador de prevención de pérdida de datos en el entorno local](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)
   > - [Usar el examinador de prevención de pérdida de datos locales de Microsoft 365](dlp-on-premises-scanner-use.md#use-the-microsoft-365-data-loss-prevention-on-premises-scanner)
   > - [Uso de directivas de prevención de pérdida de datos para aplicaciones en la nube que no son de Microsoft](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)

8. Revise la configuración de sesión del Asistente para migración. Seleccione **Siguiente**.
9. Revise el informe de migración. Preste atención a los errores que impliquen Exchange reglas de flujo de correo. Puede corregirlas y volver a migrar las directivas asociadas.

Las directivas migradas aparecerán ahora en la lista de directivas DLP en la consola DLP del Centro de cumplimiento.

## <a name="common-errors-and-mitigation"></a>Errores comunes y mitigación

|Mensaje de error|Reason|Pasos de mitigación o recomendados|
|---|---|---|
|Ya existe una directiva de `Dlp`cumplimiento con el nombre `<Name of the policy>` en escenarios .|Es probable que esta migración de directiva se haya realizado anteriormente y, a continuación, se vuelva a tentar en la misma sesión.|Actualice la sesión para actualizar la lista de directivas disponibles para la migración. Todas las directivas migradas anteriormente deben estar en el `Already migrated` estado .|
|Ya existe una directiva de `Hold`cumplimiento con el nombre `<Name of the policy>` en escenarios .|Existe una directiva de retención con el mismo nombre en el mismo inquilino.|: cambie el nombre de la directiva DLP en EAC a otro nombre. </br> : vuelva a intentar la migración de la directiva afectada.|
|`DLP-group@contoso.com` no se puede usar como valor para la condición Shared By porque es un grupo de distribución o un grupo de seguridad habilitado para correo. Use Shared by Member of predicate (Compartido por miembro del predicado) para detectar las actividades de los miembros de determinados grupos.|Las reglas de transporte permiten que los grupos se usen en la `sender is` condición, pero DLP unificado no lo permite.|Actualice la regla de transporte para quitar todas las direcciones de correo electrónico del grupo de la `sender is` condición y agregar el grupo a la `sender is a member of` condición si es necesario. Reintentar la migración de la directiva afectada|
|No se encontró el destinatario `DLP-group@contoso.com`. Si se acaba de crear, vuelva a intentar la operación después de algún tiempo. Si se ha eliminado o ha expirado, restablezca con valores válidos e inténtelo de nuevo.|Es probable que la dirección de grupo usada en `sender is a member of` o `recipient is a member of` la condición haya expirado o no sea válida.|- Quite o reemplace todas las direcciones de correo electrónico de grupo no válidas de la regla de transporte en Exchange centro de administración. </br> : vuelva a intentar la migración de la directiva afectada.|
|El valor especificado en `FromMemberOf` el predicado debe ser un grupo de seguridad habilitado para correo.|Las reglas de transporte permiten que los usuarios individuales se usen en la `sender is a member of` condición, pero DLP unificado no lo permite.|- Actualice la regla de transporte para quitar todas las direcciones de correo electrónico de usuario individuales de la `sender is a member of` condición y agregar los usuarios a la `sender is` condición si es necesario. </br> : vuelva a intentar la migración de la directiva afectada.|
|El valor especificado en `SentToMemberOf` el predicado debe ser un grupo de seguridad habilitado para correo.|Las reglas de transporte permiten que los usuarios individuales se usen bajo la `recipient is a member of` condición, pero DLP unificado no lo permite.|- Actualice la regla de transporte para quitar todas las direcciones de correo electrónico de usuario individuales de la `recipient is a member of` condición y agregar los usuarios a la `recipient is` condición si es necesario. </br> : vuelva a intentar la migración de la directiva afectada.|
|El uso del `<Name of condition>` parámetro solo se admite para Exchange. Quite este parámetro o active solo Exchange ubicación.|Es probable que exista otra directiva con el mismo nombre en el Centro de cumplimiento con otras ubicaciones como SPO/ODB/Teams para las que no se admite la condición mencionada.|Cambie el nombre de la directiva DLP en Exchange centro de administración y vuelva a intentar la migración.|

## <a name="testing-and-validation---prateek-and-aakash-to-provide-a-list-of-supported-predicates-and-known-issues-before-publishing--"></a>Pruebas y validación <!--PRATEEK AND AAKASH TO PROVIDE A LIST OF SUPPORTED PREDICATES AND KNOWN ISSUES BEFORE PUBLISHING-->

Pruebe y revise las directivas.

1. Siga los procedimientos [de prueba de una directiva DLP](create-test-tune-dlp-policy.md#test-a-dlp-policy) .
2. Revise los eventos creados por la directiva en el [Explorador de actividad](data-classification-activity-explorer.md).

## <a name="review-the-policy-matches-between-exchange-admin-center-dlp-and-microsoft-365-unified-dlp"></a>Revise las coincidencias de directiva entre Exchange DLP del Centro de administración y Microsoft 365 DLP unificada

Para asegurarse de que las directivas migradas se comportan según lo esperado, puede exportar los informes de ambos centros de administración y realizar una comparación de las coincidencias de directiva.

1. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
2. Exporte el [informe DLP de EAC](/powershell/module/exchange/get-maildetaildlppolicyreport). Puede copiar este cmdlet e insertar los valores adecuados:

   ```powershell
   Get-MailDetailDlpPolicyReport -StartDate <dd/mm/yyyy -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, MessageId, DlpPolicy, TransportRule -Unique | Export-CSV <"C:\path\filename.csv">
   ```

3. Exporte el [informe DLP unificado](/powershell/module/exchange/get-dlpdetailreport). Puede copiar este cmdlet e insertar los valores adecuados:

   ```powershell
   Get-DlpDetailReport -StartDate <dd/mm/yyyy> -EndDate <dd/mm/yyyy> -PageSize 5000 | select Date, Location, DlpCompliancePolicy, DlpComplianceRule -Unique | Export-CSV <"C:\path\filename.csv">
   ```

## <a name="activate-your-migrated-policies"></a>Activación de las directivas migradas

Una vez que esté satisfecho con el funcionamiento de las directivas migradas, puede establecerlas en **Aplicar**.

1. Abra la consola DLP del Centro de administración de Exchange.
2. Desactive o elimine la directiva de origen.
3. Abra la consola DLP del [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com/datalossprevention?viewid=policies) y seleccione la directiva que desea activar para editarla.
4. Cambie el estado a **Activado**.

## <a name="related-articles"></a>Artículos relacionados

- [Exchange Online directivas de prevención de pérdida de datos (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Introducción al explorador de actividad](data-classification-activity-explorer.md)
- [Creación, prueba y optimización de una directiva DLP](create-test-tune-dlp-policy.md)
- [Crear una directiva DLP desde una plantilla](create-a-dlp-policy-from-a-template.md)
- [Exchange Online directivas de prevención de pérdida de datos (DLP)](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
