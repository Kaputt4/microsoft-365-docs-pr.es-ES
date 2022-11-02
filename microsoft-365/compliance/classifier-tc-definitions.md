---
title: Definiciones de clasificadores entrenables
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- purview-compliance
- tier2
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: Esta es una lista de todos los clasificadores entrenables, sus definiciones y todos los tipos de archivo que buscan para encontrar información confidencial.
ms.openlocfilehash: 91f4350250adf5f2bd20bc67183f183539887a6c
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68814063"
---
# <a name="trainable-classifiers-definitions"></a>Definiciones de clasificadores entrenables

Microsoft Purview incluye varios clasificadores previamente entrenados. Aparecen en la vista **Clasificadores entrenables** de **clasificación** \> de **datos portal de cumplimiento Microsoft Purview** \> con el estado de `Ready to use`.


- **Adulto, racy y gory**: detecta imágenes de estos tipos. Las imágenes deben tener un tamaño de entre 100 kilobytes (KB) y 4 megabytes (MB) y ser mayores que 50 x 50 píxeles de alto x ancho. El examen y la detección son compatibles con Exchange Online mensajes de correo electrónico y los canales y chats de Microsoft Teams. Detecta contenido en archivos .jpeg, .png, .gif y .bmp.

- **Acuerdos**: detecta contenido relacionado con contratos legales como contratos de no divulgación, declaraciones de trabajo, contratos de préstamo y arrendamiento, contratos de empleo y contratos de no competencia. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Extracto bancario (versión preliminar):** detecta artículos que contienen una transacción financiera de una cuenta bancaria, incluida la información de la cuenta, los depósitos, los retiros, el saldo de la cuenta, los intereses acumulados y los cargos bancarios en un período determinado. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt archivos.

- **Presupuesto (versión preliminar):** detecta documentos presupuestados, previsiones presupuestarias e extractos presupuestarios actuales, incluidos los ingresos y gastos de una organización. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, Archivos .rtf, .txt, .one, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Plan de negocio (versión preliminar):** detecta los componentes de un plan de negocio, incluida la oportunidad de negocio, el plan de lograr los resultados, el estudio de mercado y el análisis de la competencia. Detecta contenido en archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .ppam, .ppa.

- **Especificaciones de construcción (versión preliminar):** detecta especificaciones de construcción para proyectos comerciales e industriales como fábricas, plantas, oficinas comerciales, aeropuertos, carreteras. Captura directrices sobre la calidad, cantidad, tipos de material de construcción, procesos, etc. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .pps, .ppam, .ppa.

- **Sabotaje corporativo (versión preliminar):** detecta mensajes que pueden mencionar actos que dañan o destruyen activos o propiedades corporativos. Este clasificador puede ayudar a los clientes a administrar las obligaciones de cumplimiento normativo, como los estándares de protección de infraestructura crítica de NERC o las regulaciones estatales como el Capítulo 9.05 RCW en el estado de Washington. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.  
> [!IMPORTANT] 
> Mientras se encuentra en versión preliminar, este clasificador puede capturar un gran volumen de contenido masivo de remitentes o boletines de noticias debido a un problema conocido. Mientras están en versión preliminar, puede abordar grandes volúmenes de contenido masivo de remitentes o boletines agregando que el **mensaje no se envía a ninguna de estas condición de dominios** con una lista de dominios que se excluirán. 

- **Quejas de clientes**: el clasificador de quejas de clientes detecta comentarios y quejas realizadas sobre los productos o servicios de su organización. Este clasificador puede ayudarle a cumplir los requisitos normativos sobre la detección y evaluación de las quejas, como los requisitos de consumer Financial Protection Bureau y Food and Drug Administration. En cumplimiento de comunicaciones, detecta contenido en archivos .msg y .eml. En el resto de servicios de Microsoft Purview Information Protection, detecta contenido en archivos .docx, .pdf, .txt, .rtf, .jpg, .jpeg, .png, .gif, .bmp, .svg.

- **Discriminación**: detecta un lenguaje discriminatorio explícito y es sensible al lenguaje discriminatorio contra las comunidades afroamericanas y negras en comparación con otras comunidades. Esto se aplica al cumplimiento de comunicaciones, es un clasificador basado en texto.

- **Archivos de acciones disciplinarias de empleados (versión preliminar):** detecta archivos relacionados con acciones disciplinarias, incluida una acción correctiva o de reprimenda en respuesta a una mala conducta del empleado, una infracción de la regla o un rendimiento deficiente. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Archivos de seguro de empleados (versión preliminar):** detecta documentos relacionados con el seguro médico de los empleados y el seguro de discapacidad en el lugar de trabajo. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .pps, .ppam, .ppa.

- **Contrato de Empleo (versión preliminar):** detecta contratos laborales que contienen detalles como la fecha de inicio, el salario, la compensación, las obligaciones laborales. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt archivos.

- **Finanzas**: detecta contenido en las categorías de finanzas corporativas, contabilidad, economía, banca e inversión. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Informes de auditoría financiera (versión preliminar):** detecta archivos, documentos e informes relativos a la auditoría financiera, tanto externa como interna realizada en una organización. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Estado financiero (versión preliminar):** detecta los estados financieros, como el estado de resultados, el balance, el estado de flujo de caja, el estado de los cambios en el patrimonio. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Regalos & entretenimiento (versión preliminar):** detecta mensajes que pueden sugerir intercambiar regalos o entretenimiento a cambio de servicio, lo que infringe las regulaciones relacionadas con el cohecho. Este clasificador puede ayudar a los clientes a administrar las obligaciones de cumplimiento normativo, como la Ley de Prácticas Corruptas Extranjeras (FCPA), la Ley de Cohecho del Reino Unido y la Regla FINRA 2320. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.
> [!IMPORTANT] 
> Mientras se encuentra en versión preliminar, este clasificador puede capturar un gran volumen de contenido masivo de remitentes o boletines de noticias debido a un problema conocido. Mientras están en versión preliminar, puede abordar grandes volúmenes de contenido masivo de remitentes o boletines agregando que el **mensaje no se envía a ninguna de estas condición de dominios** con una lista de dominios que se excluirán. 

- **Acoso**: Detecta una categoría específica de elementos de texto en lenguaje ofensivo relacionados con la conducta ofensiva dirigida a una o varias personas en función de los siguientes rasgos: raza, origen étnico, religión, origen nacional, género, orientación sexual, edad, discapacidad. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.

- **Formularios médicos/médicos (versión preliminar):** detecta diversos formularios y archivos que se usan para la documentación sistemática de los detalles de admisión de un paciente, la historia clínica, la información del paciente y la solicitud de autorización previa y se usan normalmente en los servicios médicos y de salud. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .pps, .ppam, .ppa.

- **Atención sanitaria**: detecta contenido en aspectos de administración médica y sanitaria, como servicios médicos, diagnósticos, tratamientos, reclamaciones, etc. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **RR. HH**.: detecta contenido en categorías relacionadas con recursos humanos de contratación, entrevista, contratación, formación, evaluación, advertencia y terminación. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Factura (versión preliminar):** detecta facturas que contienen un resumen desglosado de la compra, el saldo total adeudado, el pago pendiente actual y diversos métodos de pago. Detecta contenido en archivos de .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .eml, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **IP**: detecta contenido en categorías relacionadas con la propiedad intelectual, como secretos comerciales e información confidencial similar. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **TI**: detecta contenido en las categorías de tecnología de la información y ciberseguridad, como la configuración de red, la seguridad de la información, el hardware y el software. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Asuntos jurídicos**: detecta contenido en categorías relacionadas con asuntos jurídicos, como litigios, procesos legales, obligación legal, terminología legal, ley y legislación. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Contrato de licencia (versión preliminar):** detecta contratos de licencia, contiene términos y condiciones de uso y compensación para el licenciante. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt archivos.

- **Contratos de préstamo y cartas de oferta (versión preliminar):** detecta contratos de préstamo, cartas de oferta y términos y condiciones contenidos en el documento. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Archivos de fusión y adquisición (versión preliminar):** este clasificador detecta documentos que incluyen carta de intención, hojas de términos y archivos relacionados. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Registros de lote de fabricación (versión preliminar):** este clasificador detecta documentos de lote de fabricación que incluyen detalles sobre todo el proceso de fabricación y el historial de un lote de productos. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Notas de la reunión** (versión preliminar): este clasificador detecta las notas de la reunión. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .pps, .ppam, .ppa.

- **Lavado de dinero (versión preliminar):** detecta signos que pueden sugerir lavado de dinero o participación en actos para ocultar o ocultar el origen o destino de los ingresos. Este clasificador puede ayudar a los clientes a administrar las obligaciones de cumplimiento normativo, como la Ley de Secreto Bancario, la Ley Patriota de EE. UU., la Regla FINRA 3310 y la Ley contra el Lavado de Dinero de 2020. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.
> [!IMPORTANT] 
> Mientras se encuentra en versión preliminar, este clasificador puede capturar un gran volumen de contenido masivo de remitentes o boletines de noticias debido a un problema conocido. Mientras están en versión preliminar, puede abordar grandes volúmenes de contenido masivo de remitentes o boletines agregando que el **mensaje no se envía a ninguna de estas condición de dominios** con una lista de dominios que se excluirán. 

- **Archivos de diseño de red (versión preliminar):** este clasificador detecta documentación técnica sobre redes de equipos, incluidos varios componentes de red, cómo están conectados, su arquitectura, cómo funcionan y dónde solucionan problemas Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .ppam, .ppa.

- **Acuerdo de no divulgación (versión preliminar):** este clasificador detecta acuerdos de no divulgación. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt archivos.

- **Paystub (versión preliminar):** este clasificador detecta los archivos de extracto de pago y salario. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Adquisición**: detecta contenido en categorías de licitación, cita, compra y pago por suministro de bienes y servicios. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla.

- **Documentos de proyecto (versión preliminar):** este clasificador detecta informes y documentos de proyecto, que incluyen documentos de planeamiento de proyectos, documentos de carta de proyecto y programaciones. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .pps, .ppam, .ppa.

- **Blasfemia**: detecta una categoría específica de elementos de texto en lenguaje ofensivo que contienen expresiones que avergüenzan a la mayoría de las personas. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.

- **Connivencia normativa (versión preliminar):** detecta mensajes que pueden infringir los requisitos normativos contra la colusión, como un intento de ocultación de información confidencial. Este clasificador puede ayudar a los clientes a administrar las obligaciones de cumplimiento normativo, como la Ley Antimonopolio Sherman, Ley de intercambio de valores de 1933, Ley de intercambio de valores de 1934, Ley de asesores de inversión de 1940, Ley de la Comisión Federal y ley de Robinson-Patman. Detecta contenido en .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, archivos .svg.
> [!IMPORTANT] 
> Mientras se encuentra en versión preliminar, este clasificador puede capturar un gran volumen de contenido masivo de remitentes o boletines de noticias debido a un problema conocido. Mientras están en versión preliminar, puede abordar grandes volúmenes de contenido masivo de remitentes o boletines agregando que el **mensaje no se envía a ninguna de estas condición de dominios** con una lista de dominios que se excluirán. 

- **Reanudar**: este clasificador detecta la reanudación. Un currículum es un documento que un solicitante de empleo proporciona a un empleador, que tiene una declaración detallada de la experiencia profesional, la educación y los logros previos del candidato. Detecta contenido en archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .txt.

- **Ventas e ingresos (versión preliminar):** este clasificador detecta informes de ventas, declaración de ingresos/ingresos e informes de previsión de ventas/demanda para las organizaciones. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .pptx, .pptm, .ppt, .potx, .potm, .pot, .pot, .ppsx, .ppsm, .ppsm, .ppam, .ppa.

- **Archivos de desarrollo de productos de software (versión preliminar):** este clasificador detecta los archivos utilizados en el desarrollo de software, incluidos el documento de requisitos del producto, las pruebas y el planeamiento de productos, los archivos, incluidos los casos de prueba y los informes de prueba. Detecta contenido en los archivos .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml.

- **Código fuente**: detecta elementos que contienen un conjunto de instrucciones e instrucciones escritas de lenguajes de programación de equipos en GitHub: ActionScript, C, C#, C++, Clojure, CoffeeScript, Go, Haskell, Java, JavaScript, Lua, MATLAB, Objective-C, Perl, PHP, Python, R, Ruby, Scala, Shell, Swift, TeX, Vim Script. Detecta contenido en .msg, .as, .h, .c, .cs, .cc, .cpp, .hpp, .cxx, .hh, .c++, .clj, .edn, .cljc, .cljs, .coffee, .litcoffee, .go, .hs, .lhs, .java, .jar, .js, .mjs, .lua, .m, .mm, .pl, .pm, .t, .xs, .pod, .php, .phar, .php4, .pyc, . R, .r, .rda, . Archivos RData, .rds, .rb, .scala, .sc, .sh, .swift.

  > [!NOTE]
  > El código fuente se entrena para detectar cuándo la mayor parte del texto es código fuente. No detecta texto de código fuente intercalado con texto sin formato.

- **Instrucción de trabajo (versión preliminar):** este clasificador detecta una instrucción de trabajo que contiene detalles como requisitos, responsabilidades, términos y condiciones para ambas partes. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt archivos.

- **Manipulación de acciones (versión preliminar):** detecta signos de posible manipulación de acciones, como recomendaciones para comprar, vender o mantener acciones que puedan sugerir un intento de manipular el precio de las acciones. Este clasificador puede ayudar a los clientes a administrar las obligaciones de cumplimiento normativo, como la Ley de Intercambio de Valores de 1934, la Regla FINRA 2372 y la Regla FINRA 5270. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.
> [!IMPORTANT] 
> Mientras se encuentra en versión preliminar, este clasificador puede capturar un gran volumen de contenido masivo de remitentes o boletines de noticias debido a un problema conocido. Mientras están en versión preliminar, puede abordar grandes volúmenes de contenido masivo de remitentes o boletines agregando que el **mensaje no se envía a ninguna de estas condición de dominios** con una lista de dominios que se excluirán.   

- **Impuestos**: detecta contenido relacionado con impuestos, como planificación fiscal, formularios fiscales, presentación de impuestos, regulaciones fiscales. Detecta contenido en .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, Archivos .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, xla.

- **Amenaza**: detecta una categoría específica de elementos de texto en lenguaje ofensivo relacionados con amenazas para cometer violencia o hacer daño físico o daño a una persona o propiedad. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.

- **Divulgación no autorizada (versión preliminar):** detecta el uso compartido de información que contiene contenido que se designa explícitamente como confidencial o interno para personas no autorizadas. Este clasificador puede ayudar a los clientes a administrar las obligaciones de cumplimiento normativo, como la regla FINRA 2010 y la regla sec 10b-5. Detecta contenido en archivos .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg.
> [!IMPORTANT] 
> Mientras se encuentra en versión preliminar, este clasificador puede capturar un gran volumen de contenido masivo de remitentes o boletines de noticias debido a un problema conocido. Mientras están en versión preliminar, puede abordar grandes volúmenes de contenido masivo de remitentes o boletines agregando que el **mensaje no se envía a ninguna de estas condición de dominios** con una lista de dominios que se excluirán. 





> [!IMPORTANT]
> Tenga en cuenta que los clasificadores integrados y globales que se pueden entrenar no proporcionan una lista exhaustiva o completa de términos o idioma en estas áreas. Además, los estándares lingüísticos y culturales cambian continuamente y, a la luz de estas realidades, Microsoft se reserva el derecho de actualizar estos clasificadores a su discreción. Aunque los clasificadores pueden ayudar a su organización a detectar estas áreas, los clasificadores no están diseñados para proporcionar el único medio de su organización de detectar o abordar el uso de dicho lenguaje. Su organización, no Microsoft ni sus subsidiarias, sigue siendo responsable de todas las decisiones relacionadas con la supervisión, el examen, el bloqueo, la eliminación y la retención de cualquier contenido identificado por un clasificador previamente entrenado, incluido el cumplimiento de la privacidad local y otras leyes aplicables. Microsoft anima a consultar con el asesor legal antes de la implementación y el uso.

Nuestros clasificadores de amenazas, palabras soeces y acoso pueden examinar el contenido en estos idiomas:

- Árabe
- Chino (simplificado)
- Chino (tradicional)
- Neerlandés
- Inglés
- Francés
- Alemán
- Italiano
- Coreano
- Japonés
- Portugués
- Español

Todos los demás son solo inglés.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="see-also"></a>Vea también

- [Etiquetas de retención](retention.md)
- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md)
- [Etiquetas de confidencialidad](sensitivity-labels.md)
- [Definiciones de entidad de tipos de información confidencial](sensitive-information-type-entity-definitions.md)
- [Impresión con dedo del documento](document-fingerprinting.md)
- [Obtener información sobre los tipos de información confidencial basados en coincidencias exactas de datos](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
