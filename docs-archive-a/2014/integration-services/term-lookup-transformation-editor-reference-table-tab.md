---
title: Editor de transformación búsqueda de términos (pestaña tabla de referencia) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.termlookup.referencetable.f1
helpviewer_keywords:
- Term Lookup Transformation Editor
ms.assetid: 86ccec6d-615b-4f84-9226-ff80d8012f17
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f76f15d894896e70139ef80cb2ebad7004ef47ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87677204"
---
# <a name="term-lookup-transformation-editor-reference-table-tab"></a><span data-ttu-id="2ce6d-102">Editor de transformación Búsqueda de términos (pestaña Tabla de referencia)</span><span class="sxs-lookup"><span data-stu-id="2ce6d-102">Term Lookup Transformation Editor (Reference Table Tab)</span></span>
  <span data-ttu-id="2ce6d-103">Use la pestaña **Tabla de referencia** del cuadro de diálogo **Editor de transformación Búsqueda de términos** para especificar la conexión con la tabla de referencia (búsqueda).</span><span class="sxs-lookup"><span data-stu-id="2ce6d-103">Use the **Reference Table** tab of the **Term Lookup Transformation Editor** dialog box to specify the connection to the reference (lookup) table.</span></span>  
  
 <span data-ttu-id="2ce6d-104">Para obtener más información acerca de la transformación Búsqueda de términos, vea [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="2ce6d-104">To learn more about the Term Lookup transformation, see [Term Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="2ce6d-105">Opciones</span><span class="sxs-lookup"><span data-stu-id="2ce6d-105">Options</span></span>  
 <span data-ttu-id="2ce6d-106">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="2ce6d-106">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="2ce6d-107">Seleccione un administrador de conexiones de la lista o cree una conexión haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2ce6d-107">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="2ce6d-108">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="2ce6d-108">**New**</span></span>  
 <span data-ttu-id="2ce6d-109">Cree una conexión mediante el cuadro de diálogo **Configurar el administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="2ce6d-109">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="2ce6d-110">**Nombre de la tabla de referencia**</span><span class="sxs-lookup"><span data-stu-id="2ce6d-110">**Reference table name**</span></span>  
 <span data-ttu-id="2ce6d-111">Seleccione una tabla de búsqueda o una vista de la base de datos; para ello, seleccione un elemento de la lista.</span><span class="sxs-lookup"><span data-stu-id="2ce6d-111">Select a lookup table or view from the database by selecting an item from the list.</span></span> <span data-ttu-id="2ce6d-112">La tabla o vista debe contener una columna con una lista de términos con los que se pueda comparar el texto de la columna de origen.</span><span class="sxs-lookup"><span data-stu-id="2ce6d-112">The table or view should contain a column with an existing list of terms that the text in the source column can be compared to.</span></span>  
  
 <span data-ttu-id="2ce6d-113">**Configurar la salida de errores**</span><span class="sxs-lookup"><span data-stu-id="2ce6d-113">**Configure Error Output**</span></span>  
 <span data-ttu-id="2ce6d-114">Use el cuadro de diálogo [Configurar la salida de errores](../../2014/integration-services/configure-error-output.md) para especificar las opciones de control de errores de las filas que provocan errores.</span><span class="sxs-lookup"><span data-stu-id="2ce6d-114">Use the [Configure Error Output](../../2014/integration-services/configure-error-output.md) dialog box to specify error handling options for rows that cause errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce6d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2ce6d-115">See Also</span></span>  
 <span data-ttu-id="2ce6d-116">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="2ce6d-116">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="2ce6d-117">[Editor de transformación búsqueda de términos &#40;pestaña búsqueda de términos&#41;](../../2014/integration-services/term-lookup-transformation-editor-term-lookup-tab.md) </span><span class="sxs-lookup"><span data-stu-id="2ce6d-117">[Term Lookup Transformation Editor &#40;Term Lookup Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-term-lookup-tab.md) </span></span>  
 <span data-ttu-id="2ce6d-118">[Editor de transformación búsqueda de términos &#40;pestaña avanzadas&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span><span class="sxs-lookup"><span data-stu-id="2ce6d-118">[Term Lookup Transformation Editor &#40;Advanced Tab&#41;](../../2014/integration-services/term-lookup-transformation-editor-advanced-tab.md) </span></span>  
 [<span data-ttu-id="2ce6d-119">Transformación Extracción de términos</span><span class="sxs-lookup"><span data-stu-id="2ce6d-119">Term Extraction Transformation</span></span>](data-flow/transformations/term-extraction-transformation.md)  
  
  
