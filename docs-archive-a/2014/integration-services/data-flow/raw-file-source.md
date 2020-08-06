---
title: Origen de archivo sin formato | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfilesource.f1
helpviewer_keywords:
- sources [Integration Services], Raw File
- raw data [Integration Services]
- Raw File source
ms.assetid: 5b4daea5-7f76-4674-aa77-0a79f9f97f7d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4cbc5800c4fb2b90b74e66b6ff161118b2b550f2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670456"
---
# <a name="raw-file-source"></a><span data-ttu-id="2072b-102">archivo sin formato, origen</span><span class="sxs-lookup"><span data-stu-id="2072b-102">Raw File Source</span></span>
  <span data-ttu-id="2072b-103">El origen de archivo sin formato lee datos sin formato de un archivo.</span><span class="sxs-lookup"><span data-stu-id="2072b-103">The Raw File source reads raw data from a file.</span></span> <span data-ttu-id="2072b-104">Como la representación de los datos es la nativa del origen, no es necesario traducir los datos y prácticamente no es necesario analizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="2072b-104">Because the representation of the data is native to the source, the data requires no translation and almost no parsing.</span></span> <span data-ttu-id="2072b-105">Esto significa que el origen de archivo sin formato puede leer datos más rápidamente que otros orígenes, como el origen de archivo plano o el origen de OLE DB.</span><span class="sxs-lookup"><span data-stu-id="2072b-105">This means that the Raw File source can read data more quickly than other sources such as the Flat File and the OLE DB sources.</span></span>  
  
 <span data-ttu-id="2072b-106">El origen de archivo sin formato se usa para recuperar datos sin formato escritos previamente por el destino de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="2072b-106">The Raw File source is used to retrieve raw data that was previously written by the Raw File destination.</span></span> <span data-ttu-id="2072b-107">También puede señalar el origen de archivo sin formato para un archivo sin formato vacío que contenga solo las columnas (archivo solo de metadatos).</span><span class="sxs-lookup"><span data-stu-id="2072b-107">You can also point the Raw File source to an empty raw file that contains only the columns (metadata-only file).</span></span> <span data-ttu-id="2072b-108">El destino de archivo sin formato se usa para generar el archivo de solo metadatos sin tener que ejecutar el paquete.</span><span class="sxs-lookup"><span data-stu-id="2072b-108">You use the Raw File destination to generate the metadata-only file without having to run the package.</span></span> <span data-ttu-id="2072b-109">Para más información, consulte [Raw File Destination](raw-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="2072b-109">For more information, see [Raw File Destination](raw-file-destination.md).</span></span>  
  
 <span data-ttu-id="2072b-110">El archivo sin formato contiene información sobre el orden.</span><span class="sxs-lookup"><span data-stu-id="2072b-110">The raw file format contains sort information.</span></span> <span data-ttu-id="2072b-111">El destino de archivo sin formato guarda toda la información sobre el orden incluidas las marcas de comparación para las columnas de cadena.</span><span class="sxs-lookup"><span data-stu-id="2072b-111">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="2072b-112">El origen de archivo sin formato lee y respeta la información sobre el orden.</span><span class="sxs-lookup"><span data-stu-id="2072b-112">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="2072b-113">Tiene la opción de configurar el origen de archivo sin formato para omitir los marcas de orden en el archivo; para ello use el Editor avanzado.</span><span class="sxs-lookup"><span data-stu-id="2072b-113">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="2072b-114">Para obtener más información acerca de las marcas de comparación, vea [Comparing String Data](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="2072b-114">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="2072b-115">Para configurar el archivo sin formato, especifique el nombre del archivo leído por el origen de archivo sin formato.</span><span class="sxs-lookup"><span data-stu-id="2072b-115">You configure the Raw File by specifying the name of the name of the file that the Raw File source reads.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2072b-116">Este origen no usa un administrador de conexiones.</span><span class="sxs-lookup"><span data-stu-id="2072b-116">This source does not use a connection manager.</span></span>  
  
 <span data-ttu-id="2072b-117">Este origen tiene una salida.</span><span class="sxs-lookup"><span data-stu-id="2072b-117">This source has one output.</span></span> <span data-ttu-id="2072b-118">No admite una salida de error.</span><span class="sxs-lookup"><span data-stu-id="2072b-118">It does not support an error output.</span></span>  
  
## <a name="configuration-of-the-raw-file-source"></a><span data-ttu-id="2072b-119">Configuración del origen de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="2072b-119">Configuration of the Raw File Source</span></span>  
 <span data-ttu-id="2072b-120">Puede establecer propiedades a través del Diseñador de [!INCLUDE[ssIS](../../includes/ssis-md.md)] o mediante programación.</span><span class="sxs-lookup"><span data-stu-id="2072b-120">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="2072b-121">El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="2072b-121">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="2072b-122">Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2072b-122">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="2072b-123">Common Properties</span><span class="sxs-lookup"><span data-stu-id="2072b-123">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="2072b-124">Propiedades personalizadas de archivo sin formato</span><span class="sxs-lookup"><span data-stu-id="2072b-124">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="2072b-125">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="2072b-125">Related Tasks</span></span>  
 <span data-ttu-id="2072b-126">Para más información sobre cómo establecer las propiedades del componente, vea [Establecer las propiedades de un componente de flujo de datos](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="2072b-126">For information about how to set the properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="2072b-127">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="2072b-127">Related Content</span></span>  
  
-   <span data-ttu-id="2072b-128">Entrada del blog [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), en sqlservercentral.com</span><span class="sxs-lookup"><span data-stu-id="2072b-128">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2072b-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2072b-129">See Also</span></span>  
 <span data-ttu-id="2072b-130">[Destino de archivo sin formato](raw-file-destination.md) </span><span class="sxs-lookup"><span data-stu-id="2072b-130">[Raw File Destination](raw-file-destination.md) </span></span>  
 [<span data-ttu-id="2072b-131">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="2072b-131">Data Flow</span></span>](data-flow.md)  
  
  
