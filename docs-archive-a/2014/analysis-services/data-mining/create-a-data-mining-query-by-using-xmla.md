---
title: Crear una consulta de minería de datos mediante XMLA | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- content queries [DMX]
ms.assetid: 8f6b6008-006c-4792-9bd1-64c30dc3fd41
author: minewiskan
ms.author: owend
ms.openlocfilehash: d0e85b17db0781671fab0874706f12fdac95b30b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87676744"
---
# <a name="create-a-data-mining-query-by-using-xmla"></a><span data-ttu-id="062a1-102">Crear una consulta de minería de datos utilizando XMLA</span><span class="sxs-lookup"><span data-stu-id="062a1-102">Create a Data Mining Query by Using XMLA</span></span>
  <span data-ttu-id="062a1-103">Puede crear diversas consultas con los objetos de minería de datos utilizando AMO, DMX o XML/A.</span><span class="sxs-lookup"><span data-stu-id="062a1-103">You can create a variety of queries against data mining objects by using AMO, DMX, or XML/A.</span></span>  
  
 <span data-ttu-id="062a1-104">XML se utiliza para la comunicación entre el servidor de Analysis Services y todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="062a1-104">XML is used for communication between the Analysis Services server and all clients.</span></span> <span data-ttu-id="062a1-105">Por consiguiente, aunque generalmente es mucho más fácil crear consultas de contenido utilizando DMX, puede escribirlas con las instrucciones COMMAND y DISCOVER de XML/A, con un cliente que admita el protocolo SOAP o creando una consulta XML/A en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="062a1-105">Therefore, although it is generally much easier to create content queries by using DMX, you can write queries by using the DISCOVER and COMMAND statements in XML/A, either by using a client that supports the SOAP protocol, or by creating an XML/A query in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="062a1-106">En este tema se explica cómo usar las plantillas XML/A disponibles en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para crear una consulta del contenido del modelo con un modelo de minería de datos almacenadas en el servidor actual.</span><span class="sxs-lookup"><span data-stu-id="062a1-106">This topic explains how to use the XML/A templates that are available in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to create a model content query against a mining model stored on the current server.</span></span>  
  
## <a name="querying-data-mining-schema-rowsets-by-using-xmla"></a><span data-ttu-id="062a1-107">Consultar conjuntos de filas de esquema de minería de datos utilizando XML/A</span><span class="sxs-lookup"><span data-stu-id="062a1-107">Querying Data Mining Schema Rowsets by Using XML/A</span></span>  
  
#### <a name="to-open-an-xmla-template"></a><span data-ttu-id="062a1-108">Para abrir una plantilla XML/A</span><span class="sxs-lookup"><span data-stu-id="062a1-108">To open an XML/A template</span></span>  
  
1.  <span data-ttu-id="062a1-109">En [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], en el menú **Ver** , haga clic en el **Explorador de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="062a1-109">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="062a1-110">Haga clic en el icono de cubo para abrir la lista de las plantillas de Analysis Services.</span><span class="sxs-lookup"><span data-stu-id="062a1-110">Click the cube icon to open the list of Analysis Services templates.</span></span>  
  
3.  <span data-ttu-id="062a1-111">En la lista de categorías de plantilla, expanda **XMLA**, expanda **Conjuntos de filas de esquema**y haga doble clic en **Detectar conjuntos de filas de esquema** para abrir la plantilla en el editor de código adecuado.</span><span class="sxs-lookup"><span data-stu-id="062a1-111">In the list of template categories, expand **XMLA**, expand **Schema Rowsets**, and double-click **Discover Schema Rowsets** to open the template in the appropriate code editor.</span></span>  
  
4.  <span data-ttu-id="062a1-112">En el cuadro de diálogo **Conectar a Analysis Services** , complete la información de conexión y, a continuación, haga clic en **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="062a1-112">In the **Connect to Analysis Services** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="062a1-113">Se abre una ventana nueva del editor de consultas, rellenada con la plantilla **Detectar conjuntos de filas de esquema** .</span><span class="sxs-lookup"><span data-stu-id="062a1-113">A new query editor window opens, populated with the **Discover Schema Rowsets** template.</span></span>  
  
#### <a name="to-discover-column-names-from-the-mining-model-content-schema-rowset"></a><span data-ttu-id="062a1-114">Para detectar los nombres de columna del conjunto de filas de esquema MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="062a1-114">To discover column names from the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="062a1-115">Con la plantilla **Detectar conjuntos de filas de esquema** abierta, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="062a1-115">With the **Discover Schema Rowsets** template open, click **Execute**.</span></span>  
  
     <span data-ttu-id="062a1-116">En el panel **Resultados** se devuelve una lista de conjuntos de filas de esquema que contiene los nombres de los conjuntos de filas de esquema y las columnas de conjunto de filas para todos los conjuntos de filas disponibles en la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="062a1-116">A list of schema rowsets is returned in the **Results** pane that contains the rowset names and rowset columns for all rowsets available on the current instance.</span></span>  
  
2.  <span data-ttu-id="062a1-117">En el panel **consulta** , coloque el cursor después de **\<Restriction List>** y presione Entrar para agregar una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="062a1-117">In the **Query** pane, place the cursor after **\<Restriction List>** and press ENTER to add a new line.</span></span>  
  
3.  <span data-ttu-id="062a1-118">Coloque el cursor en la línea en blanco y escriba \*\* \<SchemaName> DMSCHEMA_MINING_MODEL_CONTENT \</SchemaName> \*\*</span><span class="sxs-lookup"><span data-stu-id="062a1-118">Place the cursor on the blank line and type **\<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT\</SchemaName>**</span></span>  
  
     <span data-ttu-id="062a1-119">La sección completa para las restricciones debería aparecer de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="062a1-119">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<SchemaName>DMSCHEMA_MINING_MODEL_CONTENT</SchemaName>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
4.  <span data-ttu-id="062a1-120">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="062a1-120">Click **Execute**.</span></span>  
  
     <span data-ttu-id="062a1-121">El panel **Resultados** muestra una lista de nombres de columna para el conjunto de filas de esquema especificado.</span><span class="sxs-lookup"><span data-stu-id="062a1-121">The **Results** pane shows a list of column names for the specified schema rowset.</span></span>  
  
#### <a name="to-create-a-content-query-using-the-mining-model-content-schema-rowset"></a><span data-ttu-id="062a1-122">Para crear una consulta de contenido mediante el conjunto de filas de esquema MINING MODEL CONTENT</span><span class="sxs-lookup"><span data-stu-id="062a1-122">To create a content query using the MINING MODEL CONTENT schema rowset</span></span>  
  
1.  <span data-ttu-id="062a1-123">En la plantilla **Detectar conjuntos de filas de esquema** , cambie el tipo de solicitud reemplazando el texto dentro de las etiquetas de tipos de solicitud.</span><span class="sxs-lookup"><span data-stu-id="062a1-123">In the **Discover Schema Rowsets** template, change the request type by replacing the text inside the request type tags.</span></span>  
  
     <span data-ttu-id="062a1-124">Reemplace esta línea:</span><span class="sxs-lookup"><span data-stu-id="062a1-124">Replace this line:</span></span>  
  
     `<RequestType>DISCOVER_SCHEMA_ROWSETS</RequestType>`  
  
     <span data-ttu-id="062a1-125">por la línea siguiente:</span><span class="sxs-lookup"><span data-stu-id="062a1-125">with the following line:</span></span>  
  
     <span data-ttu-id="062a1-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span><span class="sxs-lookup"><span data-stu-id="062a1-126">**\<RequestType>DMSCHEMA_MINING_MODEL_CONTENT\</RequestType>**</span></span>  
  
2.  <span data-ttu-id="062a1-127">Cambie la lista de restricciones para especificar un modelo de minería de datos por el nombre, agregando una condición nueva a las listas de restricciones.</span><span class="sxs-lookup"><span data-stu-id="062a1-127">Change the restriction list to specify a mining model by name, by adding a new condition to the restriction lists.</span></span>  
  
3.  <span data-ttu-id="062a1-128">En la plantilla, coloque el cursor después de `<Restriction List>` y presione Entrar para agregar una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="062a1-128">In the template, place the cursor after `<Restriction List>` and press ENTER to add a new line.</span></span>  
  
4.  <span data-ttu-id="062a1-129">Coloque el cursor en la línea en blanco y escriba **<MODEL_NAME>Nombre de mi modelo</MODEL_NAME>**.</span><span class="sxs-lookup"><span data-stu-id="062a1-129">Place the cursor on the blank line and type **<MODEL_NAME>My model name</MODEL_NAME>**</span></span>  
  
     <span data-ttu-id="062a1-130">La sección completa para las restricciones debería aparecer de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="062a1-130">The complete section for restrictions should appear as follows:</span></span>  
  
     `<Restrictions>`  
  
     `<RestrictionList>`  
  
     `<MODEL_NAME>My model name</MODEL_NAME>`  
  
     `</RestrictionList>`  
  
     `</Restrictions>`  
  
5.  <span data-ttu-id="062a1-131">Haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="062a1-131">Click **Execute**.</span></span>  
  
     <span data-ttu-id="062a1-132">El panel Resultados muestra la definición de esquema, junto con los valores para el modelo especificado.</span><span class="sxs-lookup"><span data-stu-id="062a1-132">The Results pane displays the schema definition, together with the values for the specified model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062a1-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="062a1-133">See Also</span></span>  
 <span data-ttu-id="062a1-134">[Contenido del modelo de minería de datos &#40;Analysis Services:&#41;de minería de datos](mining-model-content-analysis-services-data-mining.md) </span><span class="sxs-lookup"><span data-stu-id="062a1-134">[Mining Model Content &#40;Analysis Services - Data Mining&#41;](mining-model-content-analysis-services-data-mining.md) </span></span>  
 [<span data-ttu-id="062a1-135">Data Mining Schema Rowsets</span><span class="sxs-lookup"><span data-stu-id="062a1-135">Data Mining Schema Rowsets</span></span>](https://docs.microsoft.com/bi-reference/schema-rowsets/data-mining/data-mining-schema-rowsets) 
  
  
