---
title: Analizador de configuración de cumplimiento de Microsoft para el Administrador de cumplimiento
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo usar el Analizador de configuración de cumplimiento de Microsoft para ponerse en marcha rápidamente con Microsoft Purview Compliance Manager.
ms.openlocfilehash: a973412c2d40993b47343273675cee3922b57cdf
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66012822"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Analizador de configuración de cumplimiento de Microsoft para el Administrador de cumplimiento (versión preliminar)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

**En este artículo:** Obtenga información sobre cómo instalar y ejecutar la herramienta Analizador de configuración de cumplimiento de Microsoft para empezar a trabajar rápidamente con Microsoft Compliance Manager.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Introducción a Microsoft Compliance Configuration Analyzer (MCCA) (versión preliminar)

Microsoft Compliance Configuration Analyzer (MCCA) es una herramienta de versión preliminar que puede ayudarle a empezar a trabajar con [Microsoft Purview Compliance Manager](compliance-manager.md). MCCA es una utilidad basada en PowerShell que capturará las configuraciones actuales de su organización y las validará con Microsoft 365 procedimientos recomendados. Estos procedimientos recomendados se basan en un conjunto de controles que incluyen normas clave y estándares para la protección de datos y la gobernanza de datos.

MCCA puede ayudarle a ver rápidamente qué acciones de mejora en el Administrador de cumplimiento se aplican a su entorno de Microsoft 365 actual. Cada acción identificada por MCCA le proporcionará recomendaciones para la implementación, con vínculos directos al Administrador de cumplimiento y la solución aplicable para empezar a tomar medidas correctivas.

Un recurso adicional para comprender MCCA es visitar las [instrucciones léame sobre GitHub](https://github.com/OfficeDev/MCCA#overview). En esta página se proporciona información detallada sobre los requisitos previos y se proporcionan instrucciones de instalación completas. No necesita una cuenta de GitHub para acceder a esta página.

**Disponibilidad**: MCCA está disponible para todas las organizaciones con licencias de Office 365 y Microsoft 365 y clientes de Community (GCC) moderados, GCC altos y del Departamento de Defensa (DoD) del Gobierno de EE. UU.

## <a name="install-mcca-and-run-a-report"></a>Instalación de MCCA y ejecución de un informe

Puede instalar la herramienta MCCA mediante Windows PowerShell. Una vez que descargue e instale la herramienta, no es necesario repetir esos pasos para ejecutar informes. Cada vez que abra MCCA, le pedirá sus credenciales de inicio de sesión y generará un nuevo informe actualizado.

### <a name="step-1-install-the-exchange-online-powershell-v2-module"></a>Paso 1: Instalar el módulo Exchange Online PowerShell V2

Para empezar, necesitará el módulo de PowerShell Exchange Online (versión 2.0.3 o posterior) que está disponible en la galería de PowerShell. Para obtener instrucciones de instalación, consulte [Instalación y mantenimiento del módulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

### <a name="step-2-install-mcca"></a>Paso 2: Instalar MCCA

Para instalar MCCA, empiece por usar PowerShell en modo de administrador. Siga estos pasos:

1. Seleccione el botón **inicio** Windows.
1. Escriba **PowerShell**, haga clic con el botón derecho en **Windows PowerShell** y, a continuación, seleccione **Ejecutar como administrador**.
1. En el símbolo del sistema, escriba lo siguiente:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

### <a name="step-3-run-a-report"></a>Paso 3: Ejecución de un informe

Después de instalar MCCA, puede ejecutar MCCA y generar un informe. Para ejecutar un informe:

1. Abrir PowerShell
2. Ejecute el cmdlet :

    ```powershell
    Get-MCCAReport
    ```

    Si es un cliente de GCC High, deberá proporcionar un parámetro de entrada adicional para ejecutar el informe:

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. Una vez que se ejecuta MCCA, realiza una comprobación de versión inicial y solicita credenciales. En el símbolo del sistema De entrada del nombre de usuario, inicie sesión con la dirección de correo electrónico de la cuenta de Microsoft 365 ([vea los roles aptos para crear informes](#role-based-reporting)). A continuación, escriba la contraseña en el símbolo del sistema de contraseña.

El informe tardará aproximadamente entre 2 y 5 minutos en generarse. Cuando haya terminado, se abrirá una ventana del explorador y mostrará el informe HTML. Cada vez que ejecute la herramienta, le pedirá sus credenciales y generará un nuevo informe. Este informe se almacena localmente en el directorio C: \ Users \ *username* \ AppData \ Local \ Microsoft \ MCCA.

Puede acceder a los informes generados anteriormente desde este directorio.

## <a name="understanding-your-report"></a>Descripción del informe

El informe refleja los datos en función de la fecha y hora en que se generó. En la sección superior se proporcionan detalles sobre cuándo se generó, el nombre de la organización y el identificador de inquilino.

### <a name="geolocation-based-reporting"></a>Informes basados en geolocalización

En la sección **Nota** se muestra que el informe se personaliza en función de la ubicación geográfica del inquilino. Recomendaciones que aparecen en la herramienta será específica de su país o región.

La selección de geolocalización se usa para evaluar los tipos de información confidencial (SIT) que son relevantes para esa geolocalización y generar un informe que se alinee con su país o región. Elija geolocalizaciones en función de los datos que tenga en el inquilino.

Para cambiar la información de ubicación del informe, debe proporcionar un parámetro de entrada de geolocalización (-Geo). Puede elegir una o varias geolocalizaciones aplicables para el inquilino.

Siga estas instrucciones para ejecutar un informe en función de una ubicación específica:

1. Abrir PowerShell
2. Para especificar una región determinada, ejecutará un cmdlet con los números de la tabla siguiente que corresponden al país o región. Escriba varios números separándolos con una coma. Por ejemplo, el siguiente cmdlet ejecutará un informe personalizado para Asia-Pacific y Japón:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```

  | Input |  País o región |
  | :------------- | :------------: |
  | 1 | Asia-Pacífico |
  | 2 | Australia |
  | 3 | Canadá |
  | 4  | Europa (excepto Francia) / Oriente Medio / África |
  | 5  | Francia |
  | 6  | India |
  | 7  | Japón |
  | 8  | Corea |
  | 9  | Norteamérica (excepto Canadá) |
  | 10  | Sudamérica |
  | 11  | Sudáfrica |
  | 12  | Suiza |
  | 13 | Emiratos Árabes Unidos |
  | 14  | Reino Unido |

  > [!NOTE]
  > El informe siempre incluirá tipos de información confidencial internacional compatibles con MCCA, como el código SWIFT, el número de tarjeta de crédito, etc.

### <a name="role-based-reporting"></a>Informes basados en roles

El informe también se personalizará en función de su rol.

En la tabla siguiente se muestran los roles que tienen acceso a las secciones del informe. Es posible que otros roles de la organización (que no se enumeran en la tabla siguiente) no puedan ejecutar la herramienta, o que puedan ejecutar la herramienta y tener acceso limitado a la información en el informe final.

![MCCA: roles.](../media/compliance-manager-mcca-roles.png "Roles de MCCA")

Excepciones:

1. Los usuarios no podrán generar un informe para ip aparte de la sección "Uso de IRM para Exchange Online".
2. Los usuarios podrán generar un informe para ip aparte de la sección "Usar IRM para Exchange Online".
3. Los usuarios podrán generar un informe para ip aparte de la sección "Habilitar el cumplimiento de comunicaciones en O365".
4. Los usuarios no podrán generar un informe para ip aparte de la sección "Habilitar auditoría en Office 365".
5. Los usuarios podrán generar un informe para ip aparte de la sección "Habilitar auditoría en Office 365".

### <a name="solutions-summary-section"></a>Sección resumen de soluciones

La sección **Resumen de soluciones** del informe proporciona información general sobre las acciones de mejora que su organización puede realizar en el Administrador de cumplimiento para ayudar a mejorar la posición de cumplimiento.

![MCCA: resumen de soluciones.](../media/compliance-manager-mcca-solutions.png "Pantalla de resumen de soluciones de MCCA")

MCCA evalúa las configuraciones actuales en comparación con las acciones de mejora recomendadas en el Administrador de cumplimiento. En esta sección se mostrará cualquier acción de mejora identificada por la herramienta MCCA como necesaria.

Junto a cada solución de Microsoft hay cuadros codificados por colores que indican el número de elementos que corresponden a las acciones de mejora en el Administrador de cumplimiento. Las acciones se dividen en tres estados de estado:

- **Aceptar**: las acciones que cumplen las condiciones recomendadas y no necesitan atención en este momento
- **Mejora**: acciones que necesitan atención
- **Recomendación**: acciones que no necesitan atención, pero para las que se recomiendan procedimientos recomendados

Seleccione un cuadro para ver mejoras y recomendaciones.

#### <a name="items-with-the-improvement-status"></a>Elementos con el estado De mejora

Seleccione la lista desplegable situada junto a la etiqueta **Mejora** a la derecha de la acción de mejora. Verá un resumen rápido y detalles sobre la configuración actual y las acciones de mejora recomendadas. El resumen incluye vínculos directos al Administrador de cumplimiento, la solución aplicable en el portal de cumplimiento de Microsoft Purview y la documentación pertinente.

Al hacer clic en el vínculo Administrador de cumplimiento, se le lleva a una vista filtrada de todas las acciones de mejora dentro de esa solución que aún no ha implementado. Desde allí, puede ver el número de puntos que puede lograr para aumentar la [puntuación de cumplimiento](compliance-score-calculation.md) y las evaluaciones a las que se aplican, así como las regulaciones y certificaciones aplicables.

Para DLP, hay un botón **Script de corrección** que proporciona un script de PowerShell generado previamente en función de lo recomendado. Puede copiarlo y pegarlo directamente en la consola de PowerShell. Creará una directiva DLP en modo de prueba.

#### <a name="items-with-recommendation-status"></a>Elementos con estado de recomendación

Seleccione la lista desplegable situada junto a la etiqueta **Recomendación** a la derecha de la acción de mejora. Verá un resumen del entorno de Microsoft 365 actual de la organización relacionado con la acción de mejora, junto con los procedimientos recomendados.

## <a name="resources"></a>Recursos

Para obtener información más detallada sobre cómo instalar, configurar y usar MCCA, consulte [las instrucciones léame en GitHub](https://github.com/OfficeDev/MCCA#overview) (no se requiere ninguna cuenta de GitHub).

Para obtener más información sobre Windows PowerShell, comience en Uso de [la documentación de PowerShell](/powershell/scripting/how-to-use-docs). Consulte también [Inicio de Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell).
