---
title: Copiar columna, editor de transformación | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copymaptransformation.f1
helpviewer_keywords:
- Copy Column Transformation Editor
ms.assetid: d8e70541-d563-4ce4-bf66-bc888a0d3026
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7647d25891b37e5f09356d427072e84b45882e4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87673831"
---
# <a name="copy-column-transformation-editor"></a><span data-ttu-id="d6bd6-102">Copiar columna, editor de transformación</span><span class="sxs-lookup"><span data-stu-id="d6bd6-102">Copy Column Transformation Editor</span></span>
  <span data-ttu-id="d6bd6-103">Utilice el cuadro de diálogo **Editor de copia de transformación de columna** para seleccionar las columnas que desee copiar y para asignar nombres a las nuevas columnas de resultados.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-103">Use the **Copy Column Transformation Editor** dialog box to select columns to copy and to assign names for the new output columns.</span></span>  
  
 <span data-ttu-id="d6bd6-104">Para obtener más información acerca de la transformación Copiar columna, vea [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="d6bd6-104">To learn more about the Copy Column transformation, see [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6bd6-105">Cuando solo copie todos los datos de origen a un destino, es posible que no sea necesario utilizar la transformación Copiar columna.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-105">When you are simply copying all of your source data to a destination, it may not be necessary to use the Copy Column transformation.</span></span> <span data-ttu-id="d6bd6-106">En algunos escenarios, puede conectar un origen con un destino de forma directa, cuando no se requiera la transformación de datos.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-106">In some scenarios, you can connect a source directly to a destination, when no data transformation is required.</span></span> <span data-ttu-id="d6bd6-107">En estas circunstancias, por lo general, es preferible utilizar el Asistente para importación y exportación de SQL Server para crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-107">In these circumstances it is often preferable to use the SQL Server Import and Export Wizard to create your package for you.</span></span> <span data-ttu-id="d6bd6-108">Después, puede mejorar y volver a configurar el paquete, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-108">Later you can enhance and reconfigure the package as needed.</span></span> <span data-ttu-id="d6bd6-109">Para obtener más información, vea [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="d6bd6-109">For more information, see [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="d6bd6-110">Opciones</span><span class="sxs-lookup"><span data-stu-id="d6bd6-110">Options</span></span>  
 <span data-ttu-id="d6bd6-111">**Columnas de entrada disponibles**</span><span class="sxs-lookup"><span data-stu-id="d6bd6-111">**Available Input Columns**</span></span>  
 <span data-ttu-id="d6bd6-112">Seleccione las columnas que desea copiar utilizando las casillas.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-112">Select columns to copy by using the check boxes.</span></span> <span data-ttu-id="d6bd6-113">Las selecciones agregan columnas de entrada a la tabla que aparece debajo.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-113">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="d6bd6-114">**Columna de entrada**</span><span class="sxs-lookup"><span data-stu-id="d6bd6-114">**Input Column**</span></span>  
 <span data-ttu-id="d6bd6-115">Seleccione de la lista de columnas de entrada disponibles las columnas que desee copiar.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-115">Select columns to copy from the list of available input columns.</span></span> <span data-ttu-id="d6bd6-116">Las selecciones se reflejan en las casillas activadas en la tabla **Columnas de entrada disponibles** .</span><span class="sxs-lookup"><span data-stu-id="d6bd6-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="d6bd6-117">**Alias de salida**</span><span class="sxs-lookup"><span data-stu-id="d6bd6-117">**Output Alias**</span></span>  
 <span data-ttu-id="d6bd6-118">Escriba un alias para cada columna de salida nueva.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-118">Type an alias for each new output column.</span></span> <span data-ttu-id="d6bd6-119">El valor predeterminado es **Copia de**seguido del nombre de la columna de entrada; no obstante, puede elegir un nombre descriptivo exclusivo.</span><span class="sxs-lookup"><span data-stu-id="d6bd6-119">The default is **Copy of**, followed by the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6bd6-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6bd6-120">See Also</span></span>  
 [<span data-ttu-id="d6bd6-121">Referencia de errores y mensajes de Integration Services</span><span class="sxs-lookup"><span data-stu-id="d6bd6-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
