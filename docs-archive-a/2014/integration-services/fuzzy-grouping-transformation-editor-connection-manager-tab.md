---
title: Editor de transformación agrupación aproximada (pestaña administrador de conexiones) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.connection.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 47b1446d-5331-473c-9cb5-a98b1f55bf5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2a8b0af9f36fdd386f7da375184fd4e4ec5c4be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676057"
---
# <a name="fuzzy-grouping-transformation-editor-connection-manager-tab"></a><span data-ttu-id="ae34f-102">Editor de transformación Agrupación aproximada (pestaña Administrador de conexiones)</span><span class="sxs-lookup"><span data-stu-id="ae34f-102">Fuzzy Grouping Transformation Editor (Connection Manager Tab)</span></span>
  <span data-ttu-id="ae34f-103">Use la pestaña **Administrador de conexiones** del cuadro de diálogo **Editor de transformación Agrupación aproximada** para seleccionar una conexión existente o crear una nueva.</span><span class="sxs-lookup"><span data-stu-id="ae34f-103">Use the **Connection Manager** tab of the **Fuzzy Grouping Transformation Editor** dialog box to select an existing connection or create a new one.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae34f-104">El servidor especificado por la conexión debe ejecutar [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ae34f-104">The server specified by the connection must be running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ae34f-105">La transformación Agrupación aproximada crea objetos de datos temporales en tempdb que pueden ser tan grandes como toda la entrada de la transformación.</span><span class="sxs-lookup"><span data-stu-id="ae34f-105">The Fuzzy Grouping transformation creates temporary data objects in tempdb that may be as large as the full input to the transformation.</span></span> <span data-ttu-id="ae34f-106">Mientras se ejecuta la transformación, se emiten consultas de servidor a esos objetos temporales.</span><span class="sxs-lookup"><span data-stu-id="ae34f-106">While the transformation executes, it issues server queries against these temporary objects.</span></span> <span data-ttu-id="ae34f-107">Esto puede afectar al rendimiento general del servidor.</span><span class="sxs-lookup"><span data-stu-id="ae34f-107">This can affect overall server performance.</span></span>  
  
 <span data-ttu-id="ae34f-108">Para obtener más información acerca de la transformación Agrupación aproximada, vea [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="ae34f-108">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="ae34f-109">Opciones</span><span class="sxs-lookup"><span data-stu-id="ae34f-109">Options</span></span>  
 <span data-ttu-id="ae34f-110">**Administrador de conexiones OLE DB**</span><span class="sxs-lookup"><span data-stu-id="ae34f-110">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="ae34f-111">Seleccione un administrador de conexiones OLE DB existente con el cuadro de lista, o bien cree una conexión con el botón **Nuevo** .</span><span class="sxs-lookup"><span data-stu-id="ae34f-111">Select an existing OLE DB connection manager by using the list box, or create a new connection by using the **New** button.</span></span>  
  
 <span data-ttu-id="ae34f-112">**Nuevo**</span><span class="sxs-lookup"><span data-stu-id="ae34f-112">**New**</span></span>  
 <span data-ttu-id="ae34f-113">Cree una conexión mediante el cuadro de diálogo **Configurar el administrador de conexiones OLE DB** .</span><span class="sxs-lookup"><span data-stu-id="ae34f-113">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae34f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae34f-114">See Also</span></span>  
 <span data-ttu-id="ae34f-115">[Referencia de errores y mensajes de Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="ae34f-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="ae34f-116">Identificar filas de datos similares mediante la transformación Agrupación aproximada</span><span class="sxs-lookup"><span data-stu-id="ae34f-116">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
