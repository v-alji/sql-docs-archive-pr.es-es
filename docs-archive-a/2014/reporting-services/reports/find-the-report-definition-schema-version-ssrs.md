---
title: Buscar la versión del esquema de definición de informe (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- XML schemas [Reporting Services]
- Report Definition Language, XML schema
- schemas [Reporting Services]
ms.assetid: 67954419-1b61-4481-a3b9-23b4ba7a5624
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 413a270a3722ddda1f418c748fa5b7fba50dfeea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87746156"
---
# <a name="find-the-report-definition-schema-version-ssrs"></a><span data-ttu-id="a5751-102">Buscar la versión del esquema de definición de informe (SSRS)</span><span class="sxs-lookup"><span data-stu-id="a5751-102">Find the Report Definition Schema Version (SSRS)</span></span>
  <span data-ttu-id="a5751-103">Un archivo de definición de informe especifica el espacio de nombres RDL para la versión del esquema de definición de informe que se utiliza para validar el archivo rdl.</span><span class="sxs-lookup"><span data-stu-id="a5751-103">A report definition file specifies the RDL namespace for the version of the report definition schema that is used to validate the rdl file.</span></span> <span data-ttu-id="a5751-104">Cuando se abre un archivo .rdl en un entorno de creación de informes, como por ejemplo, el Diseñador de informes en [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] o el Generador de informes, si el informe se ha creado para un espacio de nombres anterior, se crea automáticamente un archivo de copia de seguridad y se actualiza el informe al espacio de nombres actual.</span><span class="sxs-lookup"><span data-stu-id="a5751-104">When you open an .rdl file in a report authoring environment such as Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or Report Builder, if the report was created for a previous namespace, a backup file is automatically created, and the report is upgraded to the current namespace.</span></span> <span data-ttu-id="a5751-105">Si se guarda la definición de informe actualizada, se ha guardado el archivo .rdl convertido.</span><span class="sxs-lookup"><span data-stu-id="a5751-105">If you save the upgraded report definition, you have saved the converted .rdl file.</span></span> <span data-ttu-id="a5751-106">Esta es la única manera para actualizar una definición de informe.</span><span class="sxs-lookup"><span data-stu-id="a5751-106">This is the only way to upgrade a report definition.</span></span> <span data-ttu-id="a5751-107">La definición de informe en sí misma no se actualiza en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a5751-107">The report definition itself is not upgraded on a report server.</span></span> <span data-ttu-id="a5751-108">El informe de compilación se actualiza en un servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a5751-108">The compiled report is upgraded on a report server.</span></span> <span data-ttu-id="a5751-109">Para más información, consulte [Upgrade Reports](../install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="a5751-109">For more information, see [Upgrade Reports](../install-windows/upgrade-reports.md).</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-a-report"></a><span data-ttu-id="a5751-110">Identificar la versión de esquema RDL de un informe</span><span class="sxs-lookup"><span data-stu-id="a5751-110">How to: Identify the RDL Schema Version of a Report</span></span>  
  
1.  <span data-ttu-id="a5751-111">Abra el archivo .rdl de informe en una aplicación como Bloc de notas o XML Notepad 2007 en la que pueda ver el xml.</span><span class="sxs-lookup"><span data-stu-id="a5751-111">Open the report .rdl file in an application such as Notepad or XML Notepad 2007 in which you can view the xml.</span></span>  
  
     <span data-ttu-id="a5751-112">El elemento de informe XML especifica el espacio de nombres del esquema.</span><span class="sxs-lookup"><span data-stu-id="a5751-112">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="a5751-113">Por ejemplo, el elemento de informe siguiente especifica el espacio de nombres para el Diseñador de informes y el espacio de nombres para la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="a5751-113">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="a5751-114">La dirección URL siguiente especifica el espacio de nombres para la definición de informe: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span><span class="sxs-lookup"><span data-stu-id="a5751-114">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-report-designer"></a><span data-ttu-id="a5751-115">Identificar la versión de esquema RDL del Diseñador de informes</span><span class="sxs-lookup"><span data-stu-id="a5751-115">How to: Identify the RDL Schema Version of Report Designer</span></span>  
  
1.  <span data-ttu-id="a5751-116">Abra un proyecto nuevo.</span><span class="sxs-lookup"><span data-stu-id="a5751-116">Open a new project.</span></span> <span data-ttu-id="a5751-117">La versión del proyecto que elija determina la versión del esquema RDL.</span><span class="sxs-lookup"><span data-stu-id="a5751-117">The version of the project that you choose determines the version of the RDL schema.</span></span> <span data-ttu-id="a5751-118">En [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], se admite más de una versión de esquema.</span><span class="sxs-lookup"><span data-stu-id="a5751-118">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], more than one schema version is supported.</span></span> <span data-ttu-id="a5751-119">Para obtener más información, vea [Implementación y compatibilidad de versiones en las herramientas de datos de SQL Server &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="a5751-119">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="a5751-120">En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5751-120">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="a5751-121">Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="a5751-121">The **Add New Item** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="a5751-122">En el panel **Plantillas** , haga clic en **Informe**.</span><span class="sxs-lookup"><span data-stu-id="a5751-122">In the **Templates** pane, click **Report**.</span></span>  
  
4.  <span data-ttu-id="a5751-123">En **Nombre**, escriba un nombre para el informe o acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="a5751-123">In **Name**, type a report name or accept the default.</span></span>  
  
5.  <span data-ttu-id="a5751-124">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a5751-124">Click **Add**.</span></span> <span data-ttu-id="a5751-125">El Diseñador de informes abre un nuevo informe en blanco en la vista Diseño.</span><span class="sxs-lookup"><span data-stu-id="a5751-125">Report Designer opens a new blank report in Design view.</span></span>  
  
6.  <span data-ttu-id="a5751-126">En el menú **Ver** , haga clic en **Código**.</span><span class="sxs-lookup"><span data-stu-id="a5751-126">On the **View** menu, click **Code**.</span></span> <span data-ttu-id="a5751-127">La definición de informe se muestra como un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="a5751-127">The report definition is displayed as an XML file.</span></span>  
  
     <span data-ttu-id="a5751-128">El elemento de informe XML especifica el espacio de nombres del esquema.</span><span class="sxs-lookup"><span data-stu-id="a5751-128">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="a5751-129">Por ejemplo, el elemento de informe siguiente especifica el espacio de nombres para el Diseñador de informes y el espacio de nombres para la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="a5751-129">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner  
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="a5751-130">La dirección URL siguiente especifica el espacio de nombres para la definición de informe: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="a5751-130">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-on-the-report-server"></a><span data-ttu-id="a5751-131">Identificar la versión de esquema RDL en el servidor de informes</span><span class="sxs-lookup"><span data-stu-id="a5751-131">How to: Identify the RDL Schema Version on the Report Server</span></span>  
  
-   <span data-ttu-id="a5751-132">En el Administrador de informes, escriba la siguiente dirección URL para el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="a5751-132">In Report Manager, type the URL for the report server.</span></span> <span data-ttu-id="a5751-133">Por ejemplo, la dirección URL siguiente especifica un servidor de informes en el equipo local:</span><span class="sxs-lookup"><span data-stu-id="a5751-133">For example, the following URL specifies a report server on the local computer:</span></span>  
  
     `http://localhost/reportserver/reportdefinition.xsd`  
  
     <span data-ttu-id="a5751-134">Se abre el archivo .xsd en el explorador.</span><span class="sxs-lookup"><span data-stu-id="a5751-134">The .xsd file opens in the browser.</span></span>  
  
     <span data-ttu-id="a5751-135">El elemento de esquema XML especifica el espacio de nombres del esquema.</span><span class="sxs-lookup"><span data-stu-id="a5751-135">The XML schema element specifies the schema namespace.</span></span> <span data-ttu-id="a5751-136">Por ejemplo, el elemento de esquema siguiente especifica tres espacios de nombres: la referencia de targetNamespace usada internamente por [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], la referencia de xsd para el propio esquema (xsd) y la referencia de la definición de informe.</span><span class="sxs-lookup"><span data-stu-id="a5751-136">For example, the following schema element specifies three namespaces: the targetNamespace reference that is used internally by [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], the xsd reference for the schema itself (xsd), and the report definition reference.</span></span>  
  
    ```  
    <xsd:schema   
    targetNamespace="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    elementFormDefault="qualified">  
    ```  
  
     <span data-ttu-id="a5751-137">La dirección URL siguiente especifica el espacio de nombres para la definición de informe: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="a5751-137">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5751-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a5751-138">See Also</span></span>  
 <span data-ttu-id="a5751-139">[Actualizar informes](../install-windows/upgrade-reports.md) </span><span class="sxs-lookup"><span data-stu-id="a5751-139">[Upgrade Reports](../install-windows/upgrade-reports.md) </span></span>  
 [<span data-ttu-id="a5751-140">Lenguaje RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="a5751-140">Report Definition Language &#40;SSRS&#41;</span></span>](report-definition-language-ssrs.md)  
  
  
