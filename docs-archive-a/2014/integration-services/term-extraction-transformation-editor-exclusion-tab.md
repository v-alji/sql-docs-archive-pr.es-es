---
title: Editor de transformación extracción de términos (pestaña exclusión) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termextraction.inclusionexclusion.f1
helpviewer_keywords:
- Term Extraction Transformation Editor
ms.assetid: 90110d95-fd97-4542-9cda-832c86606130
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9bc4b0401a1dd27111d0498e9e0d848c80da1742
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677208"
---
# <a name="term-extraction-transformation-editor-exclusion-tab"></a><span data-ttu-id="68866-102">Editor de transformación Extracción de términos (pestaña Exclusión)</span><span class="sxs-lookup"><span data-stu-id="68866-102">Term Extraction Transformation Editor (Exclusion Tab)</span></span>
  <span data-ttu-id="68866-103">Use la pestaña **Exclusión** del cuadro de diálogo **Editor de transformación Extracción de términos** para establecer una conexión con una tabla de exclusión y especificar las columnas que contienen términos de exclusión.</span><span class="sxs-lookup"><span data-stu-id="68866-103">Use the **Exclusion** tab of the **Term Extraction Transformation Editor** dialog box to set up a connection to an exclusion table and specify the columns that contain exclusion terms.</span></span>  
  
 <span data-ttu-id="68866-104">Para obtener más información acerca de la transformación Extracción de términos, vea [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="68866-104">To learn more about the Term Extraction transformation, see [Term Extraction Transformation](data-flow/transformations/term-extraction-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="68866-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="68866-105">Options</span></span>  
 <span data-ttu-id="68866-106">**Utilizar términos de exclusión**</span><span class="sxs-lookup"><span data-stu-id="68866-106">**Use exclusion terms**</span></span>  
 <span data-ttu-id="68866-107">Esta opción indica si se excluirán términos específicos durante la extracción de términos mediante la especificación de una columna que contiene los términos de exclusión.</span><span class="sxs-lookup"><span data-stu-id="68866-107">Indicate whether to exclude specific terms during term extraction by specifying a column that contains exclusion terms.</span></span> <span data-ttu-id="68866-108">Si desea excluir términos, debe especificar las siguientes propiedades del origen:</span><span class="sxs-lookup"><span data-stu-id="68866-108">You must specify the following source properties if you choose to exclude terms.</span></span>  
  
 <span data-ttu-id="68866-109">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="68866-109">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="68866-110">Permite seleccionar un administrador de conexiones OLE DB o crear una conexión haciendo clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="68866-110">Select an existing OLE DB connection manager, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="68866-111">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="68866-111">**New**</span></span>  
 <span data-ttu-id="68866-112">Crea una conexión a una base de datos mediante el cuadro de diálogo **Configurar el administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="68866-112">Create a new connection to a database by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="68866-113">**Tabla o vista**</span><span class="sxs-lookup"><span data-stu-id="68866-113">**Table or view**</span></span>  
 <span data-ttu-id="68866-114">Permite seleccionar la tabla o vista que contiene los términos de exclusión.</span><span class="sxs-lookup"><span data-stu-id="68866-114">Select the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="68866-115">**Columna**</span><span class="sxs-lookup"><span data-stu-id="68866-115">**Column**</span></span>  
 <span data-ttu-id="68866-116">Permite seleccionar la columna de la tabla o vista que contiene los términos de exclusión.</span><span class="sxs-lookup"><span data-stu-id="68866-116">Select the column in the table or view that contains the exclusion terms.</span></span>  
  
 <span data-ttu-id="68866-117">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="68866-117">**Configure Error Output**</span></span>  
 <span data-ttu-id="68866-118">Use el cuadro de diálogo [Configurar la salida de errores](../../2014/integration-services/configure-error-output.md) para especificar las opciones de control de errores para las filas que provocan errores.</span><span class="sxs-lookup"><span data-stu-id="68866-118">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68866-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68866-119">See Also</span></span>  
 <span data-ttu-id="68866-120">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="68866-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="68866-121">[Editor de transformación extracción de términos &#40;pestaña extracción de términos&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span><span class="sxs-lookup"><span data-stu-id="68866-121">[Term Extraction Transformation Editor &#40;Term Extraction Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-term-extraction-tab.md) </span></span>  
 <span data-ttu-id="68866-122">[Editor de transformación extracción de términos &#40;pestaña avanzadas&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="68866-122">[Term Extraction Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-extraction-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="68866-123">Transformación Búsqueda de términos</span><span class="sxs-lookup"><span data-stu-id="68866-123">Term Lookup Transformation</span></span>](data-flow/transformations/lookup-transformation.md)  
  
  
